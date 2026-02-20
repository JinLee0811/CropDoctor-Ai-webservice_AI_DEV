# 🧠 CropDoctor AI Module

This repository contains the AI model and inference service used in the CropDoctor system.

The module is responsible for:
- Training a CNN-based plant disease classification model
- Performing inference on uploaded plant images
- Serving predictions via an API endpoint

---

## 🚀 Overview

The AI system classifies plant images into **20 disease categories** using a transfer learning approach.

Model architecture:
- **MobileNetV2 (pretrained)**
- Fine-tuned for multi-class plant disease classification
- Built with TensorFlow

The model is optimised for:
- Lightweight inference
- Real-world deployment constraints
- Handling class imbalance in agricultural datasets

---

## 📊 Dataset & Preprocessing

- Public agricultural plant disease image dataset
- 20 target classes
- Significant class imbalance addressed via:
  - Random sampling
  - Weighted cross-entropy loss

### Data Augmentation
- Rotation
- Random resized crop
- Horizontal flip

These techniques improved generalisation and reduced overfitting.

---

## ⚙️ Training Configuration

- Framework: TensorFlow
- Optimizer: Adam
- Learning Rate: 0.001
- Batch Size: 64
- Epochs: 10–20
- Input Size: 224 x 224 x 3

Model performance evaluated using:
- Validation accuracy
- Loss tracking
- Confusion matrix analysis

---

## 🏗 Inference Service

The trained model is exposed through a FastAPI-based inference service.

Responsibilities:
- Accept image upload
- Preprocess input image
- Perform model inference
- Return predicted disease label

---

## 🔐 Environment Variables

Create a `.env` file in the root directory and configure the following variables:

```env
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
ENDPOINT_URL=
```
## 🖥️ Running the AI Service

```bash
# move into AI directory
cd ai

# optional: create virtual environment
conda create -n cropdoctor python=3.8
conda activate cropdoctor

# install dependencies
pip install -r requirements.txt

# start inference server
uvicorn main:app --reload
```

---

## 📌 Future Improvements

- Improve dataset balancing
- Add real-time inference optimisation
- Explore object detection models (e.g., YOLO)
- Introduce model monitoring & performance tracking

---

## 👨‍💻 Author

Jin Lee  
AI-focused Software Engineer

