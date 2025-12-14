# Cucumber Disease Recognition (CSE366 Project)
Implementation using Machine Learning and CNN.

🔗 Kaggle Notebook: [View the Code on Kaggle](https://www.kaggle.com/code/mubashirjawad01/cucumber-disease-recognition)

#  Cucumber Diseases Recognition Using Deep Learning

This repository presents a comprehensive  deep learning–based cucumber disease recognition system, developed as project .The project explores both transfer learning models and a custom CNN architecture, combined with statistical evaluation and visual explainability using Grad-CAM.


##  Project Objectives

* Automatically identify **8 classes** of cucumber diseases and healthy samples from images
* Compare multiple **CNN architectures** for performance analysis
* Design and train a **custom CNN model** from scratch
* Apply **statistical significance testing (paired t-test)** for fair comparison
* Use **Grad-CAM** to visually interpret model decisions


##  Dataset

* Dataset Name: Cucumber Diseases Recognition Dataset
* Source: Kaggle
* Image Type: RGB leaf and fruit images
* Total Classes (8):

  * Anthracnose
  * Bacterial Wilt
  * Belly Rot
  * Downy Mildew
  * Fresh Cucumber
  * Fresh Leaf
  * Gummy Stem Blight
  * Pythium Fruit Rot

### Data Split

* Training: 70%
* Validation: 15%
* Testing: 15%

### Data Augmentation

To reduce overfitting and improve generalization:

* Random horizontal & vertical flip
* Random rotation (±20°)
* Random affine translation
* Color jitter (brightness, contrast, saturation)



## Models Implemented

### Transfer Learning Models

* VGG-16
* ResNet-50
* EfficientNet-B0

Pretrained on ImageNet and fine-tuned on the cucumber dataset.

###  Custom CNN Model

A lightweight but deep CNN designed specifically for this task:

* 5 convolutional blocks
* Progressive channel expansion: 32 → 64 → 128 → 256 → 512
* Batch Normalization + LeakyReLU
* MaxPooling after each block
* Global Average Pooling to reduce parameters
* Fully connected classifier with Dropout

**Total Parameters:** ~1.83M



## ⚙️ Training Configuration

* Image Size: 224 × 224
* Batch Size: 32
* Optimizer: AdamW
* Learning Rate: 0.0005
* Loss Function: CrossEntropyLoss with label smoothing (0.1)
* Scheduler: ReduceLROnPlateau
* Early Stopping: Enabled



## 📊 Results Summary

### Custom CNN Performance (Test Set)

* Overall Accuracy: 82%
* Macro F1-score: 0.83

| Class             | F1-score |
| ----------------- | -------- |
| Anthracnose       | 0.64     |
| Bacterial Wilt    | 0.87     |
| Belly Rot         | 0.93     |
| Downy Mildew      | 0.76     |
| Fresh Cucumber    | 0.95     |
| Fresh Leaf        | 0.79     |
| Gummy Stem Blight | 0.68     |
| Pythium Fruit Rot | 0.98     |

EfficientNet-B0 achieved the best overall accuracy among all models.



## 📈 Statistical Analysis

* Method: Paired two-tailed t-test
* Purpose: Compare model performances fairly using identical data splits
* Outcome: Performance differences between models are statistically significant (p < 0.05)



##  Model Explainability (Grad-CAM)

Grad-CAM was used to visualize important image regions influencing predictions:

* Highlights infected areas of leaves/fruits
* Confirms model focuses on disease-specific patterns
* Improves interpretability and trust in predictions



## 📁 Repository Structure


├── notebooks/              # Model training and evaluation notebooks
├── custom_cnn/             # Custom CNN implementation
├── grad_cam/               # Grad-CAM visualization code
├── results/                # Accuracy, plots, confusion matrices
├── statistical_analysis/   # Paired t-test analysis
├── README.md               # Project documentation




##  How to Run

1. Clone the repository

```bash
git clone https://github.com/Muhtasim33/Cucumber-Diseases-Recognition-Dataset_CSE366_Project.git
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Run notebooks or scripts for training and evaluation



##  Tools & Technologies

* Python
* PyTorch
* Torchvision
* Scikit-learn
* Matplotlib & Seaborn
* Grad-CAM



## Authors

KM. Sakif Muhtasim
Mubashir Jawad
Sonia Bente Siraj
Sumaiya Binte Naser

Department of Computer Science & Engineering,East West University.
