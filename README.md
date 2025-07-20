# 🧠 Radiological and Biological Dictionary of Radiomics Features (BM1.0)
**Addressing Understandable AI Issues in Personalized Breast Cancer**

[📄 Paper Link](https://github.com/MohammadRSalmanpour/Radiological-and-Biological--Radiomics-Feature--based-Dictionary-Version-BM1.0)

## 📌 Overview
This repository contains the code, feature dictionaries, and supplementary materials for the paper:

**"Radiological and Biological Dictionary of Radiomics Features: Addressing Understandable AI Issues in Personalized Breast Cancer; Dictionary Version BM1.0"**

Breast cancer radiomics models often face challenges in clinical adoption due to their "black-box" nature. Our work introduces a **dual-dictionary framework** that translates quantitative radiomic features (RFs) into **clinically meaningful BI-RADS descriptors**, bridging the gap between AI-driven insights and radiologist intuition.

---

## 🧪 Key Contributions
- 📚 **CIFID**: *Clinically-Informed Feature Interpretation Dictionary* mapping 56 radiomic features to BI-RADS descriptors based on expert consensus and literature.
- 📊 **DDFID**: *Data-Driven Feature Interpretation Dictionary* for 52 additional features based on SHAP analysis of classification results.
- 🤖 **Explainable AI Pipeline** for classifying triple-negative breast cancer (TNBC) vs. non-TNBC using interpretable machine learning and multi-cohort DCE-MRI data.
- 🏥 Clinical interpretability of RFs aligned with descriptors such as *Shape*, *Margin*, and *Internal Enhancement*.

---

## 🗂️ Dataset
We utilized DCE-MRI scans and ROI segmentations from six breast cancer cohorts:
- ISPY1
- ISPY2
- DUKE
- NACT
- TCGA-BRCA
- Advanced-MRI-Breast-Lesions (AMBL)

> Total Patients: **1549**

Each subject's data included:
- DCE-MRI (late post-contrast)
- Tumor ROI segmentation
- Molecular subtype labels (TNBC, Luminal A/B, HER2-enriched)

---

## 🧰 Methodology

### 🔄 Preprocessing
- N4 bias field correction  
- Resampling to uniform voxel spacing  
- Z-score intensity normalization  

### 🧬 Feature Extraction
- 108 standardized features from **PyRadiomics**, including:
  - First-order
  - Shape
  - GLCM, GLRLM, GLSZM, GLDM, NGTDM

### 🧠 Classification Pipeline
- 27 Feature Selection Algorithms (e.g., Chi2, Mutual Info, LASSO, ANOVA)
- 27 Classifiers (e.g., Extra Trees, XGBoost, SVM, RuleFit, MLP)
- 5-fold cross-validation and external validation
- Model interpretation using **SHAP** values

---

## 📈 Performance
- 🔥 Best classifier: **Extra Trees**
  - Validation Accuracy: **0.83**
  - External Test Accuracy: **0.69**

- 🔍 SHAP-driven insights linked to BI-RADS semantics:
  - High *Sphericity* → Round/Oval shape → TNBC
  - Low *Busyness* → Homogeneous enhancement → TNBC

---

## 📖 Dictionaries

### 📘 CIFID
A literature-driven mapping between RFs and BI-RADS descriptors. Includes shape-, margin-, and IE-related features.

### 📙 DDFID
A SHAP-guided interpretation of RFs not covered in CIFID, built from model behavior and validated against known imaging phenotypes of TNBC and non-TNBC.
