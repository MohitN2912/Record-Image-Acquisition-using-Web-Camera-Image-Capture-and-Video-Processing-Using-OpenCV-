# Record-Image-Acquisition-using-Web-Camera-Image-Capture-and-Video-Processing-Using-OpenCV-

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

### 💻 Program

### i) Write the frame as JPG image
```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()

captured_image = cv2.imread('captured_frame.jpg')

plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```

### ii) Display the video
```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

### iii) Display the video by resizing the window
```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

### iv) Rotate and display the video
```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```

### Developed By:
## **Name: MOHIT N**   

## **Register No: 212225040255**

---

### Output

### i) Write the frame as JPG image

Captured image is saved as `captured_image.jpg`

<img width="645" height="508" alt="image" src="https://github.com/user-attachments/assets/ea681b4b-514c-449e-b196-4695ccfb17d3" />


### ii) Display the video

Live webcam video is displayed

<img width="645" height="490" alt="image" src="https://github.com/user-attachments/assets/4c8398b1-f191-491c-b4cb-d8e2b8e57f59" />



### iii) Display the video by resizing the window

Video is shown in resized resolution (640 × 480)


<img width="337" height="490" alt="image" src="https://github.com/user-attachments/assets/e50f5954-6f70-45f5-ac6a-26ede00a2b1d" />



### iv) Rotate and display the video

Video is displayed after rotation (90° clockwise)


<img width="377" height="490" alt="image" src="https://github.com/user-attachments/assets/9643c8fc-708f-49f3-b94b-4473bbda4fcd" />




---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
