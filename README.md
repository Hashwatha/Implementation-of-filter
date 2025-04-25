# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.

### Step2
Convert the image from BGR to RGB.

### Step3
Apply the required filters for the image separately. 

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.

## Program:
### Developed By   : Hashwatha M
### Register Number: 212223240051

### 1. Smoothing Filters

i) Using Averaging Filter
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("taj.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/476ff00f-151b-4115-852d-61febe4e63e3)

ii) Using Weighted Averaging Filter
```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/35ae77c6-f3b8-429f-ba8f-c5a680909ced)

iii) Using Gaussian Filter
```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/de088f86-3494-4069-a22a-28b6b6f41089)

iv)Using Median Filter
```
median = cv2.medianBlur(image2, 13)
plt.imshow(cv2.cvtColor(median, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct color display
plt.title("Median Blur")
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/053de2b5-b1ee-4572-8b58-8f2c41c66e29)

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/fb1280f8-8459-4a49-bcf4-6f6afec8a9ad)

ii) Using Laplacian Operator
```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()

```
![image](https://github.com/user-attachments/assets/4081aa2e-a24d-4654-bfd4-e5cc40e59dcc)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
