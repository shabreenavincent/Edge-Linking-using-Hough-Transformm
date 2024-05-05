## Edge-Linking-using-Hough-Transformm
### Aim:
To write a Python program to detect the lines using Hough Transform.

### Software Required:
Anaconda - Python 3.7

### Algorithm:
#### Step1:

Import all the necessary modules for the program.
#### Step2:

Load a image using imread() from cv2 module.
#### Step3:

Convert the image to grayscale.
#### Step4:

Using Canny operator from cv2,detect the edges of the image.
#### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
### Program:
```python
DEVELOPED BY: SHABREENA VINCENT
REG NO: 212222230141
```
#### Read image and convert it to grayscale image
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("eren.png",0)
img_c=cv2.imread("eren.png",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
#### Find the edges in the image using canny detector and display
```python
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
#### Detect points that form a line using HoughLinesP
```python
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
#### Draw lines on the image
```python
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
#### Display the result
```python
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
### Output

#### Input image and grayscale image
![Screenshot 2024-04-12 091032](https://github.com/SHARAN-MJ/Edge-Linking-using-Hough-Transformm/assets/119560305/174d7bd0-ebcc-431f-9844-0964d3b82942)


#### Canny Edge detector output
![Screenshot 2024-04-12 091040](https://github.com/SHARAN-MJ/Edge-Linking-using-Hough-Transformm/assets/119560305/4dda4a1f-96c4-4ecf-8018-5af210fa7ca4)


#### Display the result of Hough transform
![Screenshot 2024-04-12 091048](https://github.com/SHARAN-MJ/Edge-Linking-using-Hough-Transformm/assets/119560305/1ad809c7-a35f-4ba5-93f0-a365fa2efef9)

### Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
