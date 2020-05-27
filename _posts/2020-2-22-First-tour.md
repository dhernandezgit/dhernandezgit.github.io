---
layout: post
title: First tour
tags: FollowLine
thumbnail: https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/first.png
---
This post will explain the first design of a PID controller for the line follower to make it able to do a first complete lap. PIDs are a control method based on a fast loop with feedback from some kind of sensors. In this case, the sensor is the camera and the desired control variable is the steering speed.

## P controller
The first proposed controller is a simple P controller. This means that the value of the control action in the current instant (uk) is proportional to the difference between the desired value (ref) and the measured value (yk) of the control variable. In this case, the equation on the loop is something like the following one:
> uk = P * (ref - yk)

As mentioned before, the control action for this first test is directly the angular speed (W) of the vehicle, with a fixed value of linear speed (V). The measured value is not so straightforward and there are several possible measurable values from the processed image that will be discussed on the following post. For this one, the measured value is the position on pixels of the center of the line on the first row of the image, calculated as the mean value of the pixels labeled as line. The set point or reference is the desired position on pixels of the line, in this case the center of the image.

With this, and performing some initial tests to find the appropriate values for this 2 parameters (P and V) we get a first working controller!
<br/><br/>
<iframe width="100%"
src="https://www.youtube.com/embed/_5p_hDuIynk">
</iframe>

## PD controller
Working a bit more, we can use not just the actual value of the error (ek) calculated as (ref - y) but also the past values to calculate the control action. In this case, it's only needed to initialize a variable to store the past value of the error and update the control action with the following equation:
> uk = P * ek + D * (ek - ek-1)

In this case, tuning the 3 parameters it's observable that the controller can reach a greater speed without losing the stability, as we include the value of the error tendency on the formula. With this simple steps, we designed our first working controller*!
<br/><br/>
<iframe width="100%"
src="https://www.youtube.com/embed/0oiFbe1A1IA">
</iframe>

*Do not try this with you own car. Seriously.


<p align="center">
<a href="https://jderobot.github.io/">
<img alt="JdeRobot" src="https://avatars1.githubusercontent.com/u/10959337?s=200&v=4" width="15%">
</a>
</p>