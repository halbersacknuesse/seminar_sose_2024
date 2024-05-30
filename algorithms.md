<!--
author:   Jonas Fleischer

email:    jonas.fleischer@student.tu-freiberg.de

version:  0.0.1

language: en

narrator: US English Female

comment: explenations of the mentioned algorithms for Seminar Robotik SoSe 2024, "Feature based pose estimation in dark environments" 

link:     https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.css

script:   https://cdn.jsdelivr.net/chartist.js/latest/chartist.min.js


script:   https://cdn.jsdelivr.net/npm/mermaid@10.5.0/dist/mermaid.min.js

logo: assets/logo.png
icon: assets/logo.png

@end

-->
# Mentioned Algorithms

1. [SIFT](#2)
2. [PPF](#3)
3. [SURF](#4)
4. [ORB](#5)
5. [AKAZE](#6)
6. [FAST](#7)


## SIFT

SIFT[^1], [^2] is an algorithm for recognizing and describing local features in images. The algorithm mainly consists of four steps:

- Scale-space peak selection: Potential locations for finding features are identified.
- Keypoint localization: The feature points are precisely localized.
- Orientation assignment: The keypoints are assigned an orientation.
- Keypoint descriptor: The feature points are described as a high-dimensional vector.

[^1]: https://medium.com/@deepanshut041/introduction-to-sift-scale-invariant-feature-transform-65d7f3a72d40

[^2]: https://en.wikipedia.org/wiki/Scale-invariant_feature_transform


## PPF

PPF[^3], [^4] is an algorithm for recognizing point pairs in 3D point clouds. The algorithm uses a method called Keypoint Pair Feature (K-PPF) voting to perform 6D pose estimation. The K-PPF method improves the point pair feature difference and matching accuracy. Given the 3D model of an object, the method starts by extracting 3D features that relate pairs of 3D points and their normals. These features are then quantized and stored in a hash table and used to represent the 3D model for recognition. During runtime, the same features are extracted from a downsampled version of a given scene. The hash table is then queried per extracted/quantized feature and a Hough-like voting is performed to accumulate the estimated pose and position.

[^3]: https://tolgabirdal.github.io/downloads/birdal-3dv-2015.pdf
[^4]: https://www.mdpi.com/1424-8220/22/16/6289

## SURF

SURF[^5], [^6] is a fast and robust algorithm for local, similarity-invariant representation and comparison of images. The algorithm uses box filters for fast computation of operators, which enables real-time applications such as tracking and object detection. The interest point detection approach uses a very basic Hessian matrix approximation. The integral images or summed area tables were introduced in 1984. The integral image is used as a fast and effective method for calculating the sum of values (pixel values) in a given image or a rectangular sub-area of a grid (of the given image). It can also or mainly be used to calculate the average intensity within a given image.

[^5]: https://www.youtube.com/watch?v=0sskOxN0sT0
[^6]: https://medium.com/@deepanshut041/introduction-to-surf-speeded-up-robust-features-c7396d6e7c4e

## ORB

ORB[^7], [^8] is a fusion of the FAST keypoint detector and the BRIEF descriptor with many modifications to improve performance. First, ORB uses FAST to find keypoints, then it applies the Harris corner measure to find the top N-points among them. It also uses a pyramid to generate multi-scale features. After ORB locates the keypoints, it assigns an orientation to each keypoint based on how the intensity levels change around that keypoint.

[^7]: https://medium.com/@deepanshut041/introduction-to-orb-oriented-fast-and-rotated-brief-4220e8ec40cf
[^8]: https://docs.opencv.org/3.4/d1/d89/tutorial_py_orb.html

## AKAZE

AKAZE[^9], [^10] is an improvement of the KAZE algorithm by using a mathematical framework called Fast Explicit Diffusion (FED) to create a non-linear scale space and by introducing a new descriptor called Modified Local Difference Binary (M-LDB) to reduce memory requirements.

[^9]: https://link.springer.com/content/pdf/10.1007/s11554-021-01089-9.pdf
[^10]: https://link.springer.com/article/10.1007/s11554-021-01089-9

## FAST

FAST[^11], [^12] is a corner detection algorithm that can be used to extract feature points. It recognizes the corners by applying a segment test to each pixel. It considers a circle of 16 pixels around the pixel to be tested. If more than 8 pixels are darker or lighter than p, then it is selected as a keypoint.

[^11]: https://medium.com/@deepanshut041/introduction-to-fast-features-from-accelerated-segment-test-4ed33dde6d65
[^12]: https://docs.opencv.org/3.4/df/d0c/tutorial_py_fast.html