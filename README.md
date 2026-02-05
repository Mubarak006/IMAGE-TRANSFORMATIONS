# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.



## Program:

Developed By: MUBARAK R
Register Number: 212224220066


## i)Original image

```
import cv2
import numpy as np
import matplotlib.pyplot as plt

```
```
image=cv2.imread("imagesss.jpg")
image.shape

```
(168, 300, 3)

```
#Display the images:
plt.imshow(image[:,:,::-1])
plt.title("Original Image")
plt.show()

```


## ii)Image Translation

```
# Image Translation:
tx,ty=100,200
M_translation=np.float32([[1,0,tx],[0,1,ty]])
translated_image=cv2.warpAffine(image,M_translation, (673,419))

```
```
plt.imshow(translated_image[:,:,::-1])
plt.title("Translated Image")
plt.axis("on")
plt.show()

```

## iii) Image Scaling

```
#scaled image
fx, fy = 5.0, 2.0 
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  
plt.title("Scaled Image")  
plt.axis('off')

```

## iv)Image shearing

```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) 
plt.title("Sheared Image") 
plt.axis('off')

```
## v)Image Reflection

```
#Reflected image
reflected_image = cv2.flip(image, 2)  
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  
plt.title("Reflected Image") 
plt.axis('off')

```

## vi)Image Rotation

```
# Rotated Image
(height, width) = image.shape[:2] 
angle = 60 
center = (width // 2, height // 2) 
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB)) 
plt.title("Rotated Image") 
plt.axis('off')

```

## vii)Image Cropping

```
# cropped image
x, y, w, h = 100, 100, 200, 150  
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) 
plt.title("Cropped Image") 
plt.axis('off')

```


## Output:

## i)Original image

<img width="671" height="401" alt="image" src="https://github.com/user-attachments/assets/0e7c7589-24b2-4f08-bf31-b1986cfdcf33" />

## ii)Image Translation

<img width="670" height="420" alt="image" src="https://github.com/user-attachments/assets/2dfd416c-779a-4a2b-9166-e96d1ffa6f64" />

## iii) Image Scaling

<img width="580" height="171" alt="image" src="https://github.com/user-attachments/assets/7e7029fe-584f-4d14-ab65-89e9598bf577" />

## iv)Image shearing

<img width="587" height="358" alt="image" src="https://github.com/user-attachments/assets/8dddecc4-1838-42fe-a116-ce2852261769" />

## v)Image Reflection

<img width="590" height="356" alt="image" src="https://github.com/user-attachments/assets/a09e0f23-c13e-4789-93eb-998f50d7cd08" />

## vi)Image Rotation

<img width="588" height="365" alt="image" src="https://github.com/user-attachments/assets/f87ff581-97be-414a-b0a0-8db9a693b26e" />

## vii)Image Cropping

<img width="595" height="239" alt="image" src="https://github.com/user-attachments/assets/75ffe54e-7b34-4268-b169-e755d466b57c" />

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
