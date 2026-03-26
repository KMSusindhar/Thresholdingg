# THRESHOLDING
## Aim

## Developed By: SUSINDHAR K M
## Reg No.: 212223040218
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

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

## Program

```
import cv2
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image=cv2.imread('redfort.jpg')
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)

# Original image

plt.subplot(2,2,1)
plt.imshow(cv2.cvtColor(image,cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')

# Use Global thresholding to segment the image

_,global_thresholded = cv2.threshold(gray_img, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_img, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 

_,otsu_thresholded = cv2.threshold(gray_img, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()

```
## Output

### Original Image
<img width="363" height="463" alt="image" src="https://github.com/user-attachments/assets/1ff9beee-6f21-4455-a74a-76550a83b30c" />


### Global Thresholding
<img width="341" height="458" alt="image" src="https://github.com/user-attachments/assets/24098e55-bfb5-4231-bed6-00f1e0bcbd6c" />

### Otsu's Thresholding.
<img width="403" height="480" alt="image" src="https://github.com/user-attachments/assets/ce779481-3a06-4718-8b7f-6187beb150c1" />

### Adaptive Thresholding
<img width="353" height="481" alt="image" src="https://github.com/user-attachments/assets/a05c39b4-5077-43e3-9169-bd005d1d16b8" />


### Optimum Global Thesholding using Otsu's Method
<img width="356" height="492" alt="image" src="https://github.com/user-attachments/assets/578339b8-5589-491f-878f-c28e8f7d10a4" />



## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
