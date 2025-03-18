# Face Tracking Device with Python and Arduino

## Overview
This project is a real-time face tracking system that uses Python and OpenCV for face detection and Arduino for camera movement. The system captures a video feed, detects faces, and moves a camera accordingly using servo motors.

## Features
- Real-time face detection using OpenCV's Haar Cascade Classifier
- Serial communication between Python and Arduino
- Camera movement using servo motors based on face position
- Adjustable sensitivity and movement parameters

## Required Components
- **Arduino UNO**
- **2x Servo Motors** (e.g., Tower Pro SG90)
- **Web Camera**
- **Python & OpenCV libraries**
- **Haar Cascade file** for face detection

## Installation and Setup

### 1. Install Dependencies
Make sure you have Python installed. Then, install the required libraries:
```bash
pip install opencv-python pyserial numpy
```

### 2. Setup the Arduino
Upload the Arduino sketch (`Cameracontol.ino`) to your Arduino board using the Arduino IDE.

### 3. Run the Python Script
Place the `haarcascade_frontalface_default.xml` file in the same directory as `main.py` and run the script:
```bash
python main.py
```

## How It Works
1. The webcam captures video frames.
2. OpenCV detects faces in real-time.
3. The Python script sends position commands (`L`, `R`, `U`, `D`, `S`) to the Arduino over a serial connection.
4. The Arduino moves the servos to adjust the camera's orientation.

## Code Overview
### Python (`main.py`)
- Reads frames from the webcam.
- Converts frames to grayscale.
- Detects faces and determines their position.
- Sends movement commands (`L`, `R`, `U`, `D`) to Arduino based on face position.

### Arduino (`Cameracontol.ino`)
- Receives commands from Python via serial communication.
- Controls servo motors to adjust camera direction.

## Future Improvements
- Implementing deep learning-based face tracking for better accuracy.
- Adding support for multiple face tracking.
- Using a pan-tilt camera module for smoother movement.

## Author
Developed by Mohamed Bouchenti. Contributions and suggestions are welcome!
