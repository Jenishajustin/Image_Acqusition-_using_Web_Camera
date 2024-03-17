# Image Acqusition - using Web Camera
## Aim 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.
<br>

### Step 2:
Use cv2.imread to read the video or image.
<br>

### Step 3:
Use cv2.imwrite to save the image.
<br>

### Step 4:
Use cv2.imshow to show the video.
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## Program:

### Developed By: J.JENISHA
### Register No: 212222230056

## i) Write the frame as JPG file
```python
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("diver.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Diver',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230028_deepika',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Jenisha J',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image

![diver](https://github.com/Jenishajustin/Image_Acqusition-_using_Web_Camera/assets/119405070/48b2f31a-499c-4a47-a798-bc448671ed7c)



### ii) Display the video

![Screenshot 2024-03-17 101219](https://github.com/Jenishajustin/Image_Acqusition-_using_Web_Camera/assets/119405070/83df1283-5d3b-4d6d-8f83-b3c9abbefa81)



### iii) Display the video by resizing the window

![Screenshot 2024-03-17 101642](https://github.com/Jenishajustin/Image_Acqusition-_using_Web_Camera/assets/119405070/b2198f67-5434-4af4-9632-a4c7d5aeab58)




### iv) Rotate and display the video

![Screenshot 2024-03-17 101852](https://github.com/Jenishajustin/Image_Acqusition-_using_Web_Camera/assets/119405070/5196f5db-572d-47c3-8150-1c1a06e37581)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
