# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program

### Step2:
Load a image using imread() from cv2 module

### Step3:
Convert the image to grayscale.

### Step4:

Using Canny operator from cv2,detect the edges of the image


### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.



## Program:
```
import cv2
import matplotlib.pyplot as plt
import numpy as np

# Read image and convert it to grayscale image

image=cv2.imread("road.jfif")
gray_img=cv2.cvtColor(image,cv2.COLOR_BGR2GRAY)
img=cv2.GaussianBlur(gray_img,(3,3),0)
plt.imshow(image)

# Find the edges in the image using canny detector and display

edges = cv2.Canny(image,160, 200)
plt.figure(figsize=(16,16))
plt.subplot(1,2,1)
plt.imshow(img,cmap='gray')
plt.title('Gray')
plt.subplot(1,2,2)
plt.imshow(edges,cmap='gray')
plt.title("Canny_edges")
plt.xticks([])
plt.yticks([])
plt.show()

# Detect points that form a line using HoughLinesP

lines=cv2.HoughLinesP(edges,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)

# Draw lines on the image

for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(image,(x1,y1),(x2,y2),(0,205,255),2)

# Display the result

plt.imshow(image)
plt.title('HOUGH')
plt.axis('off')


```


## Output

### Input image and grayscale image
![d1](https://github.com/Sharmilasha/EDGE--LINKING-HOUGH-TRANSFORM/assets/94506182/6b7d62d5-6f50-4c22-a6c8-a9de1762f498)



### Canny Edge detector output
![d2](https://github.com/Sharmilasha/EDGE--LINKING-HOUGH-TRANSFORM/assets/94506182/e3cd510a-b170-4909-987d-26742ceff63f)



### Display the result of Hough transform
![d3](https://github.com/Sharmilasha/EDGE--LINKING-HOUGH-TRANSFORM/assets/94506182/d5a912de-a1e4-43db-8258-97149be3b82a)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
