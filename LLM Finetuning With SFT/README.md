# 🧠 Fine-Tuning DeepSeek-R1-Distill-Qwen-1.5B with LoRA on smoltalk apigen-80k

This project sets up parameter-efficient fine-tuning (PEFT) using **LoRA** on the model [`deepseek-ai/DeepSeek-R1-Distill-Qwen-1.5B`](https://huggingface.co/deepseek-ai/DeepSeek-R1-Distill-Qwen-1.5B), using the **`apigen-80k`** split of the [`HuggingFaceTB/smoltalk`](https://huggingface.co/datasets/HuggingFaceTB/smoltalk) dataset.

> ⚠️ **Note**: Training was started successfully but not completed due to GPU resource constraints. All configuration and training setup are fully functional and ready for continuation.

---

## 📚 Dataset

- **Name**: `HuggingFaceTB/smoltalk`
- **Split**: `apigen-80k`
- **Format**: Chat-style (`messages: List[{"role": ..., "content": ...}]`)

---

## 🧠 Model

- **Base Model**: [`deepseek-ai/DeepSeek-R1-Distill-Qwen-1.5B`](https://huggingface.co/deepseek-ai/DeepSeek-R1-Distill-Qwen-1.5B)
- **Architecture**: Qwen-compatible


---

## ⚙️ LoRA Configuration

```python
LoraConfig(
    r=6,
    lora_alpha=8,
    lora_dropout=0.05,
    bias="none",
    target_modules=["q_proj", "v_proj"],
    task_type="CAUSAL_LM"
)
