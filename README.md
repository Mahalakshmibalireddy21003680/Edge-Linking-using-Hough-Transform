# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required modules.
<br>

### Step2:
Import the image to operate on.
<br>

### Step3:
Convert the imported image from BGR to GRAYSCALE.
<br>

### Step4:
Find the edges using canny edge detector and display the image.
<br>

### Step5:
Detect the points that form a line using hough transform.
<br>

### Step6:
Draw the lines on the image
<br>

### Step7:
Display the output.
<br>

### Step8:
End the program.
<br>

## Program:
```Python
# Developed by: B.Mahalakshmi
# Register No.: 212221240008

# Read image and convert it to grayscale image

import cv2
import matplotlib.pyplot as plt
import numpy as np
image = cv2.imread("flower.jpg")
smoothImage = cv2.GaussianBlur(image,(3,3),0)
plt.imshow(smoothImage)
grayImage = cv2.cvtColor(smoothImage,cv2.COLOR_BGR2GRAY)
cv2.imshow("Original Image",image)
cv2.imshow("Gray Image",grayImage)




# Find the edges in the image using canny detector and display

cannyEdges = cv2.Canny(smoothImage,120,200)
plt.imshow(cannyEdges,cmap='gray')
plt.title('Edge Image')
plt.xticks([])
plt.yticks([])
plt.show()


# Detect points that form a line using HoughLinesP

lines = cv2.HoughLinesP(cannyEdges,1,np.pi/180,threshold=80,minLineLength = 50,maxLineGap = 250)



# Draw lines on the image

for line in lines:
    x1, y1, x2, y2 = line [0]
    cv2.line(image,(x1, y1),(x2, y2),(255, 0, 0),3)



# Display the result
plt.title("Hough Transform")
plt.imshow(image)
plt.show()





```
## Output

### Input image and grayscale image
![img1](https://user-images.githubusercontent.com/93427286/171181142-83308eff-6299-4248-b3f6-75c8f47b7e02.jpg)
![img2](https://user-images.githubusercontent.com/93427286/171181348-26c74495-68b4-4186-ac6d-4632dee5c16c.jpg)

<br>
<br>
<br>
<br>

### Canny Edge detector output
![img3](https://user-images.githubusercontent.com/93427286/171181376-27e88b1e-2c21-49d6-8b2f-58245684fb68.jpg)

<br>
<br>
<br>
<br>


### Display the result of Hough transform
![img4](https://user-images.githubusercontent.com/93427286/171181404-a541ff63-cc76-4055-ade2-d3b4f0dd26eb.jpg)

<br>
<br>
<br>
<br>



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
