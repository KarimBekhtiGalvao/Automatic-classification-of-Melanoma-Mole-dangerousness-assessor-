# Automatic classification of Melanoma-Mole dangerousness assessor

Classification using: Neural Network, Bayesian Classifier, Logistic Regression, SVMs
TB3 : Traitement d'image
**author:** KarimBekhtiGalvao
Karim Bekhti Galvao This project has been done in the context of the class "Introduction to Image Processing" in Mines Saint-Etienne (EMSE) (12/2023)
---

## Project Overview

The goal of this project is to automatically classify skin lesions as melanoma or non-melanoma. We extract key features from skin images based on the ABCDE rule:  

- **A**symmetry  
- **B**order irregularity  
- **C**olor variegation  
- **D**iameter  
- **E**volution (not used in this project)

We then apply multiple machine learning models to predict the nature of each lesion.

---

## Database

The dataset consists of:

- Original lesion images (`*.jpg`)  
- Segmented masks (`*_seg.png`)  
- Superpixel images (`*_sup.png`)  

**Image loading example:**

## Database

The dataset includes:

- Original lesion images  
- Segmented masks  
- Superpixel images  

![ISIC_0000000](https://github.com/user-attachments/assets/23193b66-625b-4918-874e-303635fb46e0)
<img width="1022" height="767" alt="ISIC_0000000_segmentation" src="https://github.com/user-attachments/assets/35938705-1d02-4eb9-b742-4491a85f4d48" />
<img width="1022" height="767" alt="ISIC_0000000_superpixels" src="https://github.com/user-attachments/assets/8a471f26-88bd-428f-b1e1-8717d7f9fc6d" />

---

## Feature Extraction

### Asymmetry

Asymmetry is measured by comparing the lesion image with its rotated version to determine how much the shape deviates from symmetry.

### Border Irregularity

The irregularity of the lesion border is quantified by comparing the actual perimeter with that of a circle of equivalent area.

### Color Features

Color descriptors include the mean and variance of colors within the lesion area.

### Textural Features

Texture is captured using wavelet transforms and Local Binary Patterns (LBP) to detect variations within the lesion.

### Shape Descriptors

Additional descriptors include:

- Eccentricity  
- Perimeter  
- Extent  
- Minor and major axes  
- Equivalent diameter  
- Solidity  

These help to capture the geometric properties of the lesion.

---

## Machine Learning Models

Four models were trained to classify lesions:

1. **Bayesian Classifier**  
2. **Support Vector Machine (SVM)**  
3. **Logistic Regression**  
4. **Neural Network**  

The models are evaluated on metrics such as accuracy, recall, F-score, and AUC.

---

## Results

Evaluation of the models shows the following:

| Metric       | Neural Network | SVM  | Bayesian Model | Logistic Regression |
|--------------|----------------|------|----------------|-------------------|
| Accuracy     | 0.75           | 0.7  | 0.68           | 0.68              |
| Recall       | 0.77           | 0.66 | 0.71           | 0.71              |
| F-score      | 0.78           | 0.79 | 0.72           | 0.72              |
| AUC          | 0.74           | 0.66 | 0.68           | 0.68              |

<img width="386" height="278" alt="image" src="https://github.com/user-attachments/assets/438dc7b5-5f26-463c-bba0-30c2bc71e477" />
Example of result obtained

---
## Conclusion

- The **Neural Network** produced the best results for melanoma detection.  
- Combining ABCDE-based features with texture and shape descriptors improves model performance.  
- Feature engineering is critical to achieving high accuracy in lesion classification.

---

