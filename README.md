# Stereo Vision for 3D Reconstruction

## Project Overview

This project implements stereo vision to achieve 3D reconstruction from two different camera angles. By comparing two images of the same scenario, we extract the relative positions of objects in 3D space. The project involves the calibration process to compute fundamental and essential matrices using correspondence points, image rectification, correspondence matching, and depth calculation.

## Table of Contents
- [Calibration](#calibration)
- [Rectification](#rectification)
- [Correspondence](#correspondence)
- [Depth Calculation](#depth-calculation)
- [Results](#results)
- [Dependencies](#dependencies)
- [Usage](#usage)
- [References](#references)

## Calibration

The calibration phase involves matching images using the SIFT algorithm and Brute-Force Matcher, extracting correspondences, and computing the fundamental matrix. This phase is critical for establishing a relationship between two camera perspectives and involves normalizing image points, estimating the camera pose, and finding the best point correspondences using RANSAC.

## Rectification

Rectification transforms the images to align them along their epipolar lines. This process involves image warping and homographic transformations to rectify the images and facilitate easier point correspondence.

## Correspondence

Correspondence involves searching along epipolar lines in the second image for matches to points in the first image. Block matching and the Sum of Absolute Differences (SAD) approach are used to compute disparity for the rectified image pair.

## Depth Calculation

Depth calculation is the final step where 3D information is extracted using camera parameters and disparity data. The depth for each set of images is fine-tuned for accuracy.



![Chess Dataset](images/chess_dataset.png)

![Ladder Dataset](images/ladder_dataset.png)

![Artroom Dataset](images/artroom_dataset.png)

![Chess Matched Image](images/chess_matched_image.png)

![Ladder Matched Image](images/ladder_matched_image.png)

![Artroom Matched Image](images/artroom_matched_image.png)

For more results, visit the `images/` directory.

## Dependencies

- Python 3.x
- OpenCV
- NumPy
- Matplotlib

## Usage

To run this project, clone the repository and install the dependencies listed above. The main scripts are `artroom.py`, `chess.py`, and `ladder.py`, corresponding to different datasets.

```bash
python artroom.py
python chess.py
python ladder.py
```

## References

For in-depth understanding and methodology refer to:
- [Fundamentals of Matrix Computations](https://cmsc733.github.io/2022/proj/p3/fundmatrix)


I'm unable to directly manage or modify files within your GitHub repository or attach images to the README file for you. However, I can guide you on how to link the images in your README markdown so that they will display properly when you upload the images to your GitHub repository.

Here's how you can link images in your README file:

1. Upload your images to your GitHub repository, ideally in an `images/` directory.
2. Reference these images in your README.md using relative links.

## Results

## Calibration

Here's an example image of feature matching for Artroom Dataset:

![Feature Matching](https://github.com/kalavagunta-vamshi/673-p4/blob/main/results/artroom/chess_matched_image.png)

## Rectification

This image shows the results of image rectification:

![Rectified Image](https://github.com/kalavagunta-vamshi/673-p4/blob/main/results/artroom/rectified_epi_polar_lines_.png)

## Correspondence

Here are the epipolar lines demonstrating correspondence:

![Epipolar Lines](https://github.com/kalavagunta-vamshi/673-p4/blob/main/results/artroom/epi_polar_lines_.png)

## Depth Calculation

The following images illustrate the depth calculation results:

Depth Image - Gray:
![Depth Image Gray](https://github.com/kalavagunta-vamshi/673-p4/blob/main/results/artroom/disparity_image_gray.png)

Depth Image - Heat Map:
![Depth Image Heat](https://github.com/kalavagunta-vamshi/673-p4/blob/main/results/artroom/depth_image_heat.png)

## Disparity

The following images illustrate the Disparity results:

Disparity Image - Gray:
![Disparity Image Gray](https://github.com/kalavagunta-vamshi/673-p4/blob/main/results/artroom/disparity_image_gray.png)

Disparity Image - Heat Map:
![Disparity Image Heat](https://github.com/kalavagunta-vamshi/673-p4/blob/main/results/artroom/disparity_image_heat.png)

