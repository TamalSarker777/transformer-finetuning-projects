# Fine-Tuning Helsinki-NLP on Opus Books for English-to-French Translation
This project demonstrates how to fine-tune the Helsinki-NLP/opus-mt-en-fr translation model on the opus_books dataset using Hugging Face's transformers, datasets, and accelerate libraries.

# 🔧 Project Details
**Model**: Helsinki-NLP/opus-mt-en-fr

**Dataset**: Opus Books (en-fr)

**Task**: Machine Translation (English → French)

**Libraries Used**: 🤗 Transformers, Datasets, Accelerate, Evaluate, SacreBLEU

**Training Method**: Custom training loop using accelerate

**Evaluation Metric**: SacreBLEU

# 📊 Results
Final BLEU Score after 2 epochs: e.g., 42.10 (Replace with your actual values)

# 🚀 How to Use
You can load and test the fine-tuned model locally using:

```python
from transformers import pipeline

translator = pipeline("translation_en_to_fr", model="opus-mt-en-fr-finetuned", tokenizer="opus-mt-en-fr-finetuned")
translator("The book is on the table.")
