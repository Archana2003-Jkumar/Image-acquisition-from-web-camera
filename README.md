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
Import cv2 and numpy if needed.
### Step 2:
Use videocapture to access webcam.
### Step 3:
Display the accessed image.
### Step 4:
Use numpy operations to initialize value to width and height.
### Step 5:
Close the webcam by initializing a character.

## Program:
``` Python
### Developed By:Archana priya . J
### Register No:212221230007
```
## i) Write the frame as JPG file
```
import cv2
vid=cv2.VideoCapture(0)
while(True):
    ret,frame = vid.read()
    cv2.imshow('mypicture',frame)
    result = False
vid.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
import cv2
vid=cv2.VideoCapture(0)
while(True):
    ret,frame = vid.read()
    cv2.imshow('mypicture',frame)
    if cv2.waitKey(1)==ord('n'):
        break
vid.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
import cv2
import numpy as np
vid=cv2.VideoCapture(0)
while True :
     ret,frame = vid.read()
        width = int (vid.get(3))
        hgt = int(vid.get(4))
        
        image = np.zeros(frame.shape,np.unit8)
        smallfrm = cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
        image[:hgt//2, :width//2 ]=smallfrm
        image[hgt//2, :width//2 ]=smallfrm
        image[:hgt//2, :width//2 ]=smallfrm
        image[:hgt//2, :width//2 ]=smallfrm
         cv2.imshow('mypicture',image)
             if cv2.waitKey(1)==ord('n'):
                break
vid.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```
import cv2
import numpy as np
vid=cv2.VideoCapture(0)
while True :
            ret,frame = vid.read()
            width = int (vid.get(3))
            hgt = int(vid.get(4))

            image = np.zeros(frame.shape,np.uint8)
            smallfrm = cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
            image[:hgt//2, :width//2 ]=cv2.rotate(smallfrm,cv2.ROTATE_180)
            image[hgt//2:, :width//2 ]=smallfrm
            image[:hgt//2, width//2: ]=smallfrm
            image[hgt//2:, width//2: ]=cv2.rotate(smallfrm,cv2.ROTATE_180)
  
            cv2.imshow('mypicture',image)
            if cv2.waitKey(1)==ord('n'):
                    break
vid.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image

![dip1](https://user-images.githubusercontent.com/93427594/226092324-e1745d87-8f10-45d1-b370-f81f05206d77.png)

### ii) Display the video
![Screenshot (355)](https://user-images.githubusercontent.com/93427594/226092283-3a86f3b0-c160-42ee-810f-c59b3be29f1b.png)


### iii) Display the video by resizing the window
![Screenshot (357)](https://user-images.githubusercontent.com/93427594/226092267-02035b98-87a1-4e0c-872e-01d4d0c7db86.png)



### iv) Rotate and display the video
![Screenshot (358)](https://user-images.githubusercontent.com/93427594/226092301-4a548a95-8006-4fca-9fef-0fb0760d0f7e.png)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
