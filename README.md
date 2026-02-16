# Transfer Learning with BERT

## Dataset
Multiclass Sentiment Analysis Dataset

## Steps
- Exploratory Data Analysis
- BERT fine-tuning using PyTorch
- Model evaluation
- Inference pipeline

## Model
bert-base-uncased

## Metrics
Accuracy, Precision, Recall, F1-score (weighted)

## How to Run
Open the notebook in Google Colab and run all cells.

## Approach

This project applies transfer learning by fine-tuning a pretrained BERT model for a multiclass text classification task. The Sp1786/multiclass-sentiment-analysis-dataset is loaded using the Hugging Face datasets library. Exploratory Data Analysis (EDA) is performed to examine the distribution of sentiment classes in the training set.

Text samples are tokenized using the BERT tokenizer with padding and truncation to a fixed length. The bert-base-uncased model is used as a feature extractor, and a custom classification layer is added on top. Fine-tuning is implemented strictly using PyTorch, with a manual training loop, AdamW optimizer, and cross-entropy loss. The model is trained for 10 epochs and evaluated on a held-out test set using standard classification metrics. A confusion matrix is generated to analyze prediction behavior, and an inference function is implemented to predict labels and confidence scores for unseen text.

## Assumptions

The dataset text is assumed to be sufficiently clean for direct tokenization.

A maximum sequence length of 128 tokens captures the relevant context.

Weighted evaluation metrics are suitable due to minor class imbalance.

Training for 10 epochs is sufficient for convergence without overfitting.

## Observations

Training loss decreases steadily across epochs, indicating effective learning.

The model performs well across most sentiment classes.

Some confusion occurs between semantically similar sentiment labels.

Transfer learning with BERT significantly improves performance compared to training from scratch.
