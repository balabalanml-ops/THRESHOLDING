# *EXP - 8 - THRESHOLDING:*

## AIM:

To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:

1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step1:
Load the necessary packages

### Step2:
Read the Image and convert to grayscale
### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## PROGRAM :

## DEVELOPED : BY : SRIBALAKUMARAN  R
## REG : NO : 212225220104

## CODE:

### Original Image:

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

```
image = cv2.imread('bala.jpeg')  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  
```

```
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Original Image")
plt.axis('off')
```

## OUTPUT:

<img width="462" height="298" alt="image" src="https://github.com/user-attachments/assets/f9bcf750-6223-4d40-9e32-ddf8bf55fef1" />


### Global Thresholding with a Threshold value of 127:

```
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
```

### Adaptive Thresholding Using Gaussian Method:

```
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
```

### Otsu's method for Optimal Thresholding:

```
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
```

### Original Image:

```
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Original Image")
plt.axis('off')
```

### Global Thresholding:

```
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
```

### Adaptive Thresholding:

```
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
```

### Otsu's Method:

```
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
```

### Show the plot:

```
plt.tight_layout()
plt.show()
```

## OUTPUT:
<img width="1175" height="762" alt="image" src="https://github.com/user-attachments/assets/2d5753eb-9e3c-4bd7-82ba-abb631ad4d9f" />


## Result:

Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
