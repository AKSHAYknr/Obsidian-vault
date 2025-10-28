
---
**Semi-Supervised Learning (SSL)** is a type of **machine learning** that combines elements of **Supervised** and **Unsupervised Learning**.  
It uses a **small amount of labeled data** and a **large amount of unlabeled data** during training.

The idea is that unlabeled data can help the model learn the underlying structure of the data distribution, improving performance even when labeled data is limited.

### 🎯 Goal

To **achieve better accuracy** than unsupervised learning and **reduce the labeling effort** compared to supervised learning.

### 🧩 How It Works

1. A small portion of data is labeled manually.
    
2. The model learns initial patterns using that labeled data.
    
3. The model then uses those patterns to **label (pseudo-label)** the unlabeled data.
    
4. It retrains or refines itself using both real and pseudo-labeled data.
### 📊 Example

Suppose you have 10,000 medical images 🧬, but only 500 are labeled with a disease category.  
Semi-supervised learning uses those 500 labeled images to guide learning on the remaining 9,500 unlabeled ones — saving enormous labeling time.

### 🧠 Techniques in Semi-Supervised Learning

#### 1️⃣ Pseudo-Labeling

- The model trained on labeled data predicts labels for the unlabeled data.
    
- These predicted labels are treated as "pseudo" ground truth to retrain the model.
#### 2️⃣ Consistency Regularization

- Encourages the model to produce **consistent predictions** for slightly perturbed versions of the same input.


#### 3️⃣ Graph-Based Learning

- Builds a graph connecting similar data points.
    
- Labeled data “propagates” its label information through the graph to unlabeled nodes.

#### 4️⃣ Generative Models

- Uses models like **VAEs (Variational Autoencoders)** or **GANs (Generative Adversarial Networks)** to learn data distribution and assist classification.

### 📘 Common Algorithms

- Semi-Supervised SVM (S³VM)
    
- Label Propagation / Label Spreading
    
- Semi-Supervised k-Means
    
- Self-Training and Co-Training
    
- Graph Convolutional Networks (GCN)

### 📏 Evaluation Metrics

Since part of the data is labeled, evaluation is usually done using that labeled subset:

|Metric|Used For|
|---|---|
|Accuracy|Classification|
|F1-score|Class imbalance|
|AUC-ROC|Binary classification|

### 💡 Advantages

✅ Reduces need for expensive labeled data  
✅ Improves learning quality using unlabeled samples  
✅ Useful when labeling is difficult (medical, legal, etc.)

### ⚠️ Disadvantages

❌ Risk of reinforcing incorrect pseudo-labels  
❌ Sensitive to data imbalance  
❌ Requires careful model validation

### 🧠 Real-World Applications

- Speech recognition 🎙️
    
- Text classification 📚
    
- Medical image analysis 🩺
    
- Fraud detection 💳
    
- Web content classification 🌐