# Log-based-intrusion-detection
Machine Learning based Log Intrusion Detection System using NLP + Random Forest

This project detects anomalies in Linux authentication logs using  
**Natural Language Processing (TF-IDF)** and **Machine Learning (Random Forest)**.

The model classifies logs into the following categories:
- 0 = normal  
- 1 = privilege escalation  
- 2 = port scan  
- 3 = geo anomaly  
- 4 = brute force attack

Dataset was sampled to 80,000 rows and trained in Google Colab.

## Contents
- `notebook.ipynb` — main ML model training notebook  
- `model/` — saved Random Forest model + TF-IDF vectorizer  
- `requirements.txt` — Python dependencies  
- `dataset_info.txt` — dataset description  
- `screenshots/` — confusion matrix & results

## How to Run
1. Install dependencies  
   ```bash
   pip install -r requirements.txt

2. Open the notebook
   ```bash
   jupyter notebook notebook.ipynb

3. Run all cells to train or test the model.

## Example Prediction
sample_logs = [
    "2024-10-11 195.241.151.7 Failed login via sudo",
    "2025-02-02 10.0.0.10 Successful ssh login",
    "2024-07-21 45.12.33.19 Failed port scan detected"
]

sample_vec = tfidf.transform(sample_logs)
rf.predict(sample_vec)

## Model Accuracy
The Random Forest classifier achieved 100% accuracy on test data.

  
