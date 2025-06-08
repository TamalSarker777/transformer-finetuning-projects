# 🦁 Object Detection with DETR on Animal Dataset

This project fine-tunes the [DETR (DEtection TRansformer)](https://arxiv.org/abs/2005.12872) model from Facebook on a custom animal object detection dataset, using the Hugging Face Transformers and Datasets libraries.

---

## 📦 Dataset

- **Source:** [`Francesco/animals-ij5d2`](https://huggingface.co/datasets/Francesco/animals-ij5d2)
- **Type:** Object Detection
- **Format:** COCO-style annotations (images + bounding boxes + category labels)
- **Classes:** 12 animal categories

---

## 🧠 Model

- **Architecture:** `facebook/detr-resnet-50`
- **Framework:** Hugging Face Transformers
- **Task:** Object Detection
- **Modifications:** The classification head is re-initialized to support 12 custom classes (instead of 92 from COCO).

---

## 🔧 Training Configuration

| Setting                     | Value         |
|----------------------------|---------------|
| Epochs                     | 30            |
| Batch Size (train/eval)    | 8             |
| Learning Rate              | 5e-5          |
| Scheduler                  | Cosine        |
| Weight Decay               | 1e-4          |
| Max Grad Norm              | 0.01          |
| Mixed Precision            | Disabled (`fp16=False`) |
| Push to Hub                | Optional (`push_to_hub=False`) |
| Evaluation Strategy        | Per Epoch     |

---

## 📊 Evaluation Metrics

The model is evaluated using **COCO-style metrics**, specifically:

- **mAP** (mean Average Precision)
- **mAR** (mean Average Recall)

Metrics are computed using `torchmetrics` in the `compute_metrics` function.

---

## 🔐 Authentication

This notebook requires authentication to use Hugging Face Hub features (e.g., model loading, pushing):

Set your token securely via environment variable:

```bash
export HF_TOKEN=your_token_here
