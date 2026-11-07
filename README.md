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

<img width="642" height="512" alt="image" src="https://github.com/user-attachments/assets/03dd7044-a8a9-45e2-91b3-19fed68c0dd8" />


### ii) Display the video

Live webcam video is displayed

<img width="645" height="486" alt="image" src="https://github.com/user-attachments/assets/0d6e0da1-001b-4c37-8fc2-09fbe00209ea" />



### iii) Display the video by resizing the window

Video is shown in resized resolution (640 × 480)


<img width="333" height="496" alt="image" src="https://github.com/user-attachments/assets/767f9d5e-a89b-48c7-9f8b-1a224fa297fe" />



### iv) Rotate and display the video

Video is displayed after rotation (90° clockwise)


<img width="372" height="490" alt="image" src="https://github.com/user-attachments/assets/d3e55a51-8880-4cfa-b2b0-addf59d77716" />




---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
