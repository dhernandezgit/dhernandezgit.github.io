---
layout: post
title: Finding the key
tags: Reconstruction
thumbnail: https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/canny.png
---
In this post is treated the first step for the reconstruction, considering different options to get a set of points to reconstruct.

## Keypoints
The selection of the points for the reconstruction is the key to get a solid mesh of points, easily findable by the matching algorithm and speeding up the process of the reconstruction.

Among the several methods considered for the point selection are:
- Edge filters: Edge filtering is the easiest way to obtain a reduced set of points with enough variance to find them on a correspondent image. Some of the most known edge filters are Sobel, Robers or Canny (shown below).
- Lines or corners: Some methods employ only corner points easily findable, like the Harris detector.
- Feature selection: Some algorithm like SIFT or SURF use features to find special points easily distinguished.
- EVERY POINT!: This is the last option, viable when we want a dense reconstruction of the scene, but considerably slower than the others. 
<br/><br/>
<p align="center">
<img src="https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/canny.png" alt="Scene" width="80%">
</p>
<br/><br/>

<p align="center">
<a href="https://jderobot.github.io/">
<img alt="JdeRobot" src="https://avatars1.githubusercontent.com/u/10959337?s=200&v=4" width="15%">
</a>
</p>