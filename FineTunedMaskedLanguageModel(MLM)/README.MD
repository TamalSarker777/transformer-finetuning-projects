# Fine-Tuning ALBERT on Wikitext-103 for Masked Language Modeling

This project demonstrates how to fine-tune the lightweight `albert-base-v2` model on the `wikitext-103-raw-v1` dataset using Hugging Face's `transformers`, `datasets`, and `accelerate` libraries. The notebook includes full preprocessing, training, evaluation, and testing via the `pipeline`.

## 🔧 Project Highlights

- **Model**: `albert-base-v2` (11M parameters)
- **Dataset**: Wikitext-103 (`wikitext-103-raw-v1`)
- **Task**: Masked Language Modeling (MLM)
- **Training Framework**: 🤗 Accelerate
- **Eval Metric**: Perplexity (computed manually)

## 📈 Results

- Final Perplexity: ~8.57 after 3 epochs of training
- Training loop uses gradient accumulation and learning rate scheduling
- Evaluation masking was frozen to ensure consistent test results

## 🔍 Features

- Custom `insert_random_mask` function for stable evaluation
- Whole word masking option available
- Local model saving and loading for reuse
- Tested with `pipeline("fill-mask")` using local weights

## 🧪 How to Run

Run all cells in the `huggingface_MLM.ipynb` notebook to:
1. Load data and tokenizer
2. Fine-tune the ALBERT model
3. Save and evaluate the model
4. Test it using the Hugging Face pipeline with masked input

Example test:
```python
from transformers import pipeline

pipe = pipeline("fill-mask", model="albert-base-v2-finetuned-accelerate", tokenizer="albert-base-v2-finetuned-accelerate")
pipe("The capital of France is <mask>.")
