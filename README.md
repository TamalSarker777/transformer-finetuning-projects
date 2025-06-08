# 🚀 AI/ML Project Portfolio (Hugging Face Transformers)

This repository contains 7 deep learning projects across **Natural Language Processing (NLP)** and **Computer Vision (CV)** using state-of-the-art models and datasets from the [🤗 Hugging Face Hub](https://huggingface.co/). Each project fine-tunes a pretrained model for a specific task, implements evaluation metrics, and is self-contained with a detailed `README.md`.

---

## 📚 NLP / LLM Projects

### 1. 🧠 Fine-tuned LLM
- **Model:** [`deepseek-ai/DeepSeek-R1-Distill-Qwen-1.5B`](https://huggingface.co/deepseek-ai/DeepSeek-R1-Distill-Qwen-1.5B)
- **Dataset:** `HuggingFaceTB/smoltalk`
- **Task:** Instruction fine-tuning
- **Use Case:** LLM for chat-style prompts

---

### 2. 🔤 Masked Language Modeling (MLM)
- **Model:** [`albert-base-v2`](https://huggingface.co/albert-base-v2) (11M parameters)
- **Dataset:** `wikitext-103-raw-v1`
- **Metric:** Perplexity (computed manually)
- **Task:** Token masking and prediction

---

### 3. 🌍 Machine Translation
- **Model:** [`Helsinki-NLP/opus-mt-en-fr`](https://huggingface.co/Helsinki-NLP/opus-mt-en-fr)
- **Dataset:** Opus Books (English ↔ French)
- **Task:** English to French translation
- **Metric:** BLEU

---

### 4. 📝 Summarization
- **Model:** [`google-t5/t5-small`](https://huggingface.co/google-t5/t5-small) (60M parameters)
- **Dataset:** `databricks/databricks-dolly-15k`
- **Metric:** ROUGE (ROUGE-1, ROUGE-2, ROUGE-L, ROUGE-Lsum)
- **Task:** Abstractive summarization

---

## 🖼️ Computer Vision Projects (ViT)

### 5. 🧩 Image Segmentation
- **Model:** [`nvidia/mit-b0`](https://huggingface.co/nvidia/mit-b0)
- **Dataset:** `mattmdjaga/human_parsing_dataset`
- **Task:** Semantic segmentation with ViT encoder
- **Metric:** mIoU, pixel accuracy

---

### 6. 🕵️ Object Detection
- **Model:** [`facebook/detr-resnet-50`](https://huggingface.co/facebook/detr-resnet-50)
- **Dataset:** `Francesco/animals-ij5d2`
- **Task:** Bounding box detection (COCO-style)
- **Metric:** mAP (mean Average Precision)

---

### 7. 🏷️ Image Classification
- **Model:** [`google/vit-base-patch16-224`](https://huggingface.co/google/vit-base-patch16-224)
- **Dataset:** `Beans` (bean disease classification)
- **Task:** Multi-class classification
- **Metric:** Accuracy, F1-score

---

## 🧰 Tech Stack

- [Transformers](https://huggingface.co/docs/transformers/en/index)
- [Datasets](https://huggingface.co/docs/datasets/en/index)
- PyTorch, torchvision
- torchmetrics, evaluate
- Colab/Jupyter for notebooks

---

## 🔐 Hugging Face Login

To authenticate for loading or pushing models:

```python
from huggingface_hub import login
login(token="your_hf_token")
