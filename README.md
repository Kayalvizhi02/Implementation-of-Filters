### EX NO: 06
### DATE:
# <p align="center">Implementation of Filters</p>
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

### Step 1:

Import the necessary modules.

### Step 2:

- Average filter
```python
kernel=np.ones((11,11),np.float32)/121
image3=cv2.filter2D(image2,-1,kernel)
```
- Weighted average filter
```python

kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)

```
- Gaussian Blur
```python

gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)

```
- Median filter
```python

median=cv2.medianBlur(image2,13)

```
### Step 3:

For performing sharpening on a image.

- Laplacian Kernel
 ```python
 
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)

```
- Laplacian Operator
```python

laplacian=cv2.Laplacian(image2,cv2.CV_64F)

```
### Step 4:

Display all the images with their respective filters.

## Program:
```
Developed By   : KAYALVIZHI M
Register Number: 212220230024
```
```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("once.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
```
### 1. Smoothing Filters

i) Using Averaging Filter
```Python

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
ii) Using Weighted Averaging Filter
```Python

kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()

```
iii) Using Gaussian Filter
```Python

gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

```

iv) Using Median Filter
```Python

median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()

```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python

kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

```
ii) Using Laplacian Operator
```Python

laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()

```

## OUTPUT:
### 1. Smoothing Filters
i) Using Averaging Filter

![img](https://user-images.githubusercontent.com/75413726/167181267-0dc4d9be-f76f-4913-a782-4a1376ac3f91.jpg)

ii) Using Weighted Averaging Filter

![img1](https://user-images.githubusercontent.com/75413726/167181324-8a11e3d0-b6e0-4836-8bb8-101e4c60f47a.jpg)

iii) Using Weighted Averaging Filter

![img2](https://user-images.githubusercontent.com/75413726/167181362-b7733cd7-54c1-44ed-b758-e3f7e5a4bf9a.jpg)

iv) Using Median Filter

![img3](https://user-images.githubusercontent.com/75413726/167181420-05959387-8241-4e7c-a282-34aa28248474.jpg)

### 2. Sharpening Filters
i) Using Laplacian Kernal

![img4](https://user-images.githubusercontent.com/75413726/167181465-9c3a30a9-3997-4cb8-8085-38cb6f4f4991.jpg)

ii) Using Laplacian Operator

![img5](https://user-images.githubusercontent.com/75413726/167181499-5f411202-467b-440a-8542-9caaebd6fb79.jpg)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
