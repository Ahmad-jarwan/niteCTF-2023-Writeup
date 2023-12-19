<h1>Phantasmagoria</h1>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/169a5d604b3fb8f6904d0efbd01d17ec53ee3189/images/Screenshot%202023-12-19%20211146.png "")

<h3>As we see here we are given a forensic challenge with gif image file </h3>

![](https://github.com/Ahmad-jarwan/niteCTF-2023/blob/1458742d9bd5506a67d61f0e06d37930d0534f29/Phantasmagoria/ChallengeFile.gif)

<h1>How to Solve</h1>
<div>first i understand it is a puzzel i just need to get all the images inside gif file and merge the image to get the QR code so i found this website https://ezgif.com/split he give me the image sorted </div>
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
