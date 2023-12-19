<h1>Phantasmagoria</h1>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/169a5d604b3fb8f6904d0efbd01d17ec53ee3189/images/Screenshot%202023-12-19%20211146.png "")

<h3>As we see here we are given a forensic challenge with gif image file </h3>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/1458742d9bd5506a67d61f0e06d37930d0534f29/Phantasmagoria/ChallengeFile.gif)

<h1>How to Solve</h1>
<div>first i understand it is a Puzzle i just need to get all the images inside gif file and merge the image to get the QR code so i found this website https://ezgif.com/split he give me the image sorted </div>
<h2>how did i know the image was sorted and how i know there are 2 QR </h2>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/4c254606d76a179257f93b87ef7204ae3988a81c/images/QR%20in%20general%20.png "")

<div>if we take look of QR structure we will see there is 3 squares in the right&left of top and in left down </div>
<div>and then if we take look on the first part of image and the last part we will realize  we have three squares </div>
<div>First Part: </div>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/11e4c4369c8a55bfab24e9cc2aac7b4988ac3c08/images/first%20section.png "")

<div>Last Part: </div>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/11e4c4369c8a55bfab24e9cc2aac7b4988ac3c08/images/footer%20.png "")

<div>now how i know we have 2 QR if any one foucs on the image they are duplicated but one with dark and white background and the second with rgb color </div>

<h1>Merge images </h1>
<div>After I download the image i extract from gif file I use this website https://products.aspose.app/imaging/image-merge  to get the full QR code by adding 10 image at once on the order </div>
<div>And I do this operation twice one for Black&White QR and the second for colorized QR </div>
<h3>As example after i merge the first 10 pices of colorized QR i got this </h3>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/e84f53361383421aec11173c594bfc28621dd8f7/images/MergedImages%20(0).png "")
<div>And so on you will continue to get all part of QR and Merge all part again </div>
<h1>What will be inside the image </h1>
<div>now the first QR code </div>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/ed0ff67ffbdaecf2ced82f30694133b1c9557054/images/QR_MergedImages.png "")
<div>i got rick roll haha it's prank i got the words of Rick Astley's song so the flag not here  </div>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/364158e4ab57d64f564151d3236f77d87e18e4e1/images/QR_RGB_MergedImages.png "")

<div>but if we see the RGB image we will got n value the first thing i though it's an rsa and i got the N i should get the other C and E </div>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/ed873e8495d53e0890040da3cb69e33a9f240bb6/images/Screenshot%202023-12-19%20234844.png "")
<h1>Get C and E </h1>
<div>if we go to any stegnography website and get the RGB image in red and blue color we will get the E And C https://www.aperisolve.com/ this is a awesome website btw </div>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/aca1cc4fce961a3f84c48d1a658a9888d0b805c8/images/Screenshot%202023-12-19%20235712.png "") 
<div>so now we have the public key rsa which (e,n) and the chiper text </did>
<div>i use online decoder rsa https://www.dcode.fr/rsa-cipher</div> 
<div>n = 676791844642584980698053302310223785374313385409403045588113725155016812136880955271984417983873824026716210778280593193636428565069776587137028449750730272186542437844497237414456209835073368629304006715276260751133887794296529492487334855122615389995863721291118118732027231915027379993143595417642293787966513241655113162242886681266092600146489606133012439809001110360370456177919007156990233918640321509862398958571381198232567856064240532200641725144788895054486316049075570223352817949029389327640788515067890854211670242990506500384161300646686642943025006620039197262649011645414593036304976338145694104210102443351633126298836188101611468727285524121350542326419652662876739876424845347479917953656717595927494531015461852178181228442298434483771040709741405863344788052581819778178386583342583162229291454214612057110480344851213811069677642675472810388144418347604660534845766311357971367827288922569847511151214222283088837375795803519692209817560935544948763568461379169948048755718648569869223176458921320498263580169173526435342144022663119655800743047260437276330638259847190731172746917271144508137645140847075476659515891899224768333964574305422773267597098695989323996565887847836862251898531683849611661559455231</div>
<div>e = 580107295407929983455474259123048958892268616065202610504097478704300124688755104518843786843320420594328180667097651308831224484345522788974595814072054519017036375295283346355248179858634315967974862898808223500971903823682739564989144161533670334282168903963815530341737627355737754279837367500836251818257011349990096996208188583942365085839848233828296376979143808880317533866787720420277343358834561294167770535918326741342201019483634741886264335838390481475273985184921917334302415384882333709406390155772477875038574493991862714614995400554302836808307148531462169082270581410355365459689979718410594946465757345418167500441759086471705367181923686763503684027485517203432506707344347783693800292516556903295589747181683464968271679813556995850747615373120820875968987307345135528514167832232730587801941826874478866266248104183762332450746296192019414713597801306568432969966780462547060873090168456225293338399628593451782650498742449891396155749182822135489206945557245425857310335962454516172608455034226164240182895467945937699668831887344790952929260964764874686656180773292544947330844662364326840643409486240155063338637903846556007310024878543296033058049856666554133648498640712529858440916870291185920494704803143</div>
<div>c = 544342977532404237408772156018844280042896018581454027178213021966933179442845437798554673545620437077690160719361782366496084247799878518975715150796511397840519300211970113174385006721394626735058682356052519383771627256690815712967712491626102749570315765793607724436304925195447530638210491706318962714162678496224311664384796373433133484652485030434903014477989234639514499007880766266336487828650563294477369869284464009446027489791555956252580321314582911124874488376100440106092810747363952104507525352045668294528122872841750097177464905666071617876996930044144939116978812626955932102034257961709955290700427646253669485222926458797085660621146417897771007300680609504190057013973071878997514930801531407454022185046675516302040705165530852907708234116394362314177321060017882453944778571652891878787594756953941882037855500075620246192415211529447574738034705454952785438018144229155984327393211236378437222298093295385097467084627926991924915499333729453319553497885055095056469836597798913831551134953389760004832277777103218600963483821015591765052538315472933051886240356519093653467540608074668757871161552736235872811563026735761624551483971176815836236188425184614789972749058974348218017069740385931961400851689995</div>
<h1>so the flag will be nite{71m3_70_fr4m3_7h15_c0l0urful_e_n_c_0d3d_qr} </h1>
<div>Thank you for Reading </div>
