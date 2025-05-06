# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages
<br>

### Step2:
Read the Image and convert to grayscale.
<br>

### Step3:
Use Global thresholding to segment the image.
<br>

### Step4:
Use Adaptive thresholding to segment the image.
<br>

### Step5:
Use Otsu's method to segment the image and display the results.
<br>

## Program

```python
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread('cheetah.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('cheetah.jpg',0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)",
"Threshold Image (To Zero)","Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)",
"Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
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
## Output

### Original Image
![image](https://github.com/user-attachments/assets/5274b7e0-bcc0-486d-aba6-a0a33b5e9e3b)

<br>

### Global Thresholding
![image](https://github.com/user-attachments/assets/7391bacc-0679-405a-a519-0e9c5524a6c2)
![image](https://github.com/user-attachments/assets/405b2ccb-c0b9-43fa-9d25-f0671576dfd1)
![image](https://github.com/user-attachments/assets/44062623-bb52-41a5-9e8d-228cbff7fe52)
![image](https://github.com/user-attachments/assets/a3d67458-7243-46b1-aa36-c5f7ffbb159e)
![image](https://github.com/user-attachments/assets/dd6af5b2-9ad3-4560-ad32-e9b71aa05e01)
![Screenshot 2025-05-06 094028](https://github.com/user-attachments/assets/631f6285-d4dc-464e-9369-7c7f0d202000)

<br>

### Adaptive Thresholding
![image](https://github.com/user-attachments/assets/7fab20df-1e0b-40d1-92d2-1e960741c3e1)

![image](https://github.com/user-attachments/assets/7e0ed935-9c37-4742-94f0-3524cf01b898)

<br>

### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/user-attachments/assets/225753a8-8abf-4342-92ef-d5eec168f855)

<br>


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
