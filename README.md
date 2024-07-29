# Hyperspectral_Image_Analysis_Spectral_Unmixing_and_Classification
This project focuses on the processing and analysis of Hyperspectral Images (HSIs) using machine learning techniques. It covers spectral unmixing to decompose mixed pixels into pure materials and classification to categorize pixels into known classes, using the Salinas HSI dataset as a case study.

## Introduction

This project is dedicated to the processing and analysis of Hyperspectral Images (HSIs) using various machine learning and computational statistics methods. Hyperspectral images capture data across a spectrum of wavelengths, resulting in a three-dimensional cube of data: MxNxL, where M and N represent the spatial dimensions, and L represents the spectral dimension. Each pixel in the image corresponds to an L-dimensional vector, known as the spectral signature.

In remote sensing applications, HSIs are used to study the Earth's surface. Due to the spatial resolution of satellite sensors, each pixel often represents an area that may contain multiple materials, leading to mixed pixels. On the other hand, pure pixels represent areas with a single material. This project focuses on two primary processing tasks for HSIs: spectral unmixing and classification.

## Project Description

### Part 1: Spectral Unmixing

Spectral unmixing (SU) aims to decompose a pixel's spectral signature into contributions from several pure materials (endmembers). Given the spectral signatures of pure pixels, the objective is to determine the percentage (abundance) of each material present in a mixed pixel. Mathematically, this is expressed as:

$$ y = X\theta + \eta $$

Where:
- $y$ is the $L$-dimensional spectral signature of the pixel.
- $X$ is the matrix of spectral signatures of the pure pixels (endmembers).
- $\theta$ is the abundance vector representing the proportion of each material.
- $\eta$ is the noise vector.


**Tasks:**
1. Implement and compare the following spectral unmixing methods:
   - (a) **Least Squares (LS)**
   - (b) **Least Squares with Sum-to-One Constraint**
   - (c) **Least Squares with Non-negativity Constraint**
   - (d) **Least Squares with Non-negativity and Sum-to-One Constraints**
   - (e) **LASSO (L1 norm minimization)**

2. For each method:
   - (i) Generate abundance maps for each endmember.
   - (ii) Calculate the reconstruction error.

3. Compare and comment on the results using the class information from "Salinas_ground_truth.mat".

### Part 2: Classification

In this part, pixels are classified into one of the known classes based on their spectral signatures. Three classifiers are considered:
1. **Naïve Bayes Classifier**
2. **Minimum Euclidean Distance Classifier**
3. **K-Nearest Neighbors (K-NN) Classifier**

**Tasks:**
1. For each classifier:
   - (i) Train the classifier using 10-fold cross-validation and report the validation error and standard deviation.
   - (ii) Train the classifier on the full training set and evaluate it on a test set, compute the confusion matrix, and calculate the success rate.

## Data

The project utilizes the "Salinas" HSI, which depicts an area of the Salinas Valley in California, USA. The dataset includes:
- **Salinas_cube.mat**: Contains the spectral data.
- **Salinas_ground_truth.mat**: Contains the class labels for each pixel.

