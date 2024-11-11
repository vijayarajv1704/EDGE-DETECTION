# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.
## Program:
```
import cv2
import matplotlib.pyplot as plt
```
```
image = cv2.imread('crew.jpeg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
```
plt.imshow(cv2.cvtColor(gray_image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/a75a045e-ded8-40cb-b90e-6df2191b1cb9)

```
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
```
```
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/71a3ea27-3e25-46f2-b5b8-437a9ec0bb5c)

```
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
```
```
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/eb011f0e-5454-44da-91c7-ddd3dccbefbd)

```
canny_edges = cv2.Canny(gray_image, 50, 150)
```
```
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
plt.show()
```
![image](https://github.com/user-attachments/assets/7a997d09-a7d6-4699-bd3b-15fd72fc89fe)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
