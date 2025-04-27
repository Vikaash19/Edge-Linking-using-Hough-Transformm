# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('oph.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
plt.show()

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()

edges = cv2.Canny(gray_image, 50, 150) 
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
plt.show()

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
if lines is not None:  
    for line in lines:
        x1, y1, x2, y2 = line[0]
        cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')
plt.show()
```
## Output
### Input image
![input](https://github.com/user-attachments/assets/614644a9-010e-449c-8c9d-dacca7fd2e97)

### Grayscale image
![gray](https://github.com/user-attachments/assets/8761b877-f498-4e6f-a2d6-f1b95cd6c1ff)

### Canny Edge detector output
![canny](https://github.com/user-attachments/assets/cc6d690c-f0f7-44ba-842e-8b808aa5747b)

### Display the result of Hough transform
![hough](https://github.com/user-attachments/assets/f67c71fe-398b-4970-956d-2fcdb12aa953)

## Result:
Thus we have successfully detected lines by using Hough Transform.
