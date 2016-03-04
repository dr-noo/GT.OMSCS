04-05 Features
==============

Objectives
----------
1. Benefits of Feature Detection and Matching in Images
2. Characteristics of Good Features
3. Corners and Good Features
4. Harris Corner Detector Algorithm
5. Stages of a SIFT detector

Image Matching
--------------
- Translation (change in x and y)
- Rotation (change in x, y, and rotation angle; 3 degree of freedom)
- Scale (4 parameters {x, y, theta, scale} variations)
- affine 
- perspective

Finding Features
----------------
Goals - Find points in an image that can be 
 - found in other images
 - found precisely - well localized
 - found reliably - well matched

Characteristics of Good Features
--------------------------------
- Repeatability/Precision
- Saliency/Matchability
- Compactness and Efficiency
- Locality

Find Corders
------------
- Key property: In the region around a corner, image gradient has two or more dominant directions
- Corners are repeatable and distinctive

Corner Detection: The Basics
----------------------------
"flat" : No change in any direction
"edge" : No change along the edge direction
"corner" : Change in all direction
- Recognize a point by looking through a small window
- Shifting a window in any direction causes a large change in intensity

Corner Detection: Mathematics
-----------------------------
Compute the change in appearance by shifting the window by u,v:
E(u,v) = sum_{x,y}_{w(x,y)[I(x+u,y+v) - I(x,y)]^2
