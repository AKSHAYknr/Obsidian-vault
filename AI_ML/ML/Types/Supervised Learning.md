
---
### 🏷️ Definition

Supervised Learning is a type of **machine learning** where the model learns from **labeled data** — meaning each training example has an input (`X`) and a corresponding output (`Y`).  
The model learns the mapping function:

Y=f(X)Y = f(X)Y=f(X)

### 🎯 Goal

To predict the **output (label)** for new, unseen input data based on patterns learned during training.

### 🧩 How It Works

1. **Training Phase:**
    
    - Provide input–output pairs (X, Y).
        
    - Model learns the relationship between inputs and outputs.

2. **Testing Phase:**
    
    - Feed new input data (X’).
        
    - Model predicts output (Y’).

### 🧮 Example

|Input (X)|Output (Y)|
|---|---|
|Hours Studied|Exam Score|
|2|30|
|4|50|
|6|70|
|8|90|

Model learns that more hours → higher score, and predicts scores for unseen data.

### 🧠 Types of Supervised Learning

#### 1️⃣ Regression

Predicts **continuous values** (numeric output).  
📌 **Examples:**

- Predicting house prices
    
- Temperature forecasting
    
- Stock price prediction

📘 **Common Algorithms:**

- Linear Regression
    
- Polynomial Regression
    
- Decision Tree Regressor
    
- Random Forest Regressor

#### 2️⃣ Classification

Predicts **categorical values** (discrete output).  
📌 **Examples:**

- Email spam detection (spam / not spam)
    
- Sentiment analysis (positive / negative)
    
- Disease detection (yes / no)

📘 **Common Algorithms:**

- Logistic Regression
    
- K-Nearest Neighbors (KNN)
    
- Support Vector Machines (SVM)
    
- Decision Trees
    
- Random Forest
    
- Naive Bayes
 
### ⚙️ Steps in Supervised Learning

1. **Data Collection**
    
2. **Data Preprocessing**
    
    - Cleaning
        
    - Handling missing values
        
    - Feature scaling / encoding

3. **Splitting Data**
    
    - Train set
        
    - Test set

4. **Model Training**
    
    - Fit model on training data

5. **Model Evaluation**
    
    - Use metrics to test accuracy

6. **Model Optimization**
    
    - Hyperparameter tuning
    - Cross-validation
   
### 📏 Common Evaluation Metrics

|Type|Metrics|Description|
|---|---|---|
|Regression|MSE, RMSE, MAE, R²|Measure error between predicted & actual values|
|Classification|Accuracy, Precision, Recall, F1-score, ROC-AUC|