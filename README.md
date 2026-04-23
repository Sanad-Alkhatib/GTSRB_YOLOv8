# 🚦 Traffic Sign Classification using YOLOv8

## Project Overview
This project focuses on building a deep learning model for **traffic sign image classification** using the YOLOv8 architecture.  
The model is trained to recognize different traffic signs such as speed limits, stop signs, yield signs, and other road signals.

Unlike traditional object detection, this project uses **YOLOv8 classification mode**, where the model assigns a label to the entire image.

---

## Dataset

The dataset used in this project is the German Traffic Sign Recognition Benchmark (GTSRB), which is publicly available on Kaggle.

Source:
https://www.kaggle.com/datasets/meowmeowmeowmeowmeow/gtsrb-german-traffic-sign

This dataset contains images of German traffic signs classified into multiple categories such as speed limits, stop signs, yield signs, and other road signals.

## Dataset Details:
Total number of classes: 43
Image format: RGB images
Resolution: Varying sizes (resized during preprocessing)

##Purpose:

The dataset is used for multi-class image classification to train a YOLOv8 model capable of recognizing traffic signs in real-world scenarios.

---

##  Dataset Structure
The dataset is organized in the following format:   
dataset/  
├── train/  
│ ├── class_1/  
│ ├── class_2/  
│ └── ...  
├── val/  
│ ├── class_1/   
│ ├── class_2/  
│ └── ...    

Each folder represents a traffic sign category.

---

##  Technologies Used
- Python
- Google Colab
- OpenCV (cv2)
- Matplotlib
- Ultralytics YOLOv8
- Deep Learning (Transfer Learning)

---

##  Methodology

### 1. Data Preprocessing
- Dataset extracted from ZIP file stored on Google Drive
- Split into:
  - 80% training
  - 20% validation
- Organized into class-based folders

---

### 2. Data Visualization
- Random images from each class were displayed
- Image shapes were printed to understand dataset consistency

---

### 3. Image Augmentation
To improve model generalization, manual augmentation was applied:
- Rotation (15 degrees)
- Grayscale conversion

These transformations simulate variations that help the model generalize better.

YOLO also applies **automatic augmentation during training** such as:
- flipping
- scaling
- brightness adjustment

---

### 4. Model Training
A pre-trained YOLOv8 Nano classification model was used:

'''python
model = YOLO('yolov8n-cls.pt')
 
Training configuration:  
- Epochs: 10  
- Image size: 224x224  
- Transfer Learning enabled  

---

## Model Evaluation (Updated)

After training the YOLOv8 classification model on the GTSRB dataset, the model was evaluated on the validation set to measure its performance.

### Evaluation Results:
- Top-1 Accuracy: 99.37%
- Top-5 Accuracy: 99.98%
- Final Fitness Score: 0.9968

These results indicate that the model achieved very high classification performance, successfully distinguishing between 43 traffic sign classes.

### Training Behavior:

During training over 10 epochs, the model showed consistent improvement:
- Initial accuracy started around 84.5%
- Rapid improvement after epoch 2
- Stabilized above 99% accuracy from epoch 6 onward
- Final model converged with very low loss

This confirms that transfer learning with YOLOv8n-cls is highly effective for traffic sign classification tasks.

###  Evaluation Outputs

The model automatically generated the following evaluation visualizations:

#### 🔹 Confusion Matrix
<img width="3000" height="2250" alt="image" src="https://github.com/user-attachments/assets/6a84dfab-15a0-4044-b7a7-ad4c4f3dff49" />

#### 🔹 Training & Validation Curves
<img width="1200" height="1200" alt="image" src="https://github.com/user-attachments/assets/a0ea111a-c4dd-43cf-bf51-9b217e04f950" />

---

## Inference (Prediction)

The trained model was tested on an unseen traffic sign image (stop.jpg) to evaluate real-world performance.

### Prediction Result:
- Predicted Class: Stop Sign
- Confidence Score: 0.9783 (97.83%)

The model correctly identified the image as a Stop sign, demonstrating strong generalization ability on unseen data.

---

## Key Results (Final Updated Version)
-  Achieved very high accuracy (99%+) using YOLOv8 classification
-  Fast training on GPU (T4 GPU via Google Colab)
-  Effective transfer learning from pretrained weights (yolov8n-cls.pt)
-  Strong convergence within only 10 epochs
-  Reliable real-world predictions with high confidence

---

## Conclusion (Improved Insight)

This project demonstrates the effectiveness of YOLOv8 for image classification tasks, even though it is originally designed for object detection.

Using transfer learning and a well-structured dataset, the model achieved state-of-the-art performance on traffic sign classification, 
making it suitable for real-world autonomous driving and intelligent transportation systems.





