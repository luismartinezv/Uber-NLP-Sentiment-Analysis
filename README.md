# 🚖 Uber NLP Sentiment Analysis: Customer Churn Mitigation

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python&logoColor=white)
![Machine Learning](https://img.shields.io/badge/Machine_Learning-Scikit--Learn-orange)
![NLP](https://img.shields.io/badge/NLP-spaCy_|_TF--IDF-darkgreen)

## 📌 Executive Summary & Business Value

In the contemporary digital economy, ride-hailing platforms generate an unprecedented volume of unstructured textual data through customer feedback. Manual moderation is computationally and operationally unviable. 

**The Business Objective:** Develop a robust Text Mining framework capable of automating the sentiment classification of customer reviews. By deploying this pipeline, operations teams can **instantly filter and route urgent negative reviews to customer support**, significantly reducing response times, preventing PR crises, and mitigating user churn.

## ⚙️ Methodology & NLP Pipeline

This project utilizes advanced Natural Language Processing (NLP) techniques on a corpus of over 12,000 labeled reviews:

1. **Text Normalization & Cleansing:** Implemented the `spaCy` engine for deep linguistic analysis. The pipeline executes tokenization, lemmatization, and aggressive stop-word filtering to drastically reduce semantic noise.
2. **Mathematical Modeling (TF-IDF):** The unstructured text was transformed into a high-dimensional feature space using Term Frequency-Inverse Document Frequency (`TfidfVectorizer`), enforcing a 1,000-feature constraint to optimize computational efficiency for production deployment.
3. **Machine Learning Algorithms:** A comprehensive comparative study was conducted evaluating three supervised models:
   * Logistic Regression
   * Random Forest Classifier
   * Support Vector Machines (Linear SVM)

## 📊 Results & Model Selection

To ensure statistical validity and prevent overfitting, all algorithms were subjected to a rigorous **Stratified 5-Fold Cross-Validation**.

* **Champion Model:** `Logistic Regression`
* **Performance:** Achieved an accuracy of **93.5%** with a highly balanced F1-score.
* **Conclusion:** Logistic Regression was selected as the optimal deployment candidate over Random Forest and SVM due to its superior inference speed and low computational cost when handling sparse text matrices, making it ideal for real-time API integrations.

## 🚀 How to Run Locally

To reproduce this NLP pipeline in your local environment:

```bash
# Clone the repository
git clone [https://github.com/luismartinezv/Uber-NLP-Sentiment-Analysis.git](https://github.com/luismartinezv/Uber-NLP-Sentiment-Analysis.git)

# Navigate into the directory
cd Uber-NLP-Sentiment-Analysis

# Install dependencies
pip install -r requirements.txt

# Download the required spaCy English language model
python -m spacy download en_core_web_sm
