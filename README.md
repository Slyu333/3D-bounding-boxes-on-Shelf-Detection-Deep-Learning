# 3D-bounding-boxes-on-Shelf-Detection-Deep-Learning

## 📖 Overview
This is a **Deep Learning Programming Test** project. 
In short, it is a detection task where the goal is to predict the **3D bounding boxes** of products on a shelf.

The solution implements a pipeline that utilizes the **Intel RealSense SDK** to process video files frame-by-frame, ensuring proper alignment between RGB and Depth streams. 

For each frame, **YOLOv8** is applied to detect products in 2D space. By combining these detections with the corresponding depth data, the system calculates the real-world **spatial coordinates $(X, Y, Z)$** and estimates the **physical dimensions $(Width, Height)$** of the items.

## 📊 Demo Result

The GIF below demonstrates the pipeline running on a test video (`first_order` data).
The green bounding boxes represent YOLOv8 detections, annotated with the calculated **Distance** and **Physical Size**.
<div align="center">
  <img src="asset/demo.gif" width="45%" />
  <img src="asset/demo2.gif" width="45%" />
  <br>
  <sub><i>Figure 1: Real-time 3D detection pipeline outputs. 
  <br>
  (Green box: YOLO detection | Text: Class, Distance, and Physical Dimensions WxH)</i></sub>
</div>
<br>
## 🛠️ Project Structure & Usage

The core logic is implemented in the Jupyter Notebook: `detection_task.ipynb`.

*   **Cells 1 - 4 (Test & Debug)**
    *   These cells are designed to extract a **single frame** from the `.bag` file for testing the YOLOv8 model and the depth calculation logic.
    *   Use these cells to visualize the alignment between RGB images and Depth maps, ensuring the data is loaded correctly.

*   **Cell 5 (Main Pipeline)**
    *   **This is the main execution script.**
    *   It automatically iterates through all `.bag` files in the specified directory.
    *   It processes the video stream frame-by-frame, calculates 3D coordinates, draws bounding boxes with annotations, and saves the final results as `.mp4` videos.
