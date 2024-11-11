# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program


### Load the necessary packages.
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
### Read the Image and convert to grayscale.
```
# Read the image
image = cv2.imread('waterfallnature.jpg')

# Convert to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Display the original grayscale image
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.xticks([]), plt.yticks([])
plt.show()
```
![image](https://github.com/user-attachments/assets/28f7c87c-ab15-4ede-b2cb-b17a83bbfb47)

# Use Global thresholding to segment the image
```
# Global thresholding
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Display the global thresholding result
plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()
```
![image](https://github.com/user-attachments/assets/ecca8e06-52c9-406d-9169-b7c06e5c4a0b)




# Use Adaptive thresholding to segment the image
```
# Adaptive thresholding (Gaussian)
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
                                    cv2.THRESH_BINARY, 11, 2)

# Display the adaptive thresholding result
plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()
```
![image](https://github.com/user-attachments/assets/90590795-87b2-469c-936b-6b9268fc6bd1)




# Use Otsu's method to segment the image 
```
# Otsu's thresholding
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Display the Otsu thresholding result
plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()

```
![image](https://github.com/user-attachments/assets/265fcfa0-cb17-4910-8fb7-e0946bebd11e)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
