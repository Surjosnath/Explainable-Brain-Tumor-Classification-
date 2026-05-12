# MRI-Based Brain Tumor Classification using Deep Learning and Grad-CAM

## 📌 Overview

Brain tumors are among the most life-threatening neurological disorders, where early and accurate diagnosis plays a critical role in improving patient survival rates. Magnetic Resonance Imaging (MRI) is widely used for detecting brain abnormalities due to its superior soft-tissue imaging capability. However, manual MRI analysis can be time-consuming and prone to diagnostic errors caused by fatigue and inter-observer variability.

This project presents an Explainable AI-based Computer Aided Diagnosis (CAD) System for multi-class brain tumor classification using Deep Learning and Grad-CAM visualization techniques.

The framework utilizes multiple state-of-the-art Convolutional Neural Network (CNN) architectures with Transfer Learning to classify MRI scans into:

* Glioma Tumor
* Meningioma Tumor
* Pituitary Tumor
* No Tumor

To improve transparency and interpretability, Grad-CAM (Gradient-weighted Class Activation Mapping) is integrated to visualize the regions responsible for model predictions.

Additionally, a Streamlit-based web application is developed for real-time MRI image prediction.

---

# 🎯 Problem Statement

Brain tumors are caused by abnormal cell growth inside the brain. Tumors may be:

* Benign (non-cancerous)
* Malignant (cancerous)

Malignant tumors can become fatal depending on their location and growth rate. Therefore, timely and accurate diagnosis is essential.

The objective of this project is to build a Deep Learning-based system capable of accurately classifying brain MRI scans into different tumor categories while also providing explainable visual interpretations of predictions.

---

# 🚀 Proposed Framework

The proposed framework follows the pipeline below:

MRI Scan → Image Preprocessing → Data Augmentation → CNN-Based Transfer Learning Models → Performance Evaluation → Grad-CAM Visualization → Streamlit Deployment

---

# 📂 Dataset

The dataset used in this project is the Brain Tumor MRI Dataset obtained from Kaggle.

## Dataset Categories

The MRI images are classified into four categories:

| Class            | Description                             |
| ---------------- | --------------------------------------- |
| Glioma Tumor     | Tumor occurring in glial cells          |
| Meningioma Tumor | Tumor in meninges surrounding the brain |
| Pituitary Tumor  | Tumor in pituitary gland                |
| No Tumor         | Healthy MRI scan                        |

---

# 📊 Dataset Distribution

| Category         | Training | Validation | Testing  |
| ---------------- | -------- | ---------- | -------- |
| Glioma Tumor     | 1060     | 261        | 300      |
| Meningioma Tumor | 1072     | 267        | 306      |
| Pituitary Tumor  | 1158     | 299        | 300      |
| No Tumor         | 1279     | 316        | 405      |
| **Total**        | **4569** | **1143**   | **1311** |

---

# 🖼️ Image Preprocessing

Medical MRI images often contain unwanted noise and inconsistent dimensions. To improve model performance, multiple preprocessing techniques were applied.

## 1️⃣ Image Cropping

Cropping removes unnecessary background regions and helps the model focus on the brain area.

### Benefits

* Removes unwanted noise
* Reduces computational complexity
* Improves feature learning

---

## 2️⃣ Noise Removal using Bilateral Filter

Bilateral filtering smooths MRI images while preserving important edges and fine anatomical details.

### Why Bilateral Filtering?

* Removes noise effectively
* Preserves tumor boundaries
* Maintains edge information

---

## 3️⃣ Applying Colormap

Applying colormaps enhances image contrast and improves tissue differentiation, helping CNN models extract more meaningful features.

---

## 4️⃣ Image Resizing

All MRI images are resized to a fixed dimension before training.

### Benefits

* Standardizes model input
* Reduces memory usage
* Improves training consistency

---

# 🔄 Data Augmentation

Medical imaging datasets are often limited in size. To improve generalization and reduce overfitting, image augmentation techniques were applied using `ImageDataGenerator`.

## Augmentation Techniques

* Rotation
* Zoom
* Horizontal Flip
* Width Shift
* Height Shift
* Brightness Adjustment

### Benefits

* Increases dataset diversity
* Improves model robustness
* Prevents overfitting

---

# 🧠 Deep Learning Models Used

This project compares the performance of six Transfer Learning architectures:

* VGG19
* ResNet50
* InceptionV3
* Xception
* MobileNetV2
* NASNetLarge

These models were initialized with ImageNet pre-trained weights and fine-tuned for brain tumor classification.

---

# ⚙️ Hyperparameter Configuration

| Hyperparameter      | Value                    |
| ------------------- | ------------------------ |
| Learning Rate       | 1e-4                     |
| Batch Size          | 32                       |
| Epochs              | 25                       |
| Dropout             | 0.4                      |
| Optimizer           | Adam                     |
| Activation Function | Softmax                  |
| Loss Function       | Categorical Crossentropy |

---

# 📈 Model Performance

## Accuracy Comparison

| Model                           | Accuracy   |
| ------------------------------- | ---------- |
| ResNet50 (Without Augmentation) | 93.14%     |
| MobileNetV2                     | 95.15%     |
| VGG19                           | 97.18%     |
| NASNetLarge                     | 97.56%     |
| InceptionV3                     | 98.55%     |
| Xception                        | 98.63%     |
| ResNet50                        | **98.70%** |

---

# 📉 Evaluation Metrics

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix

These metrics provide comprehensive insights into classification performance across all tumor categories.

---

# 🔍 Grad-CAM Visualization

To improve explainability and transparency, Grad-CAM was used to visualize the regions of MRI scans influencing model predictions.

## Why Grad-CAM?

Deep learning models are often considered black-box systems. Grad-CAM helps interpret predictions by highlighting important regions inside MRI images.

### Benefits

* Improves trust in AI predictions
* Helps understand model decisions
* Useful for medical interpretability

The heatmap visualization highlights tumor regions responsible for the prediction.

---

# 🌐 Streamlit Web Application

A user-friendly Streamlit application was developed for real-time brain tumor prediction.

## Features

* Upload MRI scan
* Predict tumor category
* Display prediction confidence
* Generate Grad-CAM heatmap visualization

---

# 🛠️ Technologies Used

| Technology         | Purpose                 |
| ------------------ | ----------------------- |
| Python             | Programming Language    |
| TensorFlow / Keras | Deep Learning Framework |
| OpenCV             | Image Processing        |
| NumPy              | Numerical Computation   |
| Matplotlib         | Visualization           |
| Scikit-learn       | Evaluation Metrics      |
| Streamlit          | Web Application         |
| Grad-CAM           | Explainable AI          |

---

# 📁 Project Structure

```bash
├── Dataset/
├── Preprocessed_Images/
├── Models/
├── GradCAM_Results/
├── Streamlit_App/
├── MRI_Based_Tumor_Classification_with_DL_&_Grad_CAM.ipynb
├── requirements.txt
└── README.md
```

---

# ▶️ How to Run the Project

## 1️⃣ Clone the Repository

```bash
git clone <your-github-repo-link>
cd <repository-name>
```

---

## 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 3️⃣ Run the Jupyter Notebook

```bash
jupyter notebook
```

Open:

```bash
MRI_Based_Tumor_Classification_with_DL_&_Grad_CAM.ipynb
```

---

## 4️⃣ Run the Streamlit App

```bash
streamlit run app.py
```

---

# 📌 Key Highlights of the Project

✅ Multi-class brain tumor classification
✅ Transfer learning with six CNN architectures
✅ MRI image preprocessing pipeline
✅ Data augmentation for improved generalization
✅ Grad-CAM explainability integration
✅ High classification accuracy (~98.7%)
✅ Streamlit-based deployment
✅ Medical AI + Explainable AI integration

---

# 🔮 Future Scope

Possible future improvements include:

* Federated Learning for privacy-preserving training
* Blockchain integration for secure medical AI
* 3D MRI analysis
* Transformer-based architectures
* Multi-modal medical imaging
* Clinical deployment and validation

---

# 📚 Conclusion

This project demonstrates the effectiveness of Transfer Learning and Explainable AI for brain tumor classification using MRI scans. The integration of Grad-CAM enhances transparency, making the system more interpretable and clinically useful.

Among all models, ResNet50 achieved the highest accuracy of 98.70%, showing strong capability in extracting discriminative tumor features from MRI images.

The developed framework can serve as a valuable Computer Aided Diagnosis (CAD) tool for assisting radiologists in accurate and efficient brain tumor detection.

---

# 👨‍💻 Author

**Surjosnath Guha Thakurta**
M.Sc. Computer Science
Deep Learning | Computer Vision | Explainable AI | Medical Imaging
