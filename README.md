# IMAGE-TRANSFORMATIONS
### EXP : 4
### DATE : 16 / 9 /24

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Use OpenCV's cv2.imread() to load the image from a file.

### Step2:
Create a translation matrix using NumPy and apply it using cv2.warpAffine().

### Step3:
Use cv2.resize() to scale the image by the desired scaling factors.

### Step4:
For rotation and reflection, use cv2.getRotationMatrix2D() and cv2.warpAffine().

For shearing, create a shearing matrix and apply it using cv2.warpAffine().

### Step5:
Use NumPy array slicing to crop the image by selecting a region of interest.

## Program:

#### Developed By: MANOJ M
#### Register Number: 212221240027  
```python
i)Image Translation
import cv2
import numpy as np

# Load the image
image = cv2.imread('image.jpg')

# Define translation matrix: (shift along x, shift along y)
tx, ty = 100, 50
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])

# Apply translation
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display
cv2.imshow('Translated Image', translated_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

ii) Image Scaling
# Scaling factors
scale_x, scale_y = 1.5, 1.5

# Resize image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display
cv2.imshow('Scaled Image', scaled_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

iii)Image shearing
# Define shearing matrix
shear_factor = 0.5
shearing_matrix = np.float32([[1, shear_factor, 0], [0, 1, 0]])

# Apply shearing
sheared_image = cv2.warpAffine(image, shearing_matrix, (int(image.shape[1] * 1.5), image.shape[0]))

# Display
cv2.imshow('Sheared Image', sheared_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

iv)Image Reflection
 Reflection_Image= cv2.flip(image, 1)

# Display
cv2.imshow('Reflection Image', Reflection_Image)
cv2.waitKey(0)
cv2.destroyAllWindows()

v)Image Rotation
# Rotation center, angle and scale
center = (image.shape[1] // 2, image.shape[0] // 2)
angle, scale = 45, 1.0

# Get rotation matrix
rotation_matrix = cv2.getRotationMatrix2D(center, angle, scale)

# Apply rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (image.shape[1], image.shape[0]))

# Display
cv2.imshow('Rotated Image', rotated_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

vi)Image Cropping
# Define the region of interest (ROI)
x, y, w, h = 100, 100, 300, 300
cropped_image = image[y:y+h, x:x+w]

# Display
cv2.imshow('Cropped Image', cropped_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output:
![Screenshot 2024-09-26 161850](https://github.com/user-attachments/assets/be0d0a8e-d338-4f6f-83de-f414c2d284f6)


## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
