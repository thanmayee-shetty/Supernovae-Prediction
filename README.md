# Multimodal Supernova Progenitor Prediction

Paper: [View Paper](./supernova_springer.pdf)

---

## Overview
This project presents a multimodal machine learning framework to predict whether a Red Supergiant (RSG) star is likely to explode as a Type II supernova.

Unlike traditional approaches that focus on post-explosion observations, this work estimates pre-explosion likelihood using:
- Pre-explosion astronomical imaging
- Stellar catalog data

The model outputs a probability score representing the likelihood of core collapse.

---

## Key Idea
The approach combines:
- Deep learning-based image embeddings
- Astrophysical tabular features

This fusion enables the model to capture both morphological characteristics and physical stellar properties such as temperature, luminosity, and extinction.

---

## Architecture / Pipeline

1. Image Processing
   - Pre-explosion images from Pan-STARRS1
   - Processed using ResNet-18
   - Output: 512-dimensional feature embeddings

2. Tabular Data Processing
   - Stellar parameters from Gaia DR3 and 2MASS
   - Missing value imputation and feature scaling

3. Feature Fusion
   - Concatenation of image and tabular features into a unified representation

4. Model Training
   - Random Forest classifier with PCA
   - Outputs a calibrated supernova probability score

---

## Dataset

The dataset consists of:
- Confirmed supernova progenitors (positive samples)
- High-risk red supergiants
- Normal red supergiants (negative samples)

Total size: approximately 986 samples with multimodal features.

---

## Results

The multimodal model outperforms single-modality baselines:

- Accuracy: ~0.90  
- F1 Score: ~0.88  
- AUC: ~0.91  

These results indicate improved classification performance and better-calibrated probability estimates.

---

## Key Contributions

- A framework for pre-explosion supernova prediction
- Integration of imaging and tabular astrophysical data
- Interpretable probability-based predictions
- A method for prioritizing observational targets

---

## Tech Stack

- Python  
- PyTorch  
- Scikit-learn  
- Astropy  

---

## Applications

- Early identification of supernova candidates  
- Astronomical observation prioritization  
- Data-driven astrophysics research  

---

## Future Work

- Incorporating temporal (time-series) data  
- Exploring advanced deep learning architectures  
- Expanding datasets with additional surveys  
- Developing early-warning systems for stellar explosions  

---

## Usage

```bash
git clone https://github.com/thanmayee-shetty/supernova-prediction.git
cd supernova-prediction
pip install -r requirements.txt
