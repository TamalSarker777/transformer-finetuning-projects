# 🧠 Fine-Tuning T5-Small on Dolly-15K for Abstractive Summarization

This project demonstrates how to fine-tune Google's [`t5-small`](https://huggingface.co/google-t5/t5-small) model on the [`databricks/databricks-dolly-15k`](https://huggingface.co/datasets/databricks/databricks-dolly-15k) dataset for **abstractive summarization** using Hugging Face's `transformers`, `datasets`, and `accelerate` libraries.

---

## 🔧 Project Details

- **Model**: `google-t5/t5-small` (60M parameters)
- **Dataset**: `databricks/databricks-dolly-15k`
- **Task**: Abstractive Summarization
- **Input**: `context` field  
- **Target/Label**: `response` field  
- **Libraries Used**: 🤗 Transformers, Datasets, Accelerate, NLTK, PyTorch
- **Training Method**: Custom training loop using `accelerate`
- **Evaluation Metric**: ROUGE (ROUGE-1, ROUGE-2, ROUGE-L, ROUGE-Lsum)

---

## 📊 Results

| Epoch | ROUGE-1 | ROUGE-2 | ROUGE-L | ROUGE-Lsum |
|-------|---------|---------|---------|------------|
| 0     | 31.16   | 18.47   | 28.42   | 28.90      |
| 1     | 31.39   | 18.63   | 28.65   | 29.16      |
| 2     | 31.41   | 18.61   | 28.72   | 29.19      |
| 3     | 31.46   | 18.65   | 28.76   | 29.25      |
| 4     | 31.46   | 18.65   | 28.76   | 29.25      |

> ROUGE scores steadily improved and stabilized by epoch 4, indicating strong summarization performance on the dataset.

---
## To run the notebook, Install required libraries:
pip install transformers datasets accelerate rouge_score nltk
## Download NLTK tokenizer rules:
import nltk <br>
nltk.download("punkt")

## 🚀 How to Use the Fine-Tuned Model

You can load and run the fine-tuned model locally:

```python
from transformers import pipeline

summarizer = pipeline("summarization", model="results-t5-finetuned-squad-accelerate", tokenizer="results-t5-finetuned-squad-accelerate")

text = "Coffee drinks are made by brewing water with ground coffee beans..."
summary = summarizer(text, max_length=50)[0]["summary_text"]
print(summary)
