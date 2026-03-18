# Labeling Guide: Policy Claim Classification

## Decision Tree
Apply questions **in order**. Stop at the first "Yes."

### Step 1 → Inclusion
**Is a specific disadvantaged group explicitly mentioned?**
- Keywords: women, girls, disabled, elderly, rural, refugees, migrants, indigenous, children, youth in developing countries, low-income countries, minorities, poorest populations
- Example: *"Women are 16% less likely than men to use mobile internet."* → **Inclusion**

### Step 2 → Regulation
**Is enacting / amending / enforcing a law or regulation the core action?**
- Keywords: law, legislation, regulation, mandate, prohibit, ban, fine, penalty, audit, compliance, enforce, liability, data protection act
- Example: *"AI systems posing unacceptable risks must be prohibited."* → **Regulation**

### Step 3 → Infrastructure
**Is building / investing in / deploying a physical or technical system the core action?**
- Keywords: broadband, 5G, data center, cloud, network, server, satellite, fiber-optic, energy, GPU, compute, platform
- Example: *"5G coverage reached 57% of the global population in 2024."* → **Infrastructure**

### Step 4 → Capacity
**Is human education / training / skills development the core action?**
- Keywords: education, training, curriculum, digital literacy, reskilling, upskilling, university, PhD, workforce, talent
- Example: *"Education systems must be reformed for AI-enabled economies."* → **Capacity**

### Step 5 → Strategy
**None of the above (broad direction, vision, coordination)**
- Keywords: national strategy, coordination, international cooperation, R&D priority, governance framework, innovation ecosystem
- Example: *"Countries should develop national AI strategies."* → **Strategy**

## Boundary Cases
| Claim | Label | Reasoning |
|---|---|---|
| "Digital skills training for rural women" | Inclusion | "Rural women" = disadvantaged group → Stop at Step 1 |
| "Government should prioritize education in AI strategy" | Strategy | No group, no law, no infra, "prioritize in strategy" → Step 5 |
| "Expand broadband to close rural digital divide" | Inclusion | "Rural" = disadvantaged group → Stop at Step 1 |
| "Expand broadband infrastructure" | Infrastructure | No group, physical system → Step 3 |
| "Mandate AI transparency by law" | Regulation | No group, "mandate by law" → Step 2 |

## Rules
- If ambiguous, **skip the claim** — clean 200 > messy 300
- One label per claim — no multi-label
- Decision tree order is strict — do not jump steps
