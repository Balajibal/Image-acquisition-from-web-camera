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
img = cv2.VideoCapture(0)



## ii) Display the video
while(True):
     ret,frame=img.read()
     cv2.imwrite('mypiclook.jpg',frame)
     cv2.imshow('frame', frame)
     if cv2.waitKey(1) == ord('q'):
            break



## iii) Display the video by resizing the window
while True:
                ret, frame = cap.read()
                width = int(cap.get(3))
                height = int(cap.get(4))
                image = np.zeros(frame.shape, np.uint8)
                smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
                image[:height//2, :width//2] = smaller_frame
                image[height//2:, :width//2] = smaller_frame
                image[:height//2, width//2:] = smaller_frame
                image[height//2:, width//2:] = smaller_frame
                videoCaptureObject.release()
                cv2.destroyAllWindows()






## iv) Rotate and display the video
while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllwindows()








```
## Output

### i) Write the frame as JPG image
![Screenshot (24)](https://user-images.githubusercontent.com/75234946/162027009-cefbb803-442f-4b02-a1a2-7cf7ea61aa1f.png)



### ii) Display the video
![Screenshot (23)](https://user-images.githubusercontent.com/75234946/162027162-427658ab-8209-4a41-984a-40b60ff3f11a.png)



### iii) Display the video by resizing the window
![resizeimg](https://user-images.githubusercontent.com/75234946/162176472-534577e0-f5df-47df-9675-d67bdc2d96a6.jpeg)




### iv) Rotate and display the video
![rotateimg](https://user-images.githubusercontent.com/75234946/162176707-0a2dade3-dbd7-4e57-921b-ae468f033752.jpeg)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
