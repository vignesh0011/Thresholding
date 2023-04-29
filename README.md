## EX.NO: 09 <br>
## DATE: 
## <p align="center">THRESHOLDING</p>

## AIM:
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## SOFTWARE REQUIRED:
1. Anaconda - Python 3.7
2. OpenCV

## ALGORITHM:

### Step 1:
Load the necessary packages.

### Step 2:
Read the Image and convert to grayscale.

### Step 3:
Use Global thresholding to segment the image.

### Step 4:
Use Adaptive thresholding to segment the image.

### Step 5:
Use Otsu's method to segment the image.

### Step 6:
Display the results.

## PROGRAM:
```
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("white.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("white.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_white1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_white2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_white3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_white4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_white5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Otsu's method to segment the image 
ret,thresh_white6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Use Adaptive thresholding to segment the image
thresh_white7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_white8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_white1,thresh_white2,thresh_white3,thresh_white4,thresh_white5,thresh_white6,thresh_white7,thresh_white8]
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
## OUTPUT:

### Original Image and Grayscale Image

![Screenshot (253)](https://user-images.githubusercontent.com/75235477/170210572-2e1e989f-1011-47fb-8382-0800db50402d.png)


### Global Thresholding

![Screenshot (245)](https://user-images.githubusercontent.com/75235477/170210691-e519391e-af17-4a6a-b47f-5f97f2161916.png)


![Screenshot (246)](https://user-images.githubusercontent.com/75235477/170210702-d782b693-6af9-498e-8682-d27859e3ade6.png)
![Screenshot (247)](https://user-images.githubusercontent.com/75235477/170210725-08dddc7f-0534-4105-84f8-7a509250df2b.png)
![Screenshot (249)](https://user-images.githubusercontent.com/75235477/170210830-84d352ce-0542-4938-bc91-96c4b7df38a5.png)


### Adaptive Thresholding

![Screenshot (250)](https://user-images.githubusercontent.com/75235477/170210856-36e329f4-cb05-4186-b005-8a6a2c12034c.png)
![Screenshot (251)](https://user-images.githubusercontent.com/75235477/170210866-e25aca31-8436-4232-9b58-0a415b70ee5e.png)
![Screenshot (252)](https://user-images.githubusercontent.com/75235477/170210886-89b3c188-3d1b-4d11-a32b-0204b6b65db1.png)


### Optimum Global Thesholding using Otsu's Method

![Screenshot (250)](https://user-images.githubusercontent.com/75235477/170210773-eafe015b-16ca-4d90-8715-ed0f8461f0f3.png)

## RESULT:
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.



