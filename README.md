Overview
This repository contains a custom‑trained computer vision model for maize leaf disease detection.
The model identifies common maize diseases directly from leaf images, enabling farmers, agronomists, and agricultural AI systems to perform fast, reliable, automated diagnosis.


Disease Classes
The model predicts one of four classes:

Blight

Common Rust

Gray Leaf Spot

Healthy


Repository Structure
Code
/maize/
   maize_model.h5
   maize_notebook.ipynb
   README.md

/utils/
   preprocessing.py
   inference.py

/assets/
   sample_images/
Generate this structure: Folder Structure

Training Pipeline
The model was trained using a standard TensorFlow/Keras workflow:

Image loading & preprocessing

Data augmentation

CNN architecture definition

Training & validation

Evaluation & metrics

Exporting .h5 model file


Model Performance
Metric	Value
Accuracy	0.94
Validation Accuracy	0.92
Loss	0.18


How to Use the Model
TensorFlow Inference Example
python
import tensorflow as tf
import numpy as np
from PIL import Image

model = tf.keras.models.load_model("maize_model.h5")

img = Image.open("leaf.jpg").resize((224, 224))
img = np.array(img) / 255.0
img = np.expand_dims(img, axis=0)

pred = model.predict(img)
classes = ["Blight", "Common Rust", "Gray Leaf Spot", "Healthy"]

print(classes[np.argmax(pred)])
Convert to PyTorch: Convert Model

Deployment Options
You can deploy this model using:

FastAPI

Flask

Streamlit

Hugging Face Spaces

Edge devices (Jetson Nano, Raspberry Pi)

Deployment guide: Deployment Guide

Use Cases
Automated crop monitoring

Early disease detection

Precision agriculture

Mobile farming apps

Research & academic projects

License
Apache 2.0  — free for research, commercial use, and modification.

Author
Victor Jimmy  
AI Consultant & Solution Architect
JimmyzConcepts Ltd — Aberdeen, Scotland
Focus: Agricultural AI, RegTech Automation, SME AI Solutions
