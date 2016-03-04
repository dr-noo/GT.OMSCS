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
- I(x,y): Intensity Function
- I(x+u,y+v): Shifted Intensity Function
- w(x,y): Window Function
- E(u,v): Change in Appearance
The quadratic approximation, following Taylor Expanson, simplifies to:
E(u,v) ~ [u v] M [u v]^T
where M is a second moment matrix computed from image derivaties I_x and I_y
- The surface E(u,v) is locally approximated by a quadratic form.

Harris Detector Algorithm (Preview)
-----------------------------------
- Compute Gaussian derivatives at each pixel
- Compute second moment matrix M in a Gaussian window around each pixel.
- Compute corner response function R
- Threshold R
- Fund local maxima of response function (non-maximum suppression)

Properties of the Harris Detector
---------------------------------
- Rotation Invariant
 - Ellipse rotate but shape (eigen values) remain same
 - Corner response R is invariant

- Intensity Invariant
 - Partial invariance to additive and multiplicative intensity changes (threshold issue for multiplicative)
 - only image derivatives are used

Scale Invariant Detectors
-------------------------
### Harris-Laplacian
- Find local maximum of 
 - Harris corner detector in space (image coordinates)
 - Laplacian in scale

### SIFT (Lowe, 2004)
- Find local maximum of
 - Difference of Gaussians (DoG) in space and scale
 - DoG is simply a pyramid of the difference of Gaussians with each octave.

SIFT (Scale-Invariant Feature Transform)
----------------------------------------
- Orientation assignment
 - Compute best orientation(s) for each keypoint region
- Keypoint description
 - Use local image gradients at selected scale and rotation to describe each keypoint region.

