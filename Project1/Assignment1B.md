## What are Channels and Kernels (according to EVA)?

### Channels
Channels are the input image on which the kernels are applied. After convolution is applied on the channels, the output generated is also called channel. That can also be said as the output channel. There can be many channels for an input image. For eg Dicom images has four channels. Figure below shows an image with 4X4 matrix with 3 channels-> Red, Green and Blue.

![http](http://xrds.acm.org/blog/wp-content/uploads/2016/06/Figure1.png)

### Kernels 

Kernels are the matrix which are applied on the input channels to extract edges, features, gradients, etc from the image. They are used to get different effects such as blurring, sharpening, outlining or embossing.
In the figure below 3X3 Kernel matrix is applied on the image matrix to get the result 89. The calcualtion is shown below this image.

![http](http://machinelearninguru.com/_images/topics/computer_vision/basics/convolution/1.JPG)

![http](http://machinelearninguru.com/_images/topics/computer_vision/basics/convolution/3.JPG)

## Why should we only (well mostly) use 3x3 Kernels?

3X3 kernels can be used to approaximate any kernel size. To get the same effect as 1 5X5 kernels we can use 2 3X3 kernels. By using 3X3 kernels we can reduce the amount of parameters or weights to be learned by the network. So, by 3X3 kernels we get less parameters to learn and more layers. But by large kernels we get less number of layers and more parameters to learn. But there is a disadvantage with 3X3 kernels that they will consume more memory as all the layers needs to be in RAM for performing backpropagation.

## How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)

Operation1 : 199X199 -> 3X3 CN -> 197 X 197 -> Lost 2 Pixels
Operation2 : 197X197 -> 3X3 CN -> 195 X 195 -> Lost 4 Pixels[Cumulative]
..................
..................
..................
Operation 99: 3X3 -> 3X3 CN -> 1X1 -> Lost 99*2=198 Pixels[Cumulative]







