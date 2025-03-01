#!/bin/bash

# ================================================
# Automatic License Plate Recognition (ALPR)
# ================================================
# This project implements an Automatic License Plate Recognition (ALPR)
# system using Python. It combines object detection, OCR, and tracking
# to detect vehicles and license plates, extract license plate text,
# and annotate video outputs.

# ================================================
# Features
# ================================================
# 1. Detects vehicles and license plates in a video.
# 2. Tracks vehicles using the SORT algorithm.
# 3. Extracts license plate text using EasyOCR.
# 4. Interpolates missing bounding box data.
# 5. Visualizes results with annotations in an output video.

# ================================================
# Project Structure
# ================================================
# 📂 ALPR_Project/
# ├── add_missing_data.py      # Interpolates missing bounding box data
# ├── main.py                  # Main script for detection, tracking, and extraction
# ├── util.py                  # Utility functions for OCR and data processing
# ├── visualize.py             # Visualizes bounding boxes and annotations
# ├── models/                  # YOLO model files
# │   ├── yolov8n.pt           # Pre-trained YOLO for vehicle detection
# │   ├── license_plate_detector.pt  # Custom YOLO model for license plates
# ├── sort/                    # SORT tracking algorithm
# │   ├── sort.py              # Main SORT implementation
# │   ├── kalman_filter.py     # Kalman filter for SORT
# ├── sample.mp4               # Input video file
# ├── test.csv                 # Extracted license plate details
# ├── test_interpolated.csv    # Interpolated bounding box data
# ├── visualized_output.mp4    # Annotated output video
# └── README.md                # Documentation

# ================================================
# Requirements
# ================================================
# Python 3.8 or above is required. Install the following Python libraries:
# - numpy
# - pandas
# - opencv-python
# - easyocr
# - scipy
# - ultralytics
# - filterpy

# Install all dependencies with:
pip install -r requirements.txt

# ================================================
# Installation
# ================================================
# Clone the repository:
git clone https://github.com/your-username/ALPR_Project.git
cd ALPR_Project

# Download YOLO models:
# - YOLOv8n for vehicle detection from Ultralytics
# - Custom license plate detection model (license_plate_detector.pt)

# ================================================
# Usage
# ================================================

# 1. Detect and Extract Data
# Run the main script to process the input video and save extracted data to test.csv:
python main.py

# 2. Interpolate Missing Data
# Use add_missing_data.py to fill gaps in bounding box data:
python add_missing_data.py

# 3. Visualize Results
# Run visualize.py to create an annotated output video:
python visualize.py

# ================================================
# Results
# ================================================
# - Input Video: sample.mp4
# - CSV Outputs: test.csv and test_interpolated.csv
# - Annotated Output: visualized_output.mp4

# ================================================
# Acknowledgments
# ================================================
# - YOLOv8 by Ultralytics for object detection
# - EasyOCR for text recognition
# - SORT algorithm for real-time object tracking
