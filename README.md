# 🐾 Object Detection with YOLOv8  

This project implements **YOLOv8** for object detection and classification of cats and dogs using the **Oxford-IIIT Pet Dataset**. The framework supports **training, evaluation, and inference** across images, videos, and live camera streams.  



## 🔧 Tools & Frameworks  
- Python 3.10+  
- Google Colab / Jupyter Notebook  
- YOLOv8 (Ultralytics)  
- OpenCV  
- Pandas, NumPy, Matplotlib  
- Scikit-learn (for dataset splitting)  



## 📌 Project Workflow  

### 1. Dataset Preparation  
- Used the **Oxford-IIIT Pet dataset** (cats and dogs).  
- Converted annotations from **XML to YOLO format**.  
- Split dataset into **training (80%)** and **validation (20%)**.  

### 2. Model Development & Training  
- Conducted experiments with different YOLOv8 model variants and parameters:  
  - **Architecture:** YOLOv8n (nano) vs YOLOv8s (small)  
  - **Training duration:** 30 vs 50 epochs  
  - **Image size:** 320 vs 640 resolution  

### 3. Evaluation  
- Models assessed on **mAP@0.5**, **mAP@0.5:0.95**, **precision**, and **recall**.  
- Compared **trade-offs between accuracy, speed, and resource requirements**.  

### 4. Inference & Visualization  
- Ran predictions on **images and videos**.  
- Generated **visualizations** of correct and incorrect detections.  
- Implemented **real-time inference** on custom videos.  



## 📊 Observations  

### Architecture Differences  
- **YOLOv8n (30 epochs):** Competitive accuracy with **low computational cost**, suitable for lightweight deployment.  
- **YOLOv8s (30 epochs):** Higher accuracy but more resource-intensive, showing that **larger models are not always required**.  

### Training Duration  
- **YOLOv8s (50 epochs):** Achieved the **best balance** of precision, recall, and mAP, making it suitable for high-accuracy applications.
 
- **YOLOv8s (30 epochs):** Delivered strong results with shorter training time, proving that **extended training not always necessary**.  

### Input Resolution Trade-Offs  
- **YOLOv8s (30 epochs, imgsz=320):** Faster training and inference but lower recall. Recommended only where real-time speed is prioritized over accuracy.   



## ⚡ Challenges  

- **Training Time:** Each run required hours on Colab’s free GPU tier, making experimentation difficult. This led to upgrading to Colab Pro for access to higher-performance GPUs.
- **Incorrect Predictions in Low Light:** The model occasionally misclassified objects under poor lighting conditions, highlighting the need for **data augmentation** and **robust preprocessing**.  
- **Resource Constraints:** Larger models demanded more **memory and compute power**, which limited experimentation with higher architectures.



## 📖 References  
- 📂 [Oxford-IIIT Pet Dataset](https://public.roboflow.com/object-detection/oxford-pets)  
- 📘 [YOLOv8 Documentation](https://docs.ultralytics.com/)  



## 🚀 How to Run (Google Colab)  

This project is designed to run in **Google Colab** with Google Drive integration.  
You can upload the Oxford Pet dataset to your Google Drive and mount it in Colab using:  

```python
from google.colab import drive
drive.mount('/content/drive')
```

The folder structure in your Google Drive should be:
```
Object_Detection/
│── Object_detection_catsDogs.ipynb
│── dataset/
│    ├── train/
|    └── test/
│── data.yaml
```
The data.yaml file should define train/val paths and class labels for YOLOv8.
