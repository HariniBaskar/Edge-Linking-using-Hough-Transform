# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary Packages

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates. Display the image.


## Program:
```
Developed by: Harini.B
Reg. No: 212221230035
```

```
# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("catt.jpg",0)
Grimg = cv2.GaussianBlur(image,(3,3),0)
plt.axis('off')
plt.imshow(Grimg)
plt.show()

# Find the edges in the image using canny detector and display
edge = cv2.Canny(Grimg,40,40)
plt.imshow(edge,cmap='gray')
plt.title('Edge image')
plt.xticks([])
plt.yticks([])
plt.show()

# Detect points that form a line using HoughLinesP
lines = cv2.HoughLinesP(edge,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)

# Draw lines on the image
for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(255,0,0),3)

# Display the result
plt.imshow(edge)
plt.axis('off')
plt.show()

```
## Output

### Input image and grayscale image
![out1](https://user-images.githubusercontent.com/93427253/233847660-4348f398-3640-4410-9097-6a110a80e1ca.png)

### Canny Edge detector output
![out2](https://user-images.githubusercontent.com/93427253/233847669-77d9c001-e8b3-4775-baf9-3ac5008a38b1.png)

### Display the result of Hough transform
![out3](https://user-images.githubusercontent.com/93427253/233847687-d2e35230-d367-4873-a463-506c54d9d09a.png)


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
