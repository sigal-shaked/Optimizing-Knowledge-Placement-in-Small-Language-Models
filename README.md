# Hybrid Fine-Tuning and Retrieval for Knowledge-Aware QA

This repository accompanies the paper:

**"Optimizing Knowledge Placement in Small Language Models"**  
(accepted to *ICPRAM 2026*)

The project investigates how to combine **parametric knowledge** (fine-tuning) and **non-parametric retrieval** to improve factual accuracy and generalization in question answering.

---

## Overview

We study three complementary approaches:

- **FT-only** – a fine-tuned language model relying solely on internalized knowledge  
- **RAG-extractive** – a retrieval-only baseline that answers by extracting passages  
- **RAG-generative** – a retrieval baseline that answers by extracting passages, aided by a non finetuned SLM.
- **Hybrid FT + RAG** – a combined approach integrating retrieved evidence and finetuned SLM during generation  

---

## Repository Structure

```
.
├── configs/
│   ├── stage1_pretrain.yaml      # QLoRA fine-tuning on stable knowledge
│   └── stage2_sft.yaml           # Supervised fine-tuning with retrieved context
│
└── README.md
```

---

## Training Setup

- **Base model:** Mistral-7B-Instruct-v0.2  
- **Fine-tuning:** QLoRA (4-bit NF4)  
- **Sequence length:** 1760  
- **Optimizer:** AdamW (8-bit)  
- **Hardware:** 3× NVIDIA H100 GPUs  
- **Training time:** ~13 hours  

---

## Reproducibility

All training configurations used in the paper are provided in the `configs/` directory.

---

## Citation

```bibtex
@inproceedings{yourname2026hybrid,
  title     = {Optimizing Knowledge Placement in Small Language Models},
  author    = {Author Names},
  booktitle = {Proceedings of the International Conference on Pattern Recognition Applications and Methods (ICPRAM)},
  year      = {2026}
}
```
