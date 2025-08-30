# 🔬 DDI Prediction Using Molecular Fingerprints

A machine learning framework for predicting **Drug-Drug Interactions (DDIs)** among gastrointestinal and metabolic drugs using **molecular fingerprints** and **physicochemical descriptors**.  
The framework benchmarks multiple ML models, with **LightGBM** achieving the best performance (Accuracy: **90.96%**, ROC-AUC: **0.962**) and further improvement via a **hybrid ensemble**.  

Model interpretability is ensured through **SHAP analysis**, highlighting key molecular features driving DDI predictions.

---

## ✨ Features
- ✅ Predicts DDIs from **drug structure** and **molecular properties**  
- ⚡ Multiple models tested: **LightGBM, XGBoost, Random Forest, CatBoost, others**  
- ⚖️ Handles imbalanced data with **SMOTE** and **class weighting**  
- 🔍 **SHAP-based feature importance** for explainability  
- 📊 Modular pipeline for preprocessing, training, evaluation, and interpretation  

---

## 📂 Dataset
- **Sources:** [DDInter](https://ddinter.scbdd.com/), [PubChem](https://pubchem.ncbi.nlm.nih.gov/), [DrugBank](https://go.drugbank.com/)  
- **Size:** 12,220 drug pairs, 23 features  
- **Features:** Molecular descriptors, SMILES, DDI label  
- **Classes:**  
  - `0` → Low/None  
  - `1` → Medium  
  - `2` → High  

A sample/synthetic dataset is included for reproducibility.

---

## ⚙️ Workflow
1. **Preprocessing** → Handle missing values, scale features, calculate Morgan fingerprints  
2. **Feature Engineering** → Concatenate descriptors and fingerprints  
3. **Model Training** → Train multiple ML models  
4. **Evaluation** → Accuracy, Precision, Recall, F1-score, ROC-AUC  
5. **Interpretation** → SHAP for feature importance  

---

## 📊 Key Results
| Model          | Accuracy | ROC-AUC |
|----------------|----------|---------|
| **LightGBM**   | 0.910    | 0.962   |
| XGBoost        | 0.906    | 0.958   |
| Random Forest  | 0.906    | 0.956   |

➡️ **Hybrid ensemble achieved the best overall predictions.**

---

## 🔎 Insights
- DDIs can be reliably predicted from **molecular features alone**  
- **SHAP** identifies hydrophobicity (XLogP), molecular weight, TPSA, and specific fingerprint bits as critical predictors  
- Structurally similar drugs tend to have higher DDI risk  

---

## 🚀 Installation
```bash
git clone https://github.com/<your-username>/ddi-ml-framework.git
cd ddi-ml-framework
pip install -r requirements.txt
