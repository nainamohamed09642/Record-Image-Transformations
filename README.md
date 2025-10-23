# Record-Image-Transformations

# Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

# Software Required:
Anaconda - Python 3.7

# Algorithm:
Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis. 2.Scaling resizes the image by scaling factors. 3.Shearing distorts the image along one axis. 4.Reflection flips the image horizontally or vertically. 5.Rotation rotates the image by a given angle.

Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

# Program:
```
#Developed By: NAINA MOHAMED Z
#Register Number:21222330131

#i)Image Translation
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('a.jpg')
# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('off') 
tx, ty = 100, 50  
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))  
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  
plt.title("Translated Image")  
plt.axis('off')

#ii) Image Scaling
fx, fy = 5.0, 2.0  
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('off')

#iii)Image shearing
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('off')

#iv)Image Reflection
reflected_image = cv2.flip(image, 2)  
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('off')

#v)Image Rotation
(height, width) = image.shape[:2] 
center = (width // 2, height // 2) 
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  
rotated_image = cv2.warpAffine(image, M_rotation, (width, height)) 
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('off')

#vi)Image Cropping
x, y, w, h = 100, 100, 200, 150  
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('off')
```
## OUTPUT
ORIGINAL IMAGE
<img width="560" height="396" alt="download" src="https://github.com/user-attachments/assets/47953eaa-3918-401c-87af-2ea1da3e39f6" />


TRANSLATED IMAGE
<img width="560" height="336" alt="download" src="https://github.com/user-attachments/assets/c512ab50-d903-424c-827b-29aaa817e2a4" />

SCALED IMAGE
<img width="560" height="231" alt="download" src="https://github.com/user-attachments/assets/d6560ec3-674c-43e2-a103-e1b7b23ec830" />

SHAERED IMAGE
<img width="560" height="231" alt="download" src="https://github.com/user-attachments/assets/2bd099e8-4ba7-46af-adf5-56cd923b8be0" />

ROTATED IMAGE


<img width="515" height="372" alt="download" src="https://github.com/user-attachments/assets/59de3eef-4f21-42fa-a5f7-326507b0014b" />



CROPED IMAGE

<img width="989" height="370" alt="download" src="https://github.com/user-attachments/assets/5f6d01fe-35d0-4c7e-9aca-8596fa535e01" />


## Result:
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
