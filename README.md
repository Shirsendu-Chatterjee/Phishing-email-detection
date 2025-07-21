# Phishing-email-detection
This project uses a fine-tuned `DistilBERT` model from HuggingFace Transformers to classify emails as either Phishing or Safe. The model is trained on labeled email text and provides robust predictions using modern NLP techniques.

## 🔍 Project Overview

With the rise in phishing attacks, identifying malicious emails is more critical than ever. This project leverages **transformer-based NLP** to automatically detect phishing content in emails using supervised learning.

---

## 🧠 Model

- **Base Model:** `distilbert-base-uncased`
- **Type:** Binary Text Classification
- **Frameworks:** HuggingFace Transformers, PyTorch
- **Metrics:** Accuracy, Precision, Recall, F1-Score
| Metric        | Value         |
| ------------- | ------------- |
| **Accuracy**  | 96.88%        |
| **F1 Score**  | 97.40%        |
| **Precision** | 98.33%        |
| **Recall**    | 96.50%        |
| **Loss**      | 0.1201        |
| **Eval Time** | 60.08 seconds |




---

## 📂 Dataset (https://www.kaggle.com/datasets/subhajournal/phishingemails)

- Format: CSV file with two columns — `Email Text` and `Email Type`  
- Preprocessing:
  - Dropped nulls
  - Mapped `"Safe Email"` to `1`, `"Phishing Email"` to `0`
  - Renamed columns to `text` and `labels`

---

## ⚙️ Training

```python
model = BertForSequenceClassification.from_pretrained("distilbert-base-uncased", num_labels=2)


