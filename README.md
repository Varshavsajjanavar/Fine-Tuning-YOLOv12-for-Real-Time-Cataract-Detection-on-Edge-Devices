# Fine-Tuning YOLOv12 for Real-Time Cataract Detection on Edge Devices

This repository presents a complete, end-to-end system for real-time cataract detection using the YOLOv12 architecture. The model is optimized for mobile and edge devices, supports offline inference, and includes an additional severity-classification module for grading cataracts. The full workflow is demonstrated inside the included notebook.

---

## 1. Objective

The goal of this project is to build a fast, lightweight, and accurate cataract detection system capable of running entirely on-device without requiring cloud or GPU access. The system supports:

- Real-time cataract detection using YOLOv12  
- Automatic region-of-interest extraction  
- Cataract severity grading (Mild, Moderate, Severe, Normal)  
- Deployment-ready TensorFlow Lite model for smartphones  

This solution is designed for low-resource medical environments such as rural clinics, health camps, and telemedicine platforms.

---

## 2. Key Features

- Fine-tuned YOLOv12 detection model  
- Area Attention, FlashAttention, and R-ELAN enhancements  
- Efficient 416×416 medical image pipeline  
- Automated cropping of detected cataract regions  
- ResNet18-based severity classifier  
- TFLite quantized model for Android devices  
- Fully reproducible workflow inside the notebook  

---

## 3. Architecture

Fundus Image → YOLOv12 Detection → ROI Cropping → ResNet18 Classifier → Severity Score


### Detection  
- YOLOv12s architecture  
- Uses Area Attention for improved global context  
- FlashAttention provides fast attention computation  
- R-ELAN enhances feature aggregation efficiency  

### Severity Classification  
- Lightweight ResNet18  
- Predicts: Mild, Moderate, Severe, Normal  

---

## 4. Dataset

- Collected from Roboflow dataset “Cataract Finder”  
- YOLO-format annotations  
- All images resized to 416×416  
- Includes standard medical image preprocessing:  
  - Contrast enhancement  
  - Normalization  
  - Augmentation (flip, rotation)  

The entire dataset preparation pipeline is inside the notebook.

---

## 5. Performance Summary

| Model | Size | mAP@0.5 | Latency | Deployment |
|-------|------|----------|---------|------------|
| YOLOv12s FP32 | 30 MB | 93% | 11 ms | GPU |
| YOLOv12s TFLite int8 | 19 MB | 86% | 15 ms | Android CPU |

The optimized model maintains strong accuracy while enabling fully offline, real-time mobile inference.

---

## 6. Applications

This system is intended for practical, real-world medical screening:

- Rural primary healthcare centers  
- Eye screening camps  
- Telemedicine platforms  
- School or community health programmes  
- Mobile-based diagnostic tools  
- Early detection and triaging  

---

## 7. Deployment

The project includes:

- A fine-tuned YOLOv12 model  
- A TFLite-optimized model for smartphones  
- A severity classifier trained on cropped cataract regions  
- A single notebook demonstrating the full pipeline  

The model can be integrated into:

- Android (Kotlin/Java)  
- Flutter mobile applications  
- Raspberry Pi  
- Jetson Nano  

---

This repository contains the fully executable notebook for training, inference, evaluation, and deployment of the cataract detection system.
