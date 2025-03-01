# Automatic License Plate Recognition (ALPR)

This repository implements an **Automatic License Plate Recognition (ALPR)** system using Python. The project combines **object detection**, **OCR (Optical Character Recognition)**, and **object tracking** techniques to detect vehicles and license plates, extract license plate text, and visualize results in video outputs.

---

## Features

- Detects vehicles and license plates in a video.  
- Tracks vehicles using the **SORT algorithm**.  
- Extracts license plate text using **EasyOCR**.  
- Interpolates missing data for bounding boxes.  
- Visualizes results with bounding boxes and license plate numbers on the video output.  

---

## Project Structure

```
📂 ALPR_Project/
├── add_missing_data.py     # Interpolates missing bounding box data.
├── main.py                 # Main script to detect, track, and extract license plate information.
├── util.py                 # Utility functions for OCR, data matching, and CSV handling.
├── visualize.py            # Visualizes bounding boxes and annotations on the video.
├── models/                 # Folder for YOLO model files.
│   ├── yolov8n.pt          # Pre-trained YOLO model for vehicle detection.
│   ├── license_plate_detector.pt # Custom YOLO model for license plate detection.
├── sort/                   # SORT implementation for object tracking.
│   ├── sort.py             # Main SORT algorithm.
│   ├── kalman_filter.py    # Helper for SORT algorithm.
├── sample.mp4              # Input video file.
├── test.csv                # CSV file with extracted license plate details.
├── test_interpolated.csv   # CSV file with interpolated bounding box data.
├── visualized_output.mp4   # Annotated output video.
└── README.md               # Project documentation.
```

---

## Requirements

Ensure you have Python 3.8 or above installed.

### Python Libraries

Install the following libraries:
- `numpy`
- `pandas`
- `opencv-python`
- `easyocr`
- `scipy`
- `ultralytics`
- `filterpy`

To install all dependencies at once:
```bash
pip install -r requirements.txt
```

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/ALPR_Project.git
   cd ALPR_Project
   ```

2. Download the pre-trained YOLO models:
   - **YOLOv8** for vehicle detection (`yolov8n.pt`) from [Ultralytics YOLO repository](https://github.com/ultralytics/ultralytics).
   - Custom **license plate detection model** (`license_plate_detector.pt`).

3. Ensure the SORT files (`sort.py`, `kalman_filter.py`) are present in the `sort/` directory.

---

## Usage

### Step 1: Detect and Extract Data
Run the `main.py` script to process the input video, track vehicles, detect license plates, and save extracted data to `test.csv`.

```bash
python main.py
```

### Step 2: Interpolate Missing Data
Use `add_missing_data.py` to interpolate missing bounding box data and create `test_interpolated.csv`.

```bash
python add_missing_data.py
```

### Step 3: Visualize Results
Run `visualize.py` to overlay bounding boxes and annotations on the input video. The annotated output is saved as `visualized_output.mp4`.

```bash
python visualize.py
```

---

## Results

- **Input Video:** The system processes an MP4 video to detect vehicles and license plates.
- **CSV Files:** Extracted and interpolated data are saved in `test.csv` and `test_interpolated.csv`.
- **Output Video:** A visualization video with bounding boxes and annotations is saved as `visualized_output.mp4`.

---

## Acknowledgments

This project leverages the following:
- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics): Object detection models for vehicles and license plates.
- [EasyOCR](https://github.com/JaidedAI/EasyOCR): OCR for license plate text recognition.
- [SORT Algorithm](https://github.com/abewley/sort): Real-time object tracking.

---
