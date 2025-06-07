# 🧠 Human Parsing with Semantic Segmentation

This project demonstrates training a **semantic segmentation model** using the Hugging Face Transformers library on the [`mattmdjaga/human_parsing_dataset`](https://huggingface.co/datasets/mattmdjaga/human_parsing_dataset), based on the ATR dataset. The goal is to parse human images into fine-grained parts such as clothing, limbs, and accessories.

---
- **Name:** `mattmdjaga/human_parsing_dataset`
- **Total Samples:** 17,706 (image + segmentation mask pairs)
- **Labels (18):**  
  `"Background", "Hat", "Hair", "Sunglasses", "Upper-clothes", "Skirt", "Pants", "Dress", "Belt", "Left-shoe", "Right-shoe", "Face", "Left-leg", "Right-leg", "Left-arm", "Right-arm", "Bag", "Scarf"`

## 🚀 Training Configuration

| Setting                     | Value           |
|----------------------------|-----------------|
| Epochs                     | 5               |
| Batch Size (train/eval)    | 5               |
| Learning Rate              | 6e-5            |
| Logging Steps              | 1               |
| Eval/Save Steps            | 20              |
| Eval Accumulation Steps    | 1               |



## ✅ Evaluation Results (Example)

- **Mean IoU:** `~0.50`
- **Mean Accuracy:** `~0.61`
- **Overall Accuracy:** `~0.77`

Some classes had `IoU = 0.0` or `NaN` due to low representation in the small validation set.

---
