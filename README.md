# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations. i) Write the frame as JPG ii) Display the video iii) Display the video by resizing the window iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera 

### Step 2:
Use cv2.imread to read the video or image 

### Step 3:
Use cv2.imwrite to save the image

### Step 4:
Use cv2.imshow to show the video 

### Step 5:
End the program and close the output video window by pressing 'q'. 

## Program:
``` Python
### Developed By: Divyadharshini.A
### Register No: 212222240027

## i) Write the frame as JPG file
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("Fer.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()



### ii) Display the video

import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Car',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


### iii) Display the video by resizing the window

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
    cv2.imshow('212222230027_dario',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



### iv) Rotate and display the video


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
    cv2.imshow('212222230027_dario',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


```
## Output

### i) Write the frame as JPG image
![image](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/119393424/9a92e8a3-604f-48f7-9443-db5fe59fdc8c)


### ii) Display the video
![image](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/119393424/c7174c9a-3bf8-4ce2-ba09-18d42df15fd7)


### iii) Display the video by resizing the window
![image](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/119393424/fa8874be-f5ae-4167-ae4d-f5a9d7d877de)

### iv) Rotate and display the video
![image](https://github.com/swedha333/Image_Acqusition-_using_Web_Camera/assets/119393424/ed645428-0f5e-4603-b592-8af2eb0ddbe1)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
