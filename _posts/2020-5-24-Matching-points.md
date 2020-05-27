---
layout: post
title: Matching points
tags: Reconstruction
thumbnail: https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/match.png
---
This post talks about the current method used on point matching making use of OpenCV methods.

## Matching
Matching points means finding a homologous point of one of the stereo cameras on the other image. This can be done by looking for the patch on the entire image, but we can speed the process knowing some properties of a stereo pair.

The correspondent point won't appear anywhere on the analogous image, it can be found over the epipolar stripe. This is the line where all the possible depths of the left point are projected over the left camera. In a stereo pair, the epipolar lines are horizontal lines, so the search for the patch is only done over that line.

A patch of a preset size is created on the left image, and with the matchTemplate() function, that admits different metrics (SSD, SAD, ...) to find the patch is found on the patch of the right image correspondent with the epipolar constraint and a set margin.
<br/><br/>
<p align="center">
<img src="https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/match.png" alt="Scene" width="80%">
</p>
<br/><br/>


<p align="center">
<a href="https://jderobot.github.io/">
<img alt="JdeRobot" src="https://avatars1.githubusercontent.com/u/10959337?s=200&v=4" width="15%">
</a>
</p>