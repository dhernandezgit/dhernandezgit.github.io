---
layout: post
title: Image processing
tags: FollowLine
thumbnail: https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/test.png
---
In this post I'll talk about the method to process the captured images from the car so it becomes easier to extract information from them.

Let's take a look at an example of a frame extracted from the car.
Image Car

The line is clearly of a different color from the rest of the image, being able to segment it by a simple color filter. To make it more robust, the image is processed in the HSV color-space, as the color of the line will be always red but the saturation and brightness could be different. Then, the line is defined as the pixels that are between a range of values on the HSV color-space. Furthermore, there is a part of the image with non-relevant information to track the line, given that the circuit is plain, so the mask is cropped to only contain relevant information.

To be able to show this processing, the resulting mask is converted to a 3 channel image by formatting the result as a uint8 array with 3 concatenated masks on the channel axis. An additional step is performed to show both the original frame and the processed frame side by side. The processed frame is resized to fit the heigth of the original one, and then they are concatenated side by side.

Image JdeRobot
![Test]("Test")