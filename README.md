# EX 08 THRESHOLDING
## DATE:
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

## PROGRAM
### Developed By : Kancharla Narmadha
### Register Number : 212222110016


### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

### Read the Image and convert to grayscale
```
image = cv2.imread('rain.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('rain.jpg',0)

```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## OUTPUT

### Original Image
![Untitled](https://github.com/kancharlaNarmadha/Thresholdingg/assets/119559316/8d418751-96c8-41fa-84c8-e4138a96c193)


### Global Thresholding
![Untitled](https://github.com/kancharlaNarmadha/Thresholdingg/assets/119559316/51bf4a67-21ca-4ead-bb3d-b97a83a58d76)

![Untitled](https://github.com/kancharlaNarmadha/Thresholdingg/assets/119559316/54f1502d-c71f-4f2f-9adb-7099b6ac33c3)
![Untitled](https://github.com/kancharlaNarmadha/Thresholdingg/assets/119559316/85c66366-8008-4980-981e-b7e7dd6341db)

![Untitled](https://github.com/kancharlaNarmadha/Thresholdingg/assets/119559316/dafdb5fc-e9d0-40e3-932b-20c3206752cd)
![Untitled](https://github.com/kancharlaNarmadha/Thresholdingg/assets/119559316/d42a647f-30d0-46bd-bb37-f3e9e2dc5dc1)


### Adaptive Thresholding
![Untitled](https://github.com/kancharlaNarmadha/Thresholdingg/assets/119559316/93dddaa4-0569-4d68-8f21-bcb5e315d74d)
![Untitled](https://github.com/kancharlaNarmadha/Thresholdingg/assets/119559316/48f0e679-637b-44b0-a850-a06859126629)




### Optimum Global Thesholding using Otsu's Method
![Untitled](https://github.com/kancharlaNarmadha/Thresholdingg/assets/119559316/b86d2d46-6472-4633-b0ca-f622c557e4a2)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
