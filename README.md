# Fine-Tuning ALBERT on Wikitext-103 for Masked Language Modeling

This project demonstrates how to fine-tune the lightweight `albert-base-v2` model on the `wikitext-103-raw-v1` dataset using Hugging Face's `transformers`, `datasets`, and `accelerate` libraries.

## 🔧 Project Details

- **Model**: `albert-base-v2` (11M parameters)
- **Dataset**: Wikitext-103 (`wikitext-103-raw-v1`)
- **Task**: Masked Language Modeling (MLM)
- **Libraries Used**: 🤗 Transformers, Datasets, Accelerate, PyTorch
- **Training Method**: Custom training loop using `accelerate`
- **Evaluation Metric**: Perplexity

## 📊 Results

- Final Perplexity: ~8.57 after 3 epochs — a solid result for general-domain MLM using ALBERT.

## 🚀 How to Use

You can load the fine-tuned model locally for testing:
```python
from transformers import pipeline

pipe = pipeline("fill-mask", model="albert-base-v2-finetuned-accelerate", tokenizer="albert-base-v2-finetuned-accelerate")
pipe("The capital of France is <mask>.")
