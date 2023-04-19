# EXPERIMENT 08: EDGE LINKING USING HOUGH TRANSFORM
## AIM:
To write a Python program to detect the lines using Hough Transform.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## ALGORITHM:
### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load a image using imread() from cv2 module.

### Step 3:
Convert the image to grayscale.

### Step 4:
Using Canny operator from cv2,detect the edges of the image

### Step 5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.

### Step 6:
Display the image and end the program.

## PROGRAM:
```
#Import necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read image and convert it to grayscale image
image = cv2.imread("building2.jpg",0)
img = cv2.GaussianBlur(image,(3,3),0)

plt.axis('off')
plt.imshow(img)
plt.show()

# Find the edges in the image using canny detector and display
edge = cv2.Canny(img,50,50)
plt.imshow(edge,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()

#Detect the points that form the line
lines=cv2.HoughLinesP(edge,1,np.pi/180, threshold=80, minLineLength=40,maxLineGap=250)

# Draw lines on the image
for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(255,0,255),3)

# Display the result
plt.imshow(edge)
plt.axis('off')
plt.show()



```
## OUTPUT:

### Input image and grayscale image:  
![image](https://user-images.githubusercontent.com/93427256/232980897-80220d35-d58b-4ad7-9019-bfa9b80b9bfa.png)  

![image](https://user-images.githubusercontent.com/93427256/232980667-c1fd073b-0ac9-40bf-a34a-2c72d2185d2b.png)

### Canny Edge detector output:  
![image](https://user-images.githubusercontent.com/93427256/232979475-95da4866-5f24-4fb3-b24a-13cb6d456c85.png)

### Display the result of Hough transform:  
![image](https://user-images.githubusercontent.com/93427256/232979896-7f2a86d2-4a8f-40cc-804d-528ca3e276e2.png)

## RESULT:  

Thus the program is written with python and OpenCV to detect lines using Hough transform. 
