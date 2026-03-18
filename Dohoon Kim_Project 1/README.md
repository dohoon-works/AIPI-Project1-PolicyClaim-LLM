# Policy Claim Classification via LLM Fine-Tuning

**Duke AIPI — Project 1 | Dohoon Kim**

## What This Project Does

Measuring and Improving an open-source LLM's ability to classify policy claims from international policy documents into 5 categories:

| Category | What It Captures |
|---|---|
| **Strategy** | National direction, coordination, international cooperation |
| **Regulation** | Laws, rules, enforcement, audits, penalties |
| **Infrastructure** | Networks, data centers, cloud, energy, hardware |
| **Capacity** | Education, training, workforce skills, digital literacy |
| **Inclusion** | Access and equity for disadvantaged groups |

## Method

- **Model:** Llama 3.1 8B Instruct (Meta)
- **Fine-tuning:** SFT + QLoRA (rank 16, alpha 32) via Unsloth
- **Compute:** Google Colab T4 GPU (16 GB VRAM)
- **Dataset:** 193 claims from 7 international policy documents (143 train / 50 test)

## Results

| Metric | Baseline (zero-shot) | Fine-tuned (QLoRA) | Δ Change |
|---|---|---|---|
| Accuracy | 0.837 (83.7%) | 0.940 (94.0%) | +10.3%p |
| Macro F1 | 0.838 | 0.941 | +0.103 |
| Invalid Rate | 14.0% | 0.0% | -14.0%p |

### Per-Class F1

| Category | Baseline | Fine-Tuned | Δ |
|---|---|---|---|
| Strategy | 0.67 | 0.95 | +0.28 |
| Regulation | 0.95 | 0.95 | 0.00 |
| Infrastructure | 0.75 | 0.91 | +0.16 |
| Capacity | 0.82 | 0.95 | +0.13 |
| Inclusion | 1.00 | 0.95 | -0.05 |

## How to Run (Google Colab)

1. Upload the ZIP to Colab
2. Enable T4 GPU: Runtime → Change runtime type → T4 GPU
3. Run `notebooks/full_pipeline_colab.ipynb` cells in order (01→02→03→04)

## Repo Structure

```
Dohoon Kim_Project 1/
├── README.md
├── data/
│   ├── sources.csv                   ← 7 source document metadata + URLs
│   ├── policy_claims_dataset.xlsx    ← Full labeled dataset with labeling guide
│   ├── train.jsonl                   ← 143 training samples
│   └── test.jsonl                    ← 50 test samples
├── notebooks/
│   └── full_pipeline_colab.ipynb     ← Complete pipeline (data → baseline → fine-tune → eval)
├── results/
│   ├── baseline_metrics.json
│   ├── finetuned_metrics.json
│   ├── predictions.csv
│   ├── dataset_distribution.png
│   ├── confusion_baseline.png
│   ├── confusion_comparison.png
│   └── per_class_f1_comparison.png
└── docs/
    ├── project_plan.docx
    └── labeling_guide.md
```

## Literature Review

1. **Zhao et al. (2024)** — *LoRA Land: 310 Fine-tuned LLMs that Rival GPT-4.* QLoRA fine-tuning of 8B models outperforms GPT-4 on 85% of classification tasks. [arXiv:2405.00732](https://arxiv.org/abs/2405.00732)
2. **Peña et al. (2023)** — *Leveraging LLMs for Topic Classification in Public Affairs.* LLM-based classification of 33K+ public documents for policy analysis. [arXiv:2306.02864](https://arxiv.org/abs/2306.02864)
