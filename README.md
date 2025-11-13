# A-Project 2: Amazon Reviews Sentiment Analysis Microservice

This project developed a **binary sentiment classification model** for Amazon product reviews and deployed it as a **serverless microservice** using Docker and Google Cloud Run.  
Multiple classical and deep learning models were evaluated, including Logistic Regression, Linear SVM, LSTM, and DistilBERT.

* **Dataset:** Amazon Reviews Dataset (Kaggle, ~4M reviews)  
* **Tools:** Python, scikit-learn, TensorFlow, Hugging Face Transformers, Docker, Google Cloud Run  
* **Techniques:** Text preprocessing, TF–IDF vectorization, LSTM architecture, DistilBERT fine-tuning, microservice deployment  
* **Goal:** Build a production-ready sentiment classification API with high accuracy and scalable inference.

---

### ⚙️ Data Preparation
1. Merged Kaggle train & test sets (~4M rows).  
2. Removed 231 missing rows.  
3. Re-labeled sentiment: **0 = negative, 1 = positive**.  
4. Sampled **1 million** reviews for efficient training.  
5. Applied text cleaning: lowercase, remove punctuation, digits, and extra whitespace.  
6. Created `clean_text` feature for modeling.

---

### 🧩 Model Development
Four models were trained and evaluated on the prepared dataset.

| Model | Accuracy | Precision | Recall | F1 | Notes |
|-------|-----------|------------|---------|--------|--------|
| Logistic Regression | 0.87 | 0.87 | 0.87 | 0.87 | Classical baseline |
| Linear SVM | 0.867 | 0.87 | 0.87 | 0.87 | Strong TF–IDF performance |
| LSTM | 0.907 | 0.92 | 0.90 | 0.91 | Captures sequential patterns |
| **DistilBERT** | **0.949** | **0.96** | **0.94** | **0.95** | Best-performing model |

---

### ☁️ Model Deployment (Google Cloud Run)
The final DistilBERT model was deployed as a **serverless microservice**.

**Deployment Steps**
- Exported model + tokenizer  
- Saved artifacts in Google Cloud Storage  
- Built Docker container for Flask API  
- Pushed and deployed container to Cloud Run  


---

### 🧪 API Testing
<div align="center"> <img src="images/API_testing-postman.png" alt="API Testing Screenshot 1" width="600"/> <p><em>Testing the API with user-written review input.</em></p> </div>
<div align="center"> <img src="images/API_testing-google colab.png" alt="API Testing Screenshot 2" width="600"/> <p><em>API successfully returns predicted sentiment.</em></p> </div>

---

### 💡 Applications

1.Real-time customer review analysis
2.Automated support message classification
3.E-commerce product sentiment trends
4.Social media & brand monitoring

---

### 🧠 Skills Demonstrated

1.Sentiment analysis with classical ML, LSTM, and Transformers
2.Deep learning model comparison
3.Docker containerization
4.Google Cloud Run deployment
5.REST API development for ML services
