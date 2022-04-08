# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv and write the image as frame.

### Step 2:
Display the video and set q as a key to quit the process

### Step 3:
Import numpy and resize the frame.Display the resized frame

### Step 4:
Rotate the frame each time so that each image will be from a different quadrant

### Step 5:
Display the rotated frame

## Program:
``` Python
### Developed By: BALAJI N
### Register No: 212220230006

## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow("kakashi.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()




## ii) Display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video
import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()







```
## Output

### i) Write the frame as JPG image
![Screenshot (19)](https://user-images.githubusercontent.com/75234946/162189657-220b9226-7e3e-4647-bcf7-b9e576d2a4e5.png)




### ii) Display the video
![Screenshot (23)](https://user-images.githubusercontent.com/75234946/162027162-427658ab-8209-4a41-984a-40b60ff3f11a.png)



### iii) Display the video by resizing the window
![resizeimg](https://user-images.githubusercontent.com/75234946/162176472-534577e0-f5df-47df-9675-d67bdc2d96a6.jpeg)




### iv) Rotate and display the video
![rotateimg](https://user-images.githubusercontent.com/75234946/162176707-0a2dade3-dbd7-4e57-921b-ae468f033752.jpeg)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
