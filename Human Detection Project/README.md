# **Human Detection Project using HOG Features and 3NN classifier:**

## **Overview**

The objective of this project is to develop a program that can accurately detect the presence of humans in images using the HOG feature and a 3-NN classifier. The program will convert color images into grayscale, compute the horizontal and vertical gradients using Sobel’s operator, and quantize the gradient angle into 9 bins. The resulting HOG feature vector will be classified as human or no-human using the histogram intersection and Hellinger distance metrics. The classification accuracy for each distance metric will be reported. The program will be implemented in Python.

## **Dataset:**

The dataset consists of 10 human images and 10 non-human images which are inputs. Additionally, there 10 test images on which our algorithms and classifier would be tested on for accuracy. 

## **Methodology:**

The HOG feature vector for each of the input image - 10 human images and 10 non-human images are computed. The test image's HOG feature is compared with the input images' feature vector using distance measurement ( Histogram intersection and Hellinger distance ). The class of the 3 nearest neighbours is finally chosen and reported.

<img width="752" alt="image" src="https://github.com/Santoshsrini/CV-NYU/assets/28926309/065e7c74-6182-4894-80ca-110d19b447f0">

## **Results:**

The results for the test images classification as human or not a human is reported using the histogram intersection distance or hellinger distance computation. 

<img width="589" alt="image" src="https://github.com/Santoshsrini/CV-NYU/assets/28926309/af3deff0-15b2-4551-ad5c-5249448e6498">

<img width="573" alt="image" src="https://github.com/Santoshsrini/CV-NYU/assets/28926309/9e00cec6-c37b-4638-bc47-45a2f4c85f09">
