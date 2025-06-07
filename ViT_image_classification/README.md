# 🌿 Fine-Tuning Vision Transformer (ViT) on Beans Dataset

This repository contains a complete notebook and setup for fine-tuning a pre-trained Vision Transformer (ViT) model on the [Beans dataset](https://huggingface.co/datasets/beans), a small image classification dataset for plant disease detection.

---

## 📚 Dataset

- **Name**: Beans
- **Classes**: 
  - `healthy`
  - `angular_leaf_spot`
  - `bean_rust`
- **Source**: [Hugging Face Datasets](https://huggingface.co/datasets/beans)

---

## 🧠 Model

- **Base Model**: `google/vit-base-patch16-224`
- **Architecture**: Vision Transformer (ViT)
- **Framework**: Hugging Face `transformers` and `datasets`

---

## 🛠 Training Configuration

| Parameter                  | Value                  |
|---------------------------|------------------------|
| Epochs                    | 5                      |
| Batch Size (Train/Eval)   | 16                     |
| Learning Rate             | 5e-5                   |
| Gradient Accumulation     | 4                      |
| Warmup Ratio              | 0.1                    |
| Metric                    | Accuracy               |
| Push to Hub               | ✅ Enabled             |

---

## ✅ Results

| Epoch | Validation Accuracy |
|-------|----------------------|
| 1     | 87.4%               |
| 2     | 91.3%               |
| 3     | 95.2%               |
| 4     | 93.7%               |
| 5     | **96.1%** ✅        |

