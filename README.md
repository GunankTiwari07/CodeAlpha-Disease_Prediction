🏥 Disease Prediction from Medical Data
---
A machine learning project to predict the likelihood of diseases (Heart Disease, Diabetes, Breast Cancer) using patient medical data with multiple classification algorithms.
---
📌 Objective
Predict the possibility of diseases based on structured patient data using classification techniques.
---
📁 Project Structure
```
disease-prediction/
├── data/                    # Raw and processed datasets
│   ├── raw/                 # Original UCI datasets (CSV)
│   └── processed/           # Cleaned & feature-engineered data
├── notebooks/               # Jupyter Notebooks for EDA & experiments
│   ├── 01_EDA.ipynb
│   ├── 02_Heart_Disease.ipynb
│   ├── 03_Diabetes.ipynb
│   └── 04_Breast_Cancer.ipynb
├── src/                     # Source code modules
│   ├── __init__.py
│   ├── data_loader.py       # Dataset loading & preprocessing
│   ├── feature_engineering.py
│   ├── train.py             # Model training pipeline
│   ├── evaluate.py          # Metrics & evaluation
│   └── predict.py           # Inference on new data
├── models/                  # Saved trained models (.pkl)
├── results/                 # Plots, metrics, classification reports
├── tests/                   # Unit tests
│   └── test_pipeline.py
├── app.py                   # Streamlit web app (optional demo)
├── requirements.txt
├── config.yaml              # Hyperparameters & paths config
└── README.md
```
---
🗂️ Datasets
---
All datasets are sourced from the UCI Machine Learning Repository:
Disease	Dataset	Samples	Features
Heart Disease	Cleveland Heart Disease	303	13
Diabetes	Pima Indians Diabetes	768	8
Breast Cancer	Wisconsin Breast Cancer	569	30
To download datasets:
```bash
python src/data_loader.py --download
```
Or place CSV files manually in `data/raw/`.
---
🤖 Algorithms Used
Logistic Regression — baseline linear classifier
Support Vector Machine (SVM) — with RBF kernel
Random Forest — ensemble of decision trees
XGBoost — gradient boosted trees
---
⚙️ Setup & Installation
1. Clone the repository
```bash
git clone https://github.com/yourusername/disease-prediction.git
cd disease-prediction
```
2. Create virtual environment
```bash
python -m venv venv
source venv/bin/activate        # Linux/Mac
venv\Scripts\activate           # Windows
```
3. Install dependencies
```bash
pip install -r requirements.txt
```
---
🚀 Usage
Train all models
```bash
python src/train.py --dataset all
```
Train on a specific dataset
```bash
python src/train.py --dataset heart
python src/train.py --dataset diabetes
python src/train.py --dataset breast_cancer
```
Evaluate models
```bash
python src/evaluate.py --dataset all
```
Predict on new data
```bash
python src/predict.py --dataset heart --input data/sample_input.json
```
Run the Streamlit app
```bash
streamlit run app.py
```
---
🔑 Key Features Used
---
Heart Disease: age, sex, chest pain type, resting BP, cholesterol, fasting blood sugar, ECG results, max heart rate, exercise angina, ST depression, slope, vessels, thal
Diabetes: pregnancies, glucose, blood pressure, skin thickness, insulin, BMI, diabetes pedigree function, age
Breast Cancer: mean radius, texture, perimeter, area, smoothness, compactness, concavity, symmetry, fractal dimension (+ worst & SE variants)
---
📈 Visualizations
Generated plots saved in `results/`:
Correlation heatmaps
Feature importance charts
ROC curves
Confusion matrices
Class distribution plots
---
🧪 Running Tests
```bash
pytest tests/
```
---
📦 Tech Stack
Python 3.9+
scikit-learn
XGBoost
pandas, numpy
matplotlib, seaborn
Streamlit (demo app)
joblib (model persistence)
---
👤 Author
Your Name  
GitHub | LinkedIn
---
📄 License
This project is licensed under the MIT License — see LICENSE for details.
