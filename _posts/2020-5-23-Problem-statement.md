---
layout: post
title: Peak performance
tags: FollowLine
thumbnail: https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/final.png
---
This post explain the last tricks to get a fast and robust controller. To the infinity and beyond!

## One control to rule them all
What happens when the controller lose control? This is the part where we prevent the possible situation of not being able to find the line. The current solution is going back slowly and spinning in the opposite direction of where the line was last seen. This way the controller is able to refind the line and go back to the circuit... If the car model survived the crash.

## Faster
The first option to break records is fine tuning. The process to find the best controller was slowly increasing the speed of one part of the control and adjusting each one of the parameters separately, and then increasing the speed of the opposite part. This method, as simple as it seems really increased the performance of the control, being able to reach speeds of 25 over the curves.
<br/><br/>
<iframe width="100%"
src="https://www.youtube.com/embed/AnQLBhLMvBQ">
</iframe> 
<br/><br/>
The last option to gain some extra milliseconds is including acceleration to the controller. In this case it is achieved by increasing the speed reference while it remains the same (line or curve) and resetting the value to the starting value when the control changes. This method allowed to reach the speed of 50 on the long straight lines, but failing to work properly on the curves.
<br/><br/>
<iframe width="100%"
src="https://www.youtube.com/embed/mCYW-yUiIjA">
</iframe> 
<br/><br/>
Finally, here is a detailed tour of the circuit with a stable and fast controller, playing with the Gazebo interface.
<br/><br/>
<iframe width="100%"
src="https://www.youtube.com/embed/3L1nTG8VqS8">
</iframe> 

Thanks for reading!

<p align="center">
<a href="https://jderobot.github.io/">
<img alt="JdeRobot" src="https://avatars1.githubusercontent.com/u/10959337?s=200&v=4" width="15%">
</a>
</p>