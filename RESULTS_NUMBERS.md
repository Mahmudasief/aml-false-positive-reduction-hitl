# RESULTS_NUMBERS

This file reports **only quantitative results** produced by the experimental notebooks.
No interpretation or narrative is provided here.

---

## Dataset
- Test set size: **85,443** transactions
- Positive class (fraud) in test set: **22**

---

## Baseline Automated Models (Cost-Sensitive Thresholding)

**Cost parameters (baseline setting):**
- False Positive cost (FP): **5**
- False Negative cost (FN): **500**
- Human review cost: **not applicable**

| Model               | Optimal Threshold | Total Cost |
|--------------------|------------------|------------|
| Random Forest      | 0.05             | **11,595** |
| Logistic Regression| 0.01             | 14,880     |

Random Forest achieves the lowest baseline total expected cost.

---

## Human-in-the-Loop (HITL): Fixed-Rate Review

**Configuration:**
- Threshold: 0.05
- Manual review rate: 5%
- Human FP correction rate: 70%
- Human review cost: 20 per case

| Model                  | FP After | FN | Human Reviews | Total Cost |
|------------------------|----------|----|---------------|------------|
| Random Forest + HITL   | 115      | 22 | 12            | **11,835** |

Result:
- HITL **does not beat** the automated baseline (11,835 > 11,595).

---

## Selective HITL (Top-k High-Risk Alerts)

**Configuration:**
- Threshold: 0.05
- Top-k review rate: 20%
- Human FP correction rate: 70%
- Human review cost: 20 per case

| FP After | FN | Human Reviews | Total Cost |
|---------|----|---------------|------------|
| 103     | 22 | 49            | **12,495** |

Result:
- Selective HITL reduces false positives but **increases total cost** relative to baseline.

---

## HITL Grid Search (Cost Regime Analysis)

**Grid dimensions:**
- FP cost ∈ {1, 5, 10, 20}
- FN cost ∈ {50, 100, 200, 500, 1000}
- Human review cost ∈ {5, 10, 20, 50}
- Review rate ∈ {5%, 10%, 20%}

**Summary:**
- Total HITL configurations evaluated: **multiple cost regimes**
- Number of configurations that beat their corresponding automated baseline: **45**
- Number of configurations that beat the baseline under the primary cost setting (FP=5, FN=500, human cost=20): **0**

---

## Best HITL Policy Under Primary Cost Setting

| Threshold | Review Rate | FP Fix Rate | Human Reviews | FP After | FN | Total Cost | Beats Baseline |
|---------|-------------|-------------|---------------|----------|----|------------|----------------|
| 0.05    | 5%          | 50%         | 12            | 119      | 22 | 11,835     | False          |

---

## Key Numerical Takeaways
- Automated Random Forest baseline cost: **11,595**
- Best HITL cost under main regime: **11,835**
- HITL improves total cost **only in specific cost regimes**, not in the primary AML cost setting.
- **None of the top-cost-minimizing HITL policies beat the baseline** under the main cost assumptions.
