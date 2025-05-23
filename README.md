AI-Based Intrusion Detection System

This repository contains an AI-based intrusion detection module developed for a thesis project focused on enhancing cybersecurity in unprotected communication channels. The system leverages machine learning to detect malware based on behavioral data from the CIC-MalMem2022 dataset.

Features
Classification models: LightGBM, Random Forest, SVM, and KNN
Feature importance analysis using SHAP
Trained on the CIC-MalMem2022 dataset
Real-time prediction capability (sub-0.01s inference time with LightGBM)
Perfect or near-perfect classification results across key metrics

Files
ai_based_detection_module.ipynb — Main notebook with full training, evaluation, and SHAP explainability.

How to Run
1. Download the dataset:
The system uses the CIC-MalMem2022 dataset from the Canadian Institute for Cybersecurity.
Place the dataset files in a folder named data/ in the project root.

2. Run the notebook:
   jupyter notebook ai_based_detection_module.ipynb

Disclaimer
This project is intended for academic and research use only. It is not production-ready and should not be deployed in live systems without further testing and validation.


