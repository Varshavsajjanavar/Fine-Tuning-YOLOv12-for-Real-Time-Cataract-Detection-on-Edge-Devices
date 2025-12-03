Fine-Tuning YOYOv12 for Real-Time Cataract Detection on Edge Devices

This repository presents a complete pipeline for training, optimizing, and deploying a real-time cataract detection system using YOLOv12. The model is fine-tuned on a cataract detection dataset and further optimized for mobile inference using TensorFlow Lite.
A severity-classification module is also included to classify cataracts as Mild, Moderate, or Severe.

The system is designed for fast, offline, on-device medical screening in rural clinics, telemedicine setups, and low-resource environments.

⭐ Key Highlights

Fine-tuned YOLOv12 with Area Attention & FlashAttention

Real-time detection (~15 ms per frame)

On-device deployment using TFLite

Automated cropping of detected cataract regions

Severity grading using ResNet18 classifier

Dataset loading through Roboflow API

Fully reproducible training notebook

Supports both GPU training and CPU inference

🚀 Model Workflow
1. YOLOv12 Fine-Tuning

Data loaded from Roboflow

Preprocessing (resize, normalize, augment)

Trained for 50 epochs

Achieves high mAP and precision

2. Detection & Region Cropping

YOLOv12 detects cataract-affected regions.
Bounding box crops are automatically extracted for further classification.

3. Severity Classification

A lightweight ResNet18 model predicts:

Severe

Moderate

Mild

Normal

This enables actionable medical grading.

4. TFLite Optimization

Static int8 quantization

Operator fusion

ARM-optimized kernels

Suitable for smartphone deployment

Performance

| Metric         | YOLOv12 Original | YOLOv12 Optimized (TFLite) |
| -------------- | ---------------- | -------------------------- |
| Model Size     | 30 MB            | 19 MB                      |
| Inference Time | 11 ms            | 15 ms                      |
| F1-Score       | 91%              | 83%                        |
| mAP@0.5        | 93%              | 86%                        |
| Precision      | 92%              | 85%                        |
| Recall         | 90%              | 81%                        |

Technologies Used

| Component         | Technology                     |
| ----------------- | ------------------------------ |
| Detection         | YOLOv12                        |
| Attention         | FlashAttention, Area Attention |
| Classifier        | ResNet18                       |
| Optimizer         | PyTorch + Ultralytics          |
| Mobile Deployment | TensorFlow Lite                |
| Visualization     | Supervision                    |
| Dataset Loader    | Roboflow API                   |
| Optional App      | Flutter                        |

