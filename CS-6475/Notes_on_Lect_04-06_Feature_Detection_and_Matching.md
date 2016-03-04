04-06 Feature Detection and Matching
====================================

Objectives
----------
- Harris Corner Detection Algorithm
- SIFT

Harris Corner Detection Algorithm
---------------------------------
1. Compute horizonal and vertical derivatives of the image (convolve with derivative of Gaussians)
2. Compute outer products of gradients M
3. Convolve with larger Gaussian
4. Compute scalar interest measure R
5. Find local maxima above some threshold, detect features!

Harris Corner: Some Properties
------------------------------
- Invariant to Rotation
 - Ellipse rotates but its shape (i.e., eigenvalues) remains the same.
 - Corner response R is invariant to image rotation.
- Invariant to Image Intensity
 - Mostly invarian to additive and multiplicative intensity changes
 - Only derivatives are used
 - I -> I + b (Invariance to intensity shift)
 - I -> aI (Intensity scale)
- Invariant to Image Scale
 - No

Scale Invariant Detection
-------------------------
- A "good" function for scale detection has one stable sharp peak
- Key Point Localization in Space
 - Find robust extremum (maximum and minimum) both in space and in scale
 - Use pyramid to find maximum values, then eliminate "edges" and pick only corners.

Scale Invariant Detectors
-------------------------
- Harris-Laplacian
- Find local maximum of 
 - Harris corner detector in space (image coordinates)
 - Laplacian in scale

- SIFT (Lowe, 2004)
 - Find local maximum of
  1. Difference of Gaussian (DoG) in space and scale
  2. DoG is simply a pyramid of the difference of Gaussans with each octave.
 - Advantage: Image content is transformed into local feature coordinates that are invariant to translation, rotation, scale, and other imaging parameters.
