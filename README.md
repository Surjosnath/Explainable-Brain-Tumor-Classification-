# Explainable Brain Tumor Classification using ResNet50 and Grad-CAM

Brain tumors are among the most critical neurological disorders, where early and accurate diagnosis plays a vital role in improving patient outcomes. Magnetic Resonance Imaging (MRI) is widely used for brain tumor detection due to its ability to capture detailed soft tissue information. However, manual MRI analysis can be time-consuming and highly dependent on radiologist expertise.

This project presents an Explainable AI-based Computer-Aided Diagnosis (CAD) system for multi-class brain tumor classification using deep learning and MRI scans. The framework leverages transfer learning with the ResNet50 architecture for feature extraction and classification, combined with Grad-CAM explainability to improve transparency and interpretability in medical AI systems.

The project includes MRI preprocessing, brain-region cropping, data augmentation, model evaluation using multiple classification metrics, and Grad-CAM visualization to highlight tumor regions influencing model predictions.

---

# Problem Statement

Brain tumors are abnormal growths of cells inside the brain and can be broadly categorized into malignant and benign tumors. Accurate and early diagnosis is essential for effective treatment planning and patient survival.

Traditional diagnosis through manual MRI analysis is susceptible to:
- human error,
- radiologist fatigue,
- and variability in expertise.

This project focuses on developing an explainable deep learning framework capable of classifying:
- Glioma Tumor
- Meningioma Tumor
- Pituitary Tumor
- No Tumor

using MRI images and transfer learning techniques.

---

# Proposed Framework

The proposed framework follows the pipeline below:

1. Dataset Acquisition  
2. MRI Preprocessing and Brain Cropping  
3. Data Augmentation  
4. ResNet50 Transfer Learning  
5. Model Training and Evaluation  
6. Explainability using Grad-CAM  

The framework emphasizes both:
- high classification performance,
- and trustworthy AI through explainability.

---

# Dataset Acquisition

The project uses the Brain Tumor MRI Dataset from Kaggle.

The dataset contains MRI images belonging to four categories:
- Glioma Tumor
- Meningioma Tumor
- Pituitary Tumor
- No Tumor

## Dataset Link
Brain Tumor MRI Dataset

---

# Image Preprocessing

MRI preprocessing plays a crucial role in improving model performance and reducing irrelevant noise.

The preprocessing pipeline includes:

## 1. Brain Region Cropping

MRI scans often contain unnecessary black background regions.

To focus the model on medically relevant features:
- contour detection,
- thresholding,
- erosion and dilation,
- and extreme point extraction

were used to crop the brain region from MRI scans.

### Benefits
- removes background noise,
- improves feature extraction,
- reduces computational complexity.

---

## 2. Image Resizing

All MRI images were resized to a fixed input size compatible with ResNet50:

`224 × 224`

This standardizes the input dimensions for model training.

---

## 3. Normalization

Pixel values were normalized to improve convergence and stabilize training.

---

# Data Augmentation

Medical imaging datasets are often limited in size, which increases the risk of overfitting.

To improve model generalization, data augmentation techniques were applied to the training set, including:
- rotation,
- zoom,
- horizontal flipping,
- width/height shifting.

Data augmentation artificially increases dataset diversity and improves robustness to unseen data.

---

# Model Architecture

The project uses:

## ResNet50

through transfer learning.

## Why ResNet50?

ResNet50 was selected because:
- it performs strongly on image classification tasks,
- residual connections reduce vanishing gradient problems,
- transfer learning improves performance on smaller datasets,
- and it integrates effectively with Grad-CAM explainability.

---

# Transfer Learning

Instead of training a CNN from scratch, pretrained ImageNet weights were used as feature extractors.

## Advantages
- faster convergence,
- reduced computational cost,
- improved performance on limited medical datasets.

---

# Hyperparameter Configuration

| Hyperparameter | Value |
|---|---|
| Optimizer | Adam |
| Learning Rate | 1e-4 |
| Batch Size | 32 |
| Epochs | 25 |
| Dropout | 0.4 |
| Activation Function | Softmax |
| Loss Function | Categorical Crossentropy |

---

# Performance Evaluation

The model was evaluated using:
- Accuracy
- Confusion Matrix
- ROC Curves
- AUC Scores
- Classification Report
- Precision
- Recall
- F1-Score

---

# Model Performance

| Model | Accuracy |
|---|---|
| ResNet50 (Without Augmentation) | 93.14% |
| ResNet50 (With Augmentation) | 97.4% |

The augmented ResNet50 model demonstrated better generalization and improved classification performance.

---

# ROC Curve Analysis

ROC Curves and AUC scores were used to evaluate:
- sensitivity,
- specificity,
- and class-wise separability.

This is particularly important in medical diagnosis systems where false negatives can have severe consequences.

---

# Confusion Matrix

The confusion matrix was used to analyze:
- correct classifications,
- misclassifications,
- and class-wise prediction behavior.

This helped identify which tumor categories were more challenging for the model.

---

# Explainability using Grad-CAM

## What is Grad-CAM?

Grad-CAM (Gradient-weighted Class Activation Mapping) is an explainability technique used to visualize the regions of an MRI scan influencing the model prediction.

Grad-CAM generates heatmaps highlighting important regions used by the CNN during classification.

## Benefits
- improves interpretability,
- increases trust in medical AI systems,
- helps visualize model attention regions.

---

# Why Explainability Matters

Deep learning models are often considered black-box systems, especially in healthcare applications.

In medical diagnosis, interpretability is critical because clinicians need to understand why a prediction was made.

Grad-CAM improves transparency by showing whether the model focuses on medically relevant tumor regions.

---

# Limitations

Although the project achieved strong performance, several limitations remain:
- The dataset size is relatively limited.
- MRI images originate from limited sources.
- The model may not generalize across hospitals or imaging devices.
- Grad-CAM improves interpretability but does not provide causal reasoning.
- Clinical validation by medical experts is still required.

---

# Future Improvements

Potential future improvements include:
- Fine-tuning additional ResNet50 layers
- Exploring EfficientNet architectures
- Integrating attention mechanisms
- Applying segmentation before classification
- Federated learning for privacy-preserving medical AI
- Multi-hospital validation datasets
- Advanced explainability methods

---

# Technologies Used

- Python
- TensorFlow / Keras
- OpenCV
- NumPy
- Matplotlib
- Scikit-learn
- Grad-CAM
- Kaggle Notebook

---

# Results

- Achieved 97.4% classification accuracy using ResNet50 with data augmentation
- Improved model interpretability using Grad-CAM explainability
- Successfully classified MRI scans into four tumor categories
- Demonstrated the importance of explainable AI in medical imaging systems

---

# Conclusion

This project demonstrates how transfer learning and explainable AI can be combined to develop an effective brain tumor classification framework using MRI scans.

By integrating ResNet50 with Grad-CAM visualization, the system achieves strong classification performance while improving transparency and interpretability in AI-assisted medical diagnosis.
