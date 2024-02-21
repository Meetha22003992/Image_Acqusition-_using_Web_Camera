# Image_Acqusition-_using_Web_Camera
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
<br>Import cv2 and capture the viedo using cv2.ViedoCapture(0).

### Step 2:
<br>Write the capture image using cv2.imwrite("NewPicture.jpg",frame).

### Step 3:
<br>Resize the image using cv2.resize(frame,(0,0),fx=0.5,fy=0.5).

### Step 4:
<br>Display the image until the loop gets over.

### Step 5:
<br>Rotate the image using cv2.rotate(smaller_frame,cv2.ROTATE_180).

## Program:
``` Python
### Developed By:MEETHA PRABHU
### Register No:212222240065

## i) Write the frame as JPG file

import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video

import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('212222240065_Meetha',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window

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
    cv2.imshow('212222240065_Meetha',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video

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
    cv2.imshow('212222240065_Meetha',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image
</br>![WIN_20240221_21_55_10_Pro](https://github.com/Meetha22003992/Image_Acqusition-_using_Web_Camera/assets/119401038/dc958383-6b25-4ffb-9f4b-834287d88aab)

</br>

### ii) Display the video
</br>![Screenshot 2024-02-21 221753](https://github.com/Meetha22003992/Image_Acqusition-_using_Web_Camera/assets/119401038/79d2b6ea-5df2-4745-92b9-86bdfc5eeafc)

</br>

### iii) Display the video by resizing the window
</br>![Screenshot 2024-02-21 222340](https://github.com/Meetha22003992/Image_Acqusition-_using_Web_Camera/assets/119401038/bb61055e-9b6d-418b-a7bc-c6bb56ab18aa)

</br>

### iv) Rotate and display the video
</br>![Screenshot 2024-02-21 222425](https://github.com/Meetha22003992/Image_Acqusition-_using_Web_Camera/assets/119401038/cff52233-6cfb-476e-8c9b-6d204c97b31a)

</br>


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
