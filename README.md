# Posture-Detection

A lightweight, high-performance web application that bridges the gap between computer vision and physical ergonomics. The system utilizes deep learning models to extract skeletal landmarks from a live webcam feed, providing a solid foundation for real-time body alignment and posture analysis.

## 📌 Features

- **Neural Landmark Extraction:** Tracks 17 unique anatomical keypoints (eyes, ears, nose, shoulders, elbows, wrists, hips, knees, and ankles) in real-time.
- **Dynamic Skeletal Visualization:** Overlays a responsive "digital twin" skeleton directly onto the video feed.
- **Perfect Coordinate Precision:** Solved canvas-to-video resolution scaling issues to ensure a seamless 1:1 overlay with zero lag.

---

## 🛠️ Tech Stack

- **Frontend/UI:** HTML5, CSS3
- **Graphics & Canvas:** [p5.js](https://p5.js.org/) (for rendering the camera feed and coordinate system)
- **Machine Learning Engine:** [ml5.js](https://ml5.org/) / TensorFlow.js (powering the pre-trained **PoseNet** model)

---

## 🧠 How It Works

1. **Capture:** The browser requests webcam permission using p5.js's `createCapture(VIDEO)`.
2. **Estimation:** The raw video frames are continuously fed into the **PoseNet** neural network.
3. **Mapping:** The model outputs an array of `(x, y)` spatial coordinates along with confidence scores for 17 key points.
4. **Rendering:** The application loops through these coordinates to dynamically draw lines (the skeleton) and ellipses (the joints) perfectly on top of the user's image.

---
