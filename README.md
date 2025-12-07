# **Predictive Maintenance for Oil & Gas Pump Operations**

### *Accenture 2C — Break Through Tech AI Studio Final Project*

## ⭐ **Overview**

Unplanned pump failures are a major source of downtime and financial loss in oil & gas operations. Traditional reactive maintenance leads to unnecessary repairs, safety risks, and operational inefficiency.

Our team built a **machine learning–powered predictive maintenance system** capable of identifying pump failures before they occur, enabling operators to take preventive action and reduce downtime.

---

## 👥 **Team**

Break Through Tech AI Fellows:

* **Maruf Aurnap – Cornell University**
* **Jocelyn Prieto – Barnard College**
* **Aarshia Hukmani – Hofstra University**
* **Tobenna Ahanotu – Morgan State University**
* **Zara Jalaluddin – University of Maryland, College Park**
* **Faith Nchang – University of Maryland, College Park**

Accenture Challenge Coaches:

* **Makena Hillman – Analytics Consultant**
* **Kaneesha Dawood – Data Consultant**

---

## 🎯 **Project Goals**

* Build a model that accurately predicts when a pump is likely to fail.
* Reduce unplanned downtime by enabling early detection.
* Extend equipment lifespan through data-driven maintenance planning.
* Demonstrate measurable financial impact through predictive insights.

---

## 📊 **Dataset & Target Variable**

The dataset includes mechanical and operational signals from multiple pumps:

### **Features**

* Pump throughput (m³/h)
* Operating pressure (bar)
* Vibration levels (mm/s)
* Bearing temperature (°C)
* General temperature
* Pump identifier

### **Target**

* **Pump Status** (Running = 1, Down = 0)

### **Key Insights**

* Pumps tend to be *down* when throughput, pressure, and vibration approach zero.
* Higher sensor readings generally correlate with pumps running normally.
* Several features show strong predictive correlation with pump status.

---

## 🧠 **Modeling Approach**

We experimented with three model classes:

### **Logistic Regression**

* Interpretable, stable, and highly efficient
* Resistant to overfitting on clean, linearly separable data
* **Chosen as final model** after tuning

### **Feedforward Neural Network**

* Captures nonlinearity
* Good performance but higher variance and slower

### **Binary Sliding Window LSTM**

* Incorporates temporal patterns
* Strong sequence modeling but computationally expensive

### **Why Logistic Regression Won**

* Excellent performance after hyperparameter tuning
* Lightweight enough for real-time prediction
* Achieved **100% precision and 100% recall** on validation
* Avoided overfitting more complex models encountered

---

## 📈 **Business Impact**

Using model predictions to prevent downtime produced major savings:

* **408,985 minutes of avoided downtime**
* ~6,816 additional operational hours
* At **$500 per hour**, this yields:

  * **$3,408,210 saved across 100 days**
  * **$238,574 saved weekly**
  * **$34,082 saved daily**

This system reduced downtime by **more than 80%**, highlighting the effectiveness of predictive maintenance powered by ML.

---

## 🛠️ **Recommended Repository Structure**

```
├── data/
│   ├── raw/
│   ├── processed/
├── notebooks/
│   ├── 01_EDA.ipynb
│   ├── 02_Feature_Engineering.ipynb
│   ├── 03_Model_Training.ipynb
│   ├── 04_Model_Evaluation.ipynb
├── src/
│   ├── preprocessing.py
│   ├── train.py
│   ├── evaluate.py
│   ├── utils.py
├── dashboard/
│   ├── dashboard_mockup.png
├── models/
│   ├── logistic_regression.pkl
├── README.md
└── requirements.txt
```

---

## 🚀 **Usage**

### **1. Install requirements**

```bash
pip install -r requirements.txt
```

### **2. Train the model**

```bash
python src/train.py
```

### **3. Evaluate performance**

```bash
python src/evaluate.py
```

### **4. Predict from new data**

```python
from model import predict
predict(input_data)
```

---

## 🔮 **Future Enhancements**

* Integrate real-time sensor streaming
* Expand to multi-class failure mode classification
* Deploy model as a cloud-based microservice
* Build a live monitoring dashboard with alerts
* Add anomaly detection for unseen failure patterns

---

## 🎓 **What We Learned**

* The simplest model can be the best when data is clean and separable
* Importance of collaboration and MLOps best practices
* How to translate ML performance into business value
* Hands-on experience with the full machine learning lifecycle

