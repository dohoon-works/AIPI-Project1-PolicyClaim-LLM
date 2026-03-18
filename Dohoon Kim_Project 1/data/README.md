# Dataset: Policy Claim Classification

## Overview
- **Total claims:** 193 (143 train / 50 test)
- **Categories:** 5 (Strategy, Regulation, Infrastructure, Capacity, Inclusion)
- **Format:** JSONL with system/user/assistant messages
- **Split:** Stratified 80/20, minimum 10 per category in test

## Labeling Decision Tree
Apply in order. Stop at first "Yes."

| Step | Question | If Yes → |
|------|----------|----------|
| 1 | Specific disadvantaged group mentioned? | **Inclusion** |
| 2 | Law/regulation enactment/enforcement is core? | **Regulation** |
| 3 | Physical/technical system build/deploy is core? | **Infrastructure** |
| 4 | Human education/training/skills is core? | **Capacity** |
| 5 | None of the above | **Strategy** |
