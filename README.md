# Misinformation Detection using BERT Embeddings and Logistic Regression

## Overview
This project focuses on detecting misinformation using Natural Language Processing (NLP).  
We build a strong text-based baseline model by leveraging BERT embeddings combined with a Logistic Regression classifier.

The goal is to establish a solid baseline for misinformation detection using text data, which can later be extended to a multimodal system incorporating both text and images.

---

## Problem Statement
Misinformation detection is a challenging task, especially in real-world scenarios where content often includes both textual and visual information.  

Relying solely on text may not be sufficient, as images can significantly alter the meaning or intent of content.  

In this project, we explore how effectively a model can perform using only textual data.

---

## Approach
We follow a standard NLP pipeline:

- Load and preprocess text data  
- Convert text into dense vector representations using BERT (DistilBERT)  
- Train a classifier (Logistic Regression)  
- Evaluate performance using standard classification metrics  

This pipeline provides a simple, interpretable, and effective baseline model.

---

## Dataset
We use the IMDB movie review dataset:

- Binary classification (positive / negative sentiment)  
- Balanced dataset  
- Subset of 3000 samples used for computational efficiency  

Although this dataset is not directly misinformation-related, it serves as a reliable benchmark for text classification and model validation.

---

## Feature Extraction
We use **DistilBERT (distilbert-base-uncased)** to convert text into embeddings:

- Each text sample is transformed into a 768-dimensional vector  
- We extract the representation of the `[CLS]` token as the embedding  
- No fine-tuning is applied (feature-based approach)  

---

## Model
We use **Logistic Regression** as a baseline classifier due to:

- Simplicity  
- Interpretability  
- Strong performance with high-quality embeddings  

---

## Train-Test Split
- 80% training data  
- 20% testing data  
- Random state fixed for reproducibility  

---

## Evaluation Metrics
We evaluate the model using:

- Accuracy  
- Precision  
- Recall  
- F1-score  
- Confusion Matrix  

---

## Results
The model achieved an accuracy of approximately **74%** on the test set.

### Confusion Matrix Insights
- The model performs reasonably well on both classes  
- However, there are still misclassifications, particularly in borderline cases  

---

## Results

### Confusion Matrix
![Confusion Matrix](images/confusion_matrix.png)

### Performance
- Accuracy: 74%

---

## Results Summary
The model achieves solid baseline performance, demonstrating that BERT embeddings are effective for text classification tasks.  

However, the results indicate that text-only features are not sufficient for capturing more complex patterns related to misinformation detection.  

This highlights the importance of incorporating additional modalities such as images.

---

## How to Run

1. Clone the repository
```bash
git clone https://github.com/your-username/misinformation-detection-bert.git
cd misinformation-detection-bert
```

2. Install dependencies
```bash
pip install -r requirements.txt
```

3. Launch Jupyter Notebook
```bash
jupyter notebook
```

4. Open and run the notebook
```bash
1-text-baseline-bert.ipynb
```

---

## Limitations
- Uses only textual data  
- No fine-tuning of BERT (feature extraction only)  
- Dataset not directly related to misinformation  
- Moderate performance (baseline level)  

---

## Future Work
To improve performance, the model can be extended to a **multimodal system**:

- Extract image embeddings using CLIP  
- Combine text and image features  
- Train a multimodal classifier  
- Compare performance against the text-only baseline  

This is expected to significantly improve performance in real-world misinformation detection scenarios.

---

## Reproducibility
To reproduce this project:

1. Install required libraries:
   - pandas  
   - numpy  
   - scikit-learn  
   - transformers  
   - torch  

2. Run all notebook cells sequentially  

3. The dataset is automatically loaded via URL  

---

## Conclusion
In this project, we developed a text-based misinformation detection system using BERT embeddings and Logistic Regression.  

The model achieved an accuracy of approximately 74%, demonstrating the effectiveness of modern NLP techniques even with simple classifiers.  

At the same time, the results highlight the limitations of relying solely on textual data.  

Overall, this project establishes a strong baseline and provides a solid foundation for future improvements through multimodal approaches.

---

## Author
IOANNIDIS NIKOLAOS
Project developed as part of a personal portfolio for MSc applications in Artificial Intelligence / Data Science.
