#**Canny Edge Detection **

## **Overview**

Canny edge detector is a popular image processing technique used to detect edges in digital images. It was developed by John Canny in 1986 and is still widely used in computer vision applications. The algorithm works by finding the edges of an image based on their local intensity gradients, and then applying a series of thresholding and filtering steps to produce a binary image with strong edge pixels. 
In this project, we explore the Canny edge detector algorithm in detail, implement it in Python, and apply it to various test images to analyze its output in different scenarios. 


## **Project Methodology**

### 1. Gaussian Smoothing

Gaussian smoothing using a predefined 7 × 7 Gaussian mask was used to reduce noise and to blur images. The mask was applied to each pixel of the image using a nested loop that performed a convolution operation to calculate its smoothed value. The center of the mask was used as the reference center. For parts of the Gaussian mask going outside of the image border, the output image was undefined (undefined values were replaced with 0 in the output image). The resulting value after the convolution operation was stored in the ’smooth image’ array at the corresponding pixel position. Normalization was then performed by dividing the results of the ‘smooth image’ array by the sum of the entries (= 140 for the given mask) at each pixel location. The resulting normalized ’smooth image’ array was returned as the output of the function.


### Gradient Operation:
For gradient operation, predefined masks were used to compute gradients at 0, 45, 90 and 135 degree. The output value was undefined if part of the 3 × 3 mask goes outside of the image border or lies in the undefined region of the image after Gaussian filtering. The gradient magnitude value responses from all four masks after convolution was compared and the maximum of the absolute values of the responses was stored in the max arr. Max arr was then divided by 4 to return the normalized edge magnitude array. The indices of the maximum value for each map are recorded and used to determine the gradient angle of the edges at each pixel position. Thus, the output of the function is the normalized edge magnitude array and the gradient angle array.
### Non-Maxima Suppression:
Non-maxima suppression is used to suppress non-maximum values in a gradient image and re- tain only the local maximum values, which correspond to edges or other significant image features. In the function, the gradient angles are quantized into four sectors and stored in the sector array. The gradient magnitudes in the gradient magnitude array are compared according to the sector array and non-maximum values are suppressed retaining only gradient maximas. The resulting array of suppressed values is returned as nms, along with an array of all gradient magnitudes after nms excluding 0 values for later percentile calculation.
### Thresholding:
Thresholding is then used to convert this NMS image into a binary image by setting a thresh- old value above which a pixel is considered an edge pixel, and below which it is not. In our code, three different threshold values are calculated based on the 25𝑡h, 50𝑡h, and 75𝑡h percentiles of the gradient magnitude image after nms excluding 0 values. The function loops through each pixel of nms array and checks if the value of the pixel is greater than or equal to each of the three thresholds. If it is, the corresponding pixel in the appropriate threshold image is set to 255 (white), indicating that it is an edge pixel. If it is not, the pixel is set to 0 (black), indicating that it is not an edge pixel. The function returns three thresholded images, each with edge pixels set based on a different percentile threshold.
