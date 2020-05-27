---
layout: post
title: Controlling the controller
tags: FollowLine
thumbnail: https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/error2.png
---
This post will explain some considerations to make on choosing the measured variables and some methods to achieve a better and more robust control.

## Measuring the chaos
### Distance
For the PID controller we used the value of the error. This error can be measured in different ways. The first approach was simply measuring the horizontal distance between the reference (center of the image) and the current point. This point has one parameter to play with, the row where the distance is measured:
<br/><br/>
<p align="center">
<img src="https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/error1.png" alt="ErrorDist" width="80%">
</p>
<br/><br/>
Experimentally it is proved that the best row is the closest to the horizon line, given that the change on the reference is measured with more time and distance. Currently, the line is not measured in one row, but in several rows, extracting a polynomial and interpolating the value for that row to improve the robustness. This is the method used for the previous videos, but the best results are limited due to the nature of this measurement.

### Angle
To improve the controller, another measurement is tested: Angles. Here, the value of the error depends on the angle of the line from the car. This method admits two parameters, the measured row and the point from where the angle is measured:
<br/><br/>
<p align="center">
<img src="https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/error2.png" alt="ErrorAngle" width="80%">
</p>
<br/><br/>
When the base is higher the error raises faster and the controller is more robust, being able to step up the speed of the vehicle reaching a value of 15 while following the line because the reactions are faster.
<br/><br/>
<iframe width="100%"
src="https://www.youtube.com/embed/N7fTuUomPjc">
</iframe>

## Double PD
The next step to improve the controller is... More controllers. The needs on a straight line and on a curve are different, and the speed can be raised when the control is more simple.
### Curve detection
To be able to know if we are on a curve, the first step is sampling the line and calculating a value to check the fitting of the line over a straight line. The first test calculation is the R2, but when the pixels are slightly not aligned due to a bad detection this value raises and it is classified as a straight line. The second method is measuring the distance from each point to the perfect straight line, giving a more balanced estimation. The line is classified as curve when the distance is bigger than a threshold value. 

### Control
The control is simple. Each controller is used with the classification of the curve detector. The straight line controller has a lower value of P because the control is simpler, and the speed used along this controller is considerably higher, reaching the value of 25.
<br/><br/>
<iframe width="100%"
src="https://www.youtube.com/embed/3Ei3zmC6uDo">
</iframe>

<p align="center">
<a href="https://jderobot.github.io/">
<img alt="JdeRobot" src="https://avatars1.githubusercontent.com/u/10959337?s=200&v=4" width="15%">
</a>
</p>