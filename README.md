# IMU-Based Gesture Recognition using Raspberry Pi and TensorFlow Lite

This project implements real-time gesture recognition on a Raspberry Pi using IMU (accelerometer + gyroscope) sensor fusion via the Sense HAT module. A trained neural network classifies motion gestures and displays the result using color-coded output on the LED matrix.

---

## 🔧 Project Overview

- **Platform**: Raspberry Pi 4 Model B  
- **Sensors**: Sense HAT (Accelerometer + Gyroscope)  
- **Framework**: TensorFlow & TensorFlow Lite  
- **Language**: Python 3  
- **Recognition**: 4 predefined gestures:
  - `move_none`
  - `move_circle`
  - `move_shake`
  - `move_twist`

---

## 🧠 Model Pipeline

1. **Data Collection**  
   Raw 6-axis IMU data recorded at 50 Hz for 1 second (50 samples).

2. **Data Processing**  
   Each sample is flattened into a vector and labeled according to the gesture performed.

3. **Model Training**  
   A simple fully connected neural network is trained using TensorFlow and exported to `.tflite`.

4. **Deployment**  
   Real-time inference is performed on the Pi using TensorFlow Lite, and results are shown on the LED matrix.

---

## 📁 Repository Structure

```
├── motion_data/              # Contains labeled .npy files for each gesture
│   ├── move_circle/
│   ├── move_none/
│   ├── move_shake/
│   └── move_twist/
│
├── data_capture.py           # Script to record gesture samples
├── train_model.py            # (optional) Script to train and export the model
├── predict.py                # Real-time inference script for Raspberry Pi
├── motion_model.tflite       # Trained and exported model
├── plots/                    # IMU signal graphs for each gesture
│
├── report/                   # LaTeX project report
│   └── imu_gesture_report.tex
│
└── README.md                 # You're reading this!
```

---

## 🚀 Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/LoKI-Codestar/<your-repo-name>.git
   cd <your-repo-name>
   ```

2. **Install Dependencies**
   ```bash
   sudo apt update
   pip install numpy tensorflow scikit-learn sense-hat
   ```

3. **Collect Data**
   Run `data_capture.py` and perform gestures when prompted.  
   Modify the `LABEL` variable as needed.

4. **Run Inference**
   Deploy `motion_model.tflite` to Raspberry Pi and run `predict.py`.

---

## 📊 Sample Results

- Accuracy: ~95% on training, ~90% on validation
- Inference time: 20–40 ms
- LED Output:
  - `move_none` – Black (off)
  - `move_circle` – Red
  - `move_shake` – Green
  - `move_twist` – Blue

---

## 📸 Screenshots

<p float="left">
  <img src="plots/move_circle_example1.png" width="45%" />
  <img src="plots/move_circle_example2.png" width="45%" />
</p>

<p float="left">
  <img src="plots/move_twist_example1.png" width="45%" />
  <img src="plots/move_twist_example2.png" width="45%" />
</p>

---

## 📄 Report

The complete lab report with methodology, graphs, and analysis is available in the `report/` folder.  
📄 [`imu_gesture_report.tex`](report/imu_gesture_report.tex)

---

## 📚 References

- [TensorFlow Lite](https://www.tensorflow.org/lite)
- [Sense HAT Python API](https://pythonhosted.org/sense-hat/)
- [Raspberry Pi Docs](https://www.raspberrypi.com/documentation/)

---

## 👤 Author

**Sahil Gore**  
TH Deggendorf – Embedded Systems Lab 05  
Instructor: Prof. Tobias Schaffer

---