# Sign Language Recognition

A real-time Tamil Sign Language Recognition system that translates hand gestures into text and speech using computer vision and machine learning. The system extracts hand landmarks via MediaPipe, classifies gestures with a trained ML model, and delivers real-time predictions with text-to-speech output — achieving **99.64% accuracy** across **12 gesture classes**.

---

## Overview

This project bridges communication gaps for the hearing and speech impaired by recognizing Tamil sign language gestures in real time through a webcam feed. Hand movements are captured, converted into landmark coordinates, and classified using a trained machine learning model, with the result converted to speech for accessible communication.

---

## Features

- **Real-time gesture recognition** via live webcam feed
- **High-precision classification** — 99.64% accuracy across 12 gesture classes
- **Landmark-based detection** — 63 landmark features extracted from 21 hand keypoints per gesture
- **Large-scale training data** — trained on 11,000+ images
- **Smoothed live inference** to reduce jitter and false predictions in real time
- **Text-to-Speech output** for accessible, spoken translation of recognized gestures
- **Model evaluation tools** to validate accuracy and performance on the landmark dataset

---

## Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat-square&logo=opencv&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0097A7?style=flat-square&logo=google&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)

- **Computer Vision:** OpenCV, MediaPipe (hand landmark detection)
- **Machine Learning:** Scikit-learn (MLP classifier)
- **Speech Output:** Text-to-Speech
- **Frontend:** JavaScript-based interface for live interaction

---

## Project Structure

```
Sign_language_recognition/
├── Backend/                          # Core backend logic and model serving
├── Evaluation Metrics/               # Scripts and results for model evaluation
├── Fonts/                            # Fonts used for Tamil text rendering
├── Frontend/                         # User-facing interface
├── extract_landmarks_to_csv.py       # Extracts hand landmarks from images into CSV format
├── train_mlp_landmarks.py            # Trains the MLP classifier on landmark data
├── evaluate_mlp_landmarks.py         # Evaluates trained model performance and accuracy
├── validate_landmark_dataset.py      # Validates and cleans the landmark dataset
├── live_landmark_inference_smoothed.py  # Real-time gesture inference with smoothing
├── requirements.txt                  # Python dependencies
├── package-lock.json                 # Frontend dependency lock file
├── .gitignore
└── README.md
```

---

## How It Works

1. **Data Collection & Extraction** — Hand landmarks are extracted from a dataset of 11,000+ gesture images using MediaPipe, capturing 21 hand keypoints (63 features) per sample, via `extract_landmarks_to_csv.py`.
2. **Training** — The extracted landmark data is used to train an MLP (Multi-Layer Perceptron) classifier in `train_mlp_landmarks.py`.
3. **Validation & Evaluation** — The dataset and trained model are validated and evaluated for accuracy using `validate_landmark_dataset.py` and `evaluate_mlp_landmarks.py`.
4. **Live Inference** — `live_landmark_inference_smoothed.py` captures real-time webcam input, detects hand landmarks, classifies the gesture, and applies smoothing to stabilize predictions.
5. **Output** — The recognized gesture is converted to text and spoken aloud via Text-to-Speech.

---

## Setup & Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/NehaaVairavel/Sign_language_recognition.git
   cd Sign_language_recognition
   ```

2. **Install Python dependencies**
   ```bash
   python -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. **Install frontend dependencies** (if running the Frontend interface)
   ```bash
   cd Frontend
   npm install
   ```

4. **Extract landmarks from your dataset**
   ```bash
   python extract_landmarks_to_csv.py
   ```

5. **Train the model**
   ```bash
   python train_mlp_landmarks.py
   ```

6. **Evaluate the model**
   ```bash
   python evaluate_mlp_landmarks.py
   ```

7. **Run live inference**
   ```bash
   python live_landmark_inference_smoothed.py
   ```

---

## Results

| Metric              | Value            |
|----------------------|------------------|
| Accuracy              | 99.64%           |
| Gesture Classes       | 12               |
| Training Images       | 11,000+          |
| Landmark Features     | 63 (21 hand keypoints) |

---

## Future Improvements

- Expand gesture vocabulary beyond 12 classes for broader sign language coverage
- Add support for two-handed and dynamic (motion-based) gestures
- Deploy as a web or mobile application for wider accessibility
- Add multi-language speech output support

---

## Author

**Nehaa Vairavel**
📧 nehaaselvi2005@gmail.com
