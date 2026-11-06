# DIPT-Ex-4

# Geometric-Transformations-Using-OpenCV-4

---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---

##  Program

### Developed By:
**Name:**: Nishma sherin .K

### Register No: 212224240104

ORIGINAL IMAGE:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('temple.png')
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Original Image")  
plt.axis('off') 
```
TRANSLATED IMAGE:
```
tx, ty = 100, 50 
M_translation = np.float32([[1, 0, tx], [0, 1, ty]]) 
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  
plt.title("Translated Image")  
plt.axis('off')
```
SCALED IMAGE:
```
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB)) 
plt.title("Scaled Image") 
plt.axis('off')
```
SHEARED IMAGE:
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) 
plt.title("Sheared Image") 
plt.axis('off')
```
REFLECTED IMAGE:
```
reflected_image = cv2.flip(image, 2) 
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB)) 
plt.title("Reflected Image") 
plt.axis('off')
```
ROTATED IMAGE:
```
(height, width) = image.shape[:2] 
angle = 45  
center = (width // 2, height // 2) 
M_rotation = cv2.getRotationMatrix2D(center, angle, 1) 
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  
plt.title("Rotated Image")  
plt.axis('off')
```
CROPPED IMAGE:
```
x, y, w, h = 100, 100, 200, 150
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image")  
plt.axis('off')
---

```
##  Output

### original image

<img width="431" height="277" alt="image" src="https://github.com/user-attachments/assets/437c7a09-2454-4a35-8dc5-f688d4b5f9de" />


### Image Translation

<img width="831" height="565" alt="image" src="https://github.com/user-attachments/assets/f21ffe6a-fbf8-4165-a0e2-8ba85a9e7e60" />



### Image Scaling

<img width="783" height="255" alt="image" src="https://github.com/user-attachments/assets/d1614880-e2e4-4b6c-9743-70a053987134" />


### Image Shearing

<img width="838" height="559" alt="image" src="https://github.com/user-attachments/assets/98833186-beb9-4e10-b652-057953218b19" />




### Image Reflection

<img width="790" height="562" alt="image" src="https://github.com/user-attachments/assets/ada16b2e-2b98-473e-b8ba-a346fbf79f9f" />



### Image Rotation

<img width="906" height="541" alt="image" src="https://github.com/user-attachments/assets/5d4b5c32-ad5f-45a6-9726-aa9a06ea7a26" />


### cropped image

<img width="802" height="609" alt="image" src="https://github.com/user-attachments/assets/9d0cf486-80a6-4ee6-ae16-25ab7fc211e0" />


---

##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
