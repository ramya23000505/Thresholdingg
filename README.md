# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
<br>
Load the necessary packages.

### Step2:
<br>
Read the Image and convert to grayscale.

### Step3:
<br>
Use Global thresholding to segment the image.

### Step4:
<br>
Use Adaptive thresholding to segment the image.

### Step5:
<br>
Use Otsu's method to segment the image and display the results.

### Program
```
Developed By : NIVETHA.K
Register Number : 212222230102
```

### Load the necessary packages:
```PY
import numpy as np
import matplotlib.pyplot as plt
import cv2
```

# Read the Image and convert to grayscale
```PY
image = cv2.imread('girl.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('girl.jpg',0)
```
# Use Global thresholding to segment the image
```PY
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
# Use Adaptive thresholding to segment the image
```PY
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
# Use Otsu's method to segment the image 
```PY
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
# Display the results
```PY
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
## Output

### Original Image
![Screenshot 2024-10-01 194110](https://github.com/user-attachments/assets/29fe3aea-1dd2-4315-893a-6dbe6632251c)

### Global Thresholding
![Screenshot 2024-10-01 194123](https://github.com/user-attachments/assets/19142558-7dce-4098-b394-861ff30af57b)

![Screenshot 2024-10-01 194134](https://github.com/user-attachments/assets/7771861c-09a1-4780-bd69-3cf11ce0cd3c)

![Screenshot 2024-10-01 194141](https://github.com/user-attachments/assets/50b3a7f3-cf3f-441b-aacc-5072e0b703d6)

![Screenshot 2024-10-01 194149](https://github.com/user-attachments/assets/1e9e63f8-2c00-4b65-aad4-93ae176c7b66)

![Screenshot 2024-10-01 194156](https://github.com/user-attachments/assets/2078fcd1-9fe0-4a38-bc4c-2094a8548fc0)

### Adaptive Thresholding
![Screenshot 2024-10-01 194205](https://github.com/user-attachments/assets/00660be0-7a3a-4059-9b85-be81415e1430)

![Screenshot 2024-10-01 194212](https://github.com/user-attachments/assets/3fc83ba7-f99f-423c-beaf-a2f463372133)

### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-10-01 194221](https://github.com/user-attachments/assets/a0a6ef58-8cad-4e3b-a63b-40fcaedcd6cc)



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
