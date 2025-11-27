# 3D-bounding-boxes-on-Shelf-Detection-Deep-Learning

## 📖 Overview
This is a **Deep Learning Programming Test** project. 
In short, it is a detection task where the goal is to predict the **3D bounding boxes** of products on a shelf.

This solution uses **YOLOv8** for 2D object detection and **Intel RealSense SDK** for depth extraction to calculate the real-world coordinates $(X, Y, Z)$ and physical dimensions $(Width, Height)$ of the items.


## 🛠️ Project Structure & Usage

The core logic is implemented in the Jupyter Notebook: `detection_task.ipynb`.

*   **Cells 1 - 4 (Test & Debug)**
    *   These cells are designed to extract a **single frame** from the `.bag` file for testing the YOLOv8 model and the depth calculation logic.
    *   Use these cells to visualize the alignment between RGB images and Depth maps, ensuring the data is loaded correctly.

*   **Cell 5 (Main Pipeline)**
    *   **This is the main execution script.**
    *   It automatically iterates through all `.bag` files in the specified directory.
    *   It processes the video stream frame-by-frame, calculates 3D coordinates, draws bounding boxes with annotations, and saves the final results as `.mp4` videos.
