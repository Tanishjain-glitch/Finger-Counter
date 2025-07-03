# 🖖 Real-Time Finger Counter

This project detects and counts the number of fingers shown to a webcam in real-time using basic computer vision techniques with OpenCV. It can also be extended to perform gesture-based actions like controlling slides or media.

---

## 🔍 Features

* Counts number of fingers using contour and convex hull analysis
* Uses background subtraction for hand segmentation
* ROI-based processing for better speed
* Webcam support

---


## 🚀 Getting Started

### 🔧 Installation


## 📓 How It Works

### 1. **Background Averaging**

Captures static background during the first 30 frames:

```python
cv2.accumulateWeighted(frame, background, 0.5)
```

### 2. **Hand Segmentation**

Subtracts current frame from background to segment the hand:

```python
cv2.absdiff(background.astype("uint8"), current_frame)
```

### 3. **Finger Counting**

Uses convex hull and circular ROI logic to count extended fingers.

* Finds extreme points of hand
* Calculates center of palm
* Draws circular mask
* Counts contours outside the palm area

---

## 📅 Run the Code

```bash
python finger_counter.py
```

### Exit

Press `q` or `ESC` to exit the program.

---

## 💪 Improve Accuracy

* Use better lighting
* Place hand steadily in ROI
* Adjust ROI coordinates:

```python
roi_top = 100
roi_bottom = 300
roi_right = 350
roi_left = 550
```

---

## 🚗 Run Faster

* Use a USB webcam
* Reduce image size
* Skip displaying intermediate windows
* Run on Jetson Nano (accelerated OpenCV build)

---

## 📈 Future Ideas

* Add gesture classification
* Trigger actions (volume, browser control, etc.)
* Replace logic with MediaPipe or YOLOv8 hands

---

## 👤 Author

Made by Tanish Jain

---

