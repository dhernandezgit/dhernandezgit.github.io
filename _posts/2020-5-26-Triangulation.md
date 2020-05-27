---
layout: post
title: Triangulation
tags: Reconstruction
thumbnail: https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/final3d.png
---
This post treats the reconstruction of the matching points and the results of this process.

## Triangulation
Once the correspondent points are known, it's possible to reconstruct the 3D model. The fast way is using the OpenCV function triangulatePoints over the points with a low disparity value. Disparity is the difference on coordinates between the left point and the correspondent point.

Another possible method is using the equations of the points, where f is the focal distance, B is the baseline or distance between cameras, d is the disparity and u and v are the coordinates of the point referred to the center of the image:
> Z = f * B / d

> X = u * Z / f

> Y = v * Z / f

The results of this method are shown in the following sequence, where all the points are considered and it is reconstructed in row order: 
<br/><br/>
<p align="center">
<img src="https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/1.png" alt="Scene" width="80%">
</p>
<br/><br/>
<br/><br/>
<p align="center">
<img src="https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/2.png" alt="Scene" width="80%">
</p>
<br/><br/>
<br/><br/>
<p align="center">
<img src="https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/3.png" alt="Scene" width="80%">
</p>
<br/><br/>

## Final result
The final result is the next one, which can be overlapped with a real image of the 3D scene, with a decent amount of correspondence, specially over the right blocks.
<br/><br/>
<p align="center">
<img src="https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/4.png" alt="Scene" width="80%">
</p>
<br/><br/>
<br/><br/>
<p align="center">
<img src="https://github.com/dhernandezgit/dhernandezgit.github.io/raw/master/images/final3d.png" alt="Scene" width="80%">
</p>
<br/><br/>
Thanks for reading!

<p align="center">
<a href="https://jderobot.github.io/">
<img alt="JdeRobot" src="https://avatars1.githubusercontent.com/u/10959337?s=200&v=4" width="15%">
</a>
</p>