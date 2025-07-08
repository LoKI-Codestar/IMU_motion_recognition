# IMU Motion Recognition using Sensor Fusion on Raspberry Pi

This project implements a real-time gesture recognition system using the **Sense HAT** on a **Raspberry Pi**, leveraging 6-axis IMU data (accelerometer + gyroscope) to classify gestures like `move_none`, `move_circle`, `move_shake`, and `move_twist`. The trained model is deployed using **TensorFlow Lite** and provides visual output on the Sense HAT LED matrix.

---

## 📌 Features

- Real-time gesture recognition on Raspberry Pi  
- IMU data fusion using accelerometer and gyroscope  
- Model training using TensorFlow  
- Deployment via TensorFlow Lite  
- LED output mapped to gestures using color codes  
- Graphical plots for 6-axis IMU signals  

---

## 📁 Repository Structure

```
IMU_motion_recognition/
├── data/                       # Raw .npy gesture recordings
├── graphs/                     # 6-axis IMU signal graph images
├── images/                     # Photos of LED matrix & hardware
├── model/                      # Trained model (.tflite)
├── src/
│   ├── data_capture.py         # Script to collect IMU gesture data
│   ├── train_model.py          # Model training script
│   ├── predict.py              # Real-time inference script
├── report/
│   └── imu_gesture_report.tex  # Final LaTeX project report
├── README.md                   # Project description (this file)
```

---

## 🧠 Model Overview

- **Input shape**: 50 time steps × 6 features (flattened to 300)
- **Architecture**: Fully Connected Neural Network with 2 hidden layers
- **Output**: Softmax over 4 gesture classes
- **Framework**: TensorFlow → TensorFlow Lite

---

## 🎯 Gestures & LED Color Mapping

| Gesture       | LED Matrix Color |
|---------------|------------------|
| move_none     | Black (OFF)      |
| move_circle   | Red              |
| move_shake    | Green            |
| move_twist    | Blue             |

---

## 🚀 Getting Started

### ✅ Requirements

- Raspberry Pi 4 or 5  
- Sense HAT  
- Python 3.9+  
- TensorFlow & TensorFlow Lite  
- NumPy, scikit-learn  

### 🔧 Setup Instructions

```bash
git clone https://github.com/LoKI-Codestar/IMU_motion_recognition.git
cd IMU_motion_recognition
```

1. Collect gesture data using `src/data_capture.py`  
2. Train your model using `src/train_model.py`  
3. Deploy and run live inference using `src/predict.py`

---

## 📊 Sensor Output Graphs

The project includes time-series plots for each gesture showing 6-axis IMU signals (x, y, z from accelerometer and gyroscope). These are available under the `graphs/` folder.

---

## 📸 Hardware Setup

Photos of the Raspberry Pi + Sense HAT setup, along with LED output during prediction, are available under the `images/` directory.

---

## 📄 Lab Report

The complete technical documentation is written using LaTeX and can be found at:

```
report/imu_gesture_report.tex
```

This includes sections like Introduction, Methodology, Model Training, Results, Challenges, and Conclusion.

---

## 🙋‍♂️ Author

**Sahil Gore**  
TH Deggendorf  
[GitHub: LoKI-Codestar](https://github.com/LoKI-Codestar)

---

## 📚 References

- [TensorFlow Lite Documentation](https://www.tensorflow.org/lite)  
- [Sense HAT Python API](https://pythonhosted.org/sense-hat/)  
- [Raspberry Pi Documentation](https://www.raspberrypi.com/documentation/)  
- THD Lab05 – Prof. Tobias Schaffer

---

## 🙌 Contributions

Feel free to fork the repo, suggest improvements, or open issues. PRs are welcome!