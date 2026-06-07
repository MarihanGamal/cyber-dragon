# 🐉 Cyber Dragon Security Dashboard
**Message Urgency & Threat Detection System**

---

## 📦 Project Structure

```
cyber_dragon/
├── dataset.csv        ← 5,572 real SMS messages (ham/spam)
├── train.py           ← Model training script
├── model.pkl          ← Trained Logistic Regression model
├── vectorizer.pkl     ← TF-IDF vectorizer
├── app.py             ← Streamlit dashboard
├── requirements.txt   ← Python dependencies
└── README.md
```

---

## 🚀 Quick Start

### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Train the model (already done — pkl files included)
```bash
python train.py
```
Expected output:
- ✅ Accuracy: **98.57%**
- 📁 Saves `model.pkl` and `vectorizer.pkl`

### 3. Launch the dashboard
```bash
streamlit run app.py
```
Open browser at: **http://localhost:8501**

---

## 🎯 Features

| Feature | Details |
|---|---|
| ML Model | Logistic Regression + TF-IDF (1-2 ngrams, 5000 features) |
| Dataset | 5,572 real SMS messages from UCI SMS Spam Collection |
| Accuracy | 98.57% on held-out test set |
| Classes | Normal (ham) / Suspicious (spam) |
| Risk Score | Probability score 0–100% |
| Threat Level | Low / Medium / High |
| Keyword Detection | 30+ urgency & threat keywords |
| Keyword Highlighting | Visual highlight in input text |
| Session Stats | Live counters + pie chart |
| History | Last 10 analyzed messages |
| UI Theme | Cyberpunk dark neon (Orbitron font) |

---

## 🔍 predict_message() API

```python
from app import predict_message

result = predict_message("URGENT! Verify your account password now!")
# Returns:
# {
#   "label": "Suspicious",
#   "risk_score": 0.93,
#   "detected_keywords": ["urgent", "verify", "password", "account"]
# }
```

---

## 📊 Model Performance

```
              precision    recall  f1-score
Normal            0.99      0.99      0.99
Suspicious        0.96      0.93      0.95

Accuracy: 98.57%
```

Confusion Matrix:
```
               Pred Normal  Pred Suspicious
True Normal          960               6
True Suspicious       10             139
```

---

## 🐉 UI Preview

- Dark cyberpunk background
- Neon green (safe) / red (threat) color coding
- Animated pulsing alert for suspicious messages
- Plotly donut chart for distribution
- Keyword chip highlights
- Glowing Orbitron font headers
