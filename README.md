# Phishing Email Detection using DistilBERT and Multilingual BERT

## Project Overview

This project explores phishing email detection using Natural Language Processing (NLP) and Transformer-based models.

Two approaches were developed to classify emails as **Phishing** or **Legitimate**:

1. **English Phishing Detection:** Fine-tuning DistilBERT on English phishing email data.
2. **Thai Phishing Detection:** Translating English emails into Thai using NLLB-200 and fine-tuning Multilingual BERT (mBERT).

The project demonstrates how pretrained language models and machine translation can be applied to phishing email classification across different languages.

---

## Dataset

**Source:** [Phishing Email Dataset – Kaggle](https://www.kaggle.com/datasets/naserabdullahalam/phishing-email-dataset)

The project uses `phishing_email.csv`, containing email text and classification labels.

Data preparation includes:
- Handling missing values
- Removing duplicate records
- Sampling data for model training and evaluation
- Translating selected English emails into Thai

**Data used in experiments:**
- English DistilBERT: 3,000 samples
- Thai Multilingual BERT: 1,000 samples

The two experiments use different sample sizes and language settings.

---

## Methodology

### 1. English Phishing Email Detection — DistilBERT

**Model:** `distilbert-base-uncased`

- Load and preprocess English phishing email data.
- Select 3,000 email samples.
- Tokenize email text using the DistilBERT tokenizer.
- Fine-tune the pretrained model for binary classification.
- Evaluate classification performance using Accuracy and F1-score.

### 2. Thai Phishing Email Detection — Multilingual BERT

**Translation Model:** NLLB-200

**Classification Model:** `bert-base-multilingual-cased`

- Load and preprocess the original English email dataset.
- Select 1,000 email samples.
- Translate English email text into Thai using NLLB-200.
- Tokenize the translated text using the multilingual BERT tokenizer.
- Fine-tune mBERT for phishing email classification.
- Evaluate classification accuracy on the test dataset.

---

## Technologies and Libraries

- **Programming Language:** Python
- **Deep Learning Framework:** PyTorch
- **NLP Framework:** Hugging Face Transformers
- **Data Processing:** Pandas
- **Machine Learning:** Scikit-learn
- **Development Environment:** Jupyter Notebook / Google Colab

---

## Model Evaluation

| Model | Language | Samples | Evaluation |
|---|---|---:|---|
| DistilBERT | English | 3,000 | Accuracy, F1-score |
| Multilingual BERT | Thai | 1,000 | Accuracy |

**Thai mBERT reported accuracy: approximately 79%.**

The experiments demonstrate two approaches to phishing email detection. Since they use different sample sizes and languages, their results should not be interpreted as a controlled head-to-head comparison.

---

## Project Files

- `TestBERT (1).ipynb` — English phishing email classification using DistilBERT.
- `TestThaiBERT (2).ipynb` — Thai phishing email classification using NLLB-200 and Multilingual BERT.

## How to Run

1. Download the project notebooks.
2. Prepare the `phishing_email.csv` dataset from the referenced Kaggle source.
3. Open the notebooks in Google Colab or Jupyter Notebook.
4. Install the required Python libraries.
5. Adjust the dataset file paths if necessary.
6. Run the notebook cells in sequence to preprocess data, train the models, and evaluate performance.

GPU acceleration is recommended for Transformer fine-tuning and machine translation.

---

## Key Learning Outcomes

- Applied Transformer-based models to phishing email classification.
- Practiced fine-tuning pretrained language models.
- Explored machine translation for Thai-language NLP tasks.
- Gained experience in text preprocessing, tokenization, and model evaluation.
- Worked with Hugging Face Transformers and PyTorch.
