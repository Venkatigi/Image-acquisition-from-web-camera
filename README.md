# Image-Acquisition-from-Web-Camera
## Aim:  
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.<br>
i) Write the frame as JPG<br>
ii) Display the video <br>
iii) Display the video by resizing the window<br>
iv) Rotate and display the video

## Software Used:
Anaconda - Python 3.7
## Algorithm:
### Step 1:
Import Opencv Package.
### Step 2:
Capture the Video from the WebCamera.
### Step 3:
Write the image to a file.
### Step 4:
Show the image or the live camera.
### Step 5:
Show the image or the live camera.
## Program:
```
Developed By  : Venkatesh E
Register No   : 212221230119
```
### i) Write the frame as JPG file
``` Python
import cv2
video = cv2.VideoCapture(0)
while(True):
    t,frame = video.read()
    cv2.imwrite("Newpicture.jpg",frame)
    result=False
    if cv2.waitKey(1) == ord('b'):
        break
video.release()
cv2.destroyAllWindows()
```
### ii) Display the video
```python
import cv2
pic = cv2.VideoCapture(0)
while True:
    t,frame = pic.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1) == ord('b'):      
        break
pic.release()
cv2.destroyAllWindows()
```
### iii) Display the video by resizing the window
```python
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = smallerFrame
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = smallerFrame
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()
```
### iv) Rotate and display the video
```python
import numpy as np
import cv2
im = cv2.VideoCapture(0)
while True:
    ret,frame = im.read()
    width = int(im.get(3))
    height = int(im.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smallerFrame = cv2.resize(frame,(0,0),fx = 0.5,fy=0.5)
    image[:height//2,:width//2] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    image[height//2:, :width // 2] = smallerFrame
    image[:height//2, width//2:] = smallerFrame
    image[height//2:, width//2:] = cv2.rotate(smallerFrame,cv2.ROTATE_180)
    cv2.imshow('frame',image)
    if cv2.waitKey(1) == ord('b'):
        break
im.release()
cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image
![Write the frame as JPG image](1.JPG)
### ii) Display the video
![Display the video](2.JPG)
### iii) Display the video by resizing the window
![Display the video by resizing the window](3.JPG)
### iv) Rotate and display the video
![Rotate and display the video](4.JPG)
## Result:
Thus the image is accessed from webcamera and displayed using openCV.
