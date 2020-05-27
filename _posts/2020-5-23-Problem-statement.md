---
layout: post
title: Problem statement
tags: Reconstruction
thumbnail: https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/scene.png
---
In this post is explained the material and objective of the 3D reconstruction project. Given a robot with a pair of cameras and a set of figurines, the objective is getting the 3D position of some points of the real world, possibly making the robot capable of interacting with it.

## Scene
This project consists on the 3D reconstruction of the following scene:
<br/><br/>
<p align="center">
<img src="https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/scene.png" alt="Scene" width="80%">
</p>
<br/><br/>
With the robot on the bottom part of the image, which has a couple of cameras in a canonical form, meaning that they are aligned at a given distance. This is known cause it is given access to the calibration matrixes of the cameras via command interface. There are two matrixes returned, the intrinsics matrix K, where we can find the values of the focal length in pixels and center of the image and the extrinsic matrixes RT, where we can find the position and orientation of the cameras. An example image retrieved with the camera pair is the following one:
<br/><br/>
<p align="center">
<img src="https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/imgs.png" alt="Scene" width="80%">
</p>
<br/><br/>

<p align="center">
<a href="https://jderobot.github.io/">
<img alt="JdeRobot" src="https://avatars1.githubusercontent.com/u/10959337?s=200&v=4" width="15%">
</a>
</p>