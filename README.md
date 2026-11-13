# NeuroBRIDGE
Explanation-grounded dual-attention framework for EEG biomarker discovery in Parkinson's and Alzheimer's disease

## Overview
This study proposes NeuroBRIDGE (Bidirectional Recurrent Interpretable Dual-attention for Grounded EEG), an explainable deep learning framework for classifying Parkinson's disease (PD) and Alzheimer's disease (AD) from resting-state EEG. Each EEG segment is converted into an ordered sequence of channel-wise descriptors: delta, theta, alpha, beta, and gamma band power, Shannon entropy, and zero-crossing count. A bidirectional recurrent encoder models dependencies along this sequence, and a dual-axis attention module scores both the descriptor tokens and the latent encoder channels. Shapley additive explanations (SHAP) and XGBoost permutation importance cross-check the model's decisions. Two-sample t-tests and Cohen's d quantify class differences in attention profiles, so that the identified descriptors can be compared with known neurophysiological EEG markers of PD and AD.

# NeuroBRIDGE notebooks
This repository contains the notebooks used to preprocess the EEG data, train NeuroBRIDGE, and generate the explanation analyses for each cohort.

## Files
1. **NeuroBRIDGE_PD.ipynb**: The complete pipeline for PD versus healthy controls on the UC San Diego resting-state EEG dataset. It covers data loading, band-pass filtering, segmentation, descriptor extraction, NeuroBRIDGE training and evaluation, SHAP analysis, attention analysis with t-tests and Cohen's d, XGBoost permutation importance, and PCA.
2. **NeuroBRIDGE_AD.ipynb**: The same pipeline for AD versus cognitively normal participants on the AHEPA EEG dataset. The frontotemporal dementia group is excluded.

The notebooks were developed in Google Colab (Python 3.11, GPU runtime). Install all dependencies (numpy, pandas, scipy, matplotlib, seaborn, scikit-learn, tensorflow, mne, shap, xgboost, librosa) before running them, and set the dataset paths in the loading cells to your local copies.

# Citation
Citation details will be added once the article is published.

# Publicly available datasets
- UC San Diego resting-state EEG data from patients with Parkinson's disease (Jackson et al., 2019): DOI 10.1523/ENEURO.0151-19.2019, Data: https://openneuro.org/datasets/ds002778
- AHEPA scalp EEG recordings of Alzheimer's disease, frontotemporal dementia and healthy subjects (Miltiadous et al., 2023): DOI 10.3390/data8060095, Data: https://openneuro.org/datasets/ds004504
