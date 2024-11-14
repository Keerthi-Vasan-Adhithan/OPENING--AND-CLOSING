# Exp - 10
# OPENING--AND-CLOSING
## Name: KEERTHI VASAN A
## Reg No: 212222240048
## Date:
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Give the input text using cv2.putText()
<br>

### Step3:
Perform opening operation and display the result
<br>

### Step4:
Similarly, perform closing operation and display the result
<br>


 
## Program:

``` Python

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Create a blank image
image = np.zeros((300, 600, 3), dtype="uint8")

# Step 2: Create the text using cv2.putText
text = "PRANAV"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)

# Step 3: Create a structuring element (5x5 rectangular)
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))

# Step 4: Use Opening operation (erosion followed by dilation)
opening_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)

# Step 5: Use Closing operation (dilation followed by erosion)
closing_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)

# Convert images from BGR to RGB for Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
opening_image_rgb = cv2.cvtColor(opening_image, cv2.COLOR_BGR2RGB)
closing_image_rgb = cv2.cvtColor(closing_image, cv2.COLOR_BGR2RGB)

# Plot the original, opening, and closing images using Matplotlib
plt.figure(figsize=(10, 5))

plt.subplot(1, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(opening_image_rgb)
plt.title("Opening Operation")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(closing_image_rgb)
plt.title("Closing Operation")
plt.axis("off")

plt.tight_layout()
plt.show()


     



```
## Output:

### Display the input Image
![image](https://github.com/user-attachments/assets/f94facc2-0fb9-492e-81fb-f1be97ffe0fe)


<br>
<br>
<br>
<br>
<br>
<br>

### Display the result of Opening
![image](https://github.com/user-attachments/assets/770126ff-fc15-4789-9e35-ece5ad0489e1)


<br>
<br>
<br>
<br>
<br>
<br>

### Display the result of Closing
![image](https://github.com/user-attachments/assets/4aabc1ec-8e67-49cf-a650-387404a4bf0a)


<br>
<br>
<br>
<br>
<br>
<br>

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
