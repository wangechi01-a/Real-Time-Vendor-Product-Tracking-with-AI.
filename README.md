# Real-Time Vendor Product Tracking with AI

## Overview

This assignment involves creating a basic real-time vendor product tracking system using AI and machine learning. The goal is to detect and track products in a warehouse-like environment from a pre-existing or self-recorded video. You will use object detection models to identify and track items within a video feed. The project must be completed within a day.

## Objectives

### 1. Data Collection and Preprocessing:
- Use an existing video dataset or create a short video (1-2 minutes) of products in a warehouse-like environment.
- Extract key frames from the video.
- Label the products in the extracted frames to prepare them for model training using tools like Roboflow.

### 2. Model Development:
- Develop a basic object detection model using the pre-trained YOLOv3 (You Only Look Once version 3) implemented via the Ultralytics library.
- Train the model on the labeled frames to detect and classify the products within the video.

### 3. Basic Tracking System:
- Implement a simple tracking system to track product locations over time in the video feed.
- Ensure detected products are highlighted with bounding boxes as they appear in the video.

## Deliverables

1. **Video Data**: 
   - A short video (or extracted frames) of products in a warehouse-like setup.
   - Labeled frames for training the detection model.
   
2. **Detection Model**:
   - A basic object detection model trained to detect a few products in the video.
   - Include the code used for model training and detection.

3. **Tracking Output**:
   - A video or a series of frames showing detected and tracked products with bounding boxes drawn around them.

## Tools and Technologies

- **Programming Language**: Python
- **Libraries**: 
  - OpenCV (for video processing)
  - TensorFlow/Keras or PyTorch (for model development)
  - **Roboflow** (for dataset management and labeling)
  - **Ultralytics YOLOv3** (for implementing the YOLOv3 model)
- **Pre-trained Model**: YOLOv3 (for faster implementation)

## How YOLOv3 Works

YOLOv3 is a state-of-the-art, real-time object detection model that uses a single convolutional neural network (CNN) to predict multiple bounding boxes and class probabilities directly from full images in one evaluation. Here's how it functions within this project:

1. **Single Pass Detection**: YOLOv3 divides the input image into a grid and predicts bounding boxes and probabilities for each grid cell, making it efficient for real-time applications.
2. **Multi-Scale Predictions**: The model detects objects at different scales using multiple layers, improving its ability to detect small and large objects effectively.
3. **Non-Maximum Suppression (NMS)**: YOLOv3 applies NMS to eliminate redundant overlapping boxes and retain only the most confident predictions.

## How the Project Works

1. **Data Preparation**:
   - A video or a set of frames is prepared, showcasing various products in a warehouse environment.
   - The frames are labeled with the product names and bounding box coordinates using **Roboflow**. Roboflow simplifies the annotation process, allowing you to upload images, label them, and manage datasets efficiently.

2. **Model Training**:
   - The YOLOv3 model is configured and trained on the labeled frames. The **Ultralytics** library provides a straightforward interface to work with YOLOv3, allowing for easy integration and training of the model.
   - Transfer learning is utilized by loading pre-trained weights, which speeds up the training process and improves accuracy.

3. **Object Detection and Tracking**:
   - The trained YOLOv3 model processes the input video frame by frame.
   - For each frame, the model detects products and draws bounding boxes around them.
   - A basic tracking algorithm, such as the Kalman filter or simple centroid tracking, is implemented to maintain the identity of each detected product across frames, ensuring consistent tracking.

4. **Output Visualization**:
   - The output is displayed as a video showing the bounding boxes around detected products in real-time, allowing users to observe how the model performs in tracking.

## Instructions for Setup

1. **Clone or download the project**.
2. **Install the required libraries**:
   ```bash
   pip install opencv-python tensorflow keras roboflow ultralytics
   ```
3. **Run the data preprocessing script** to extract frames and label them using Roboflow.
4. **Train the object detection model** using the Ultralytics YOLOv3 implementation with the provided code and labeled frames.
5. **Run the tracking system** to detect and track products in the video feed.

## How to See and Use the Project

1. **View the Project**:
   - After cloning the repository, navigate to the project directory and open the files to explore the code, data, and documentation.
   - View the sample video and output videos in the designated folder.

2. **Run the Project**:
   - Ensure all dependencies are installed as per the setup instructions.
   - Run the main script to execute the tracking system. You can modify the input video file path in the code to test with different videos.
