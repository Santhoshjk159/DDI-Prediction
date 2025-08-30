DDI Prediction Using Molecular Fingerprints
Overview
This project presents a machine learning framework to predict drug-drug interactions (DDIs) among gastrointestinal and metabolic drugs using molecular fingerprints and physicochemical descriptors. Multiple models were benchmarked; LightGBM achieved the best results (Accuracy: 90.96%, ROC-AUC: 0.962), further improved via hybrid ensemble. Key model insights are provided using SHAP analysis for interpretability.

Features
Predicts DDIs from drug structure and molecular properties

Models: LightGBM, XGBoost, Random Forest, CatBoost, others

SMOTE and class weighting for imbalanced data

SHAP-based feature importance for explainability

Dataset
Sources: DDInter, PubChem, DrugBank

Size: 12,220 drug pairs, 23 features (molecular descriptors, SMILES, DDI label)

Classes: 0 (Low/None), 1 (Medium), 2 (High)

Sample or synthetic data example is included for reproducibility.

Workflow
Preprocessing: Handle missing values, scale features, calculate Morgan fingerprints

Feature Engineering: Concatenate descriptors/fingerprints

Model Training: Multi-model training, soft-voting hybrid ensemble

Evaluation: Accuracy, precision, recall, F1-score, ROC-AUC

Interpretation: SHAP for top features (e.g., XLogP_B, MolecularWeight_B, TPSA_A, FP_5428)

Installation
bash
git clone https://github.com/<your-username>/ddi-ml-framework.git
cd ddi-ml-framework
pip install -r requirements.txt
RDKit may require Anaconda or be installed via conda-forge.

Usage
Place your data (or use provided sample schema) in data/

Launch notebook:

text
jupyter notebook notebooks/DDI_Prediction.ipynb
Run scripts from src/ for modular pipeline

Key Results
Model Accuracy ROC-AUC
LightGBM 0.910 0.962
XGBoost 0.906 0.958
Random Forest 0.906 0.956
Hybrid ensemble gave best overall predictions.

Insights
DDIs can be predicted with molecular features alone

SHAP highlights hydrophobicity, molecular weight, TPSA, and specific fingerprint bits as critical for interactions

Structurally similar drugs have higher DDI risk

Applications
Polypharmacy risk screening in clinics

Pre-clinical drug development

Personalized medication optimization

Drug safety monitoring in post-market surveillance

Limitations & Future Scope
Handling class imbalance is challenging for rare DDI classes

Future work: 3D structures, pharmacogenomics, expanding to other drug classes, deep learning approaches

References
See /docs/Thesis.pdf and /docs/Presentation.pdf for full literature.

Cheng F., JAMIA, 2014

Davis E., IJTD, 2018

Wang J., Molecules, 2024

DDInter, NAR, 2022

[Full reference list in thesis]

License and Acknowledgements
MIT License. Thanks to Dr. Sudarshana Deepa V, Department of Biotechnology, NIT Andhra Pradesh, and collaborators.

For issues, suggestions, or contributions: please open an issue or pull request!
