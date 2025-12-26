# Contributions and Failure Taxonomy

## Contributions

This work makes the following contributions:

### Contribution 1: Cost-First Evaluation of HITL Systems**  
   We reformulate human-in-the-loop (HITL) decision systems as cost-optimization problems rather than accuracy-optimization problems. Unlike prior work that evaluates HITL using classification metrics (e.g., precision, recall, AUC), we evaluate performance using total expected operational cost, explicitly modeling false positives, false negatives, and human review costs.

### Contribution 2: Decision-Layer Optimization Without Retraining**  
   We demonstrate that substantial performance differences can be achieved without retraining the underlying model, purely through threshold selection and selective human review policies. This isolates the decision layer as a dominant driver of system performance under asymmetric error costs.

### Contribution 3: Negative Results for Naïve HITL Policies**  
   We provide empirical evidence that naïvely applied HITL policies can increase total expected cost, even when human reviewers outperform the model on false positives. This serves as a counterexample to the common assumption that adding human review is inherently beneficial.

### Contribution 4: Cost-Regime–Dependent HITL Effectiveness**  
   We identify distinct economic regimes in which:
   - Fully automated decision-making is optimal  
   - Selective HITL yields marginal gains  
   - HITL intervention strictly degrades system-level performance  

   These regimes are determined jointly by error cost asymmetry, human review cost, and review allocation strategy.

### Contribution 5: Actionable Guidance for AML Deployment**  
   Using AML transaction monitoring as a case study, we derive operationally relevant guidance for when human review should be deployed, how selectively it should be applied, and when it should be avoided entirely.

---

## Failure Taxonomy for Human-in-the-Loop Systems

We formalize the following failure modes for HITL decision systems:

### Failure Mode 1: Cost-Blind HITL Deployment
Human review is added without explicitly modeling review cost or error asymmetry.  
**Outcome:** Reduced false positives but increased total expected cost.

### Failure Mode 2: Recall-Dominant Cost Regimes
False-negative costs are low relative to human review costs.  
**Outcome:** HITL intervention degrades performance despite improved apparent precision.

### Failure Mode 3: Over-Broad Review Policies
Fixed or high review rates are applied uniformly across all flagged cases rather than selectively.  
**Outcome:** Human effort is wasted on low-risk cases, eroding cost efficiency.

### Failure Mode 4: Metric Illusion
Improvements in standard machine learning metrics mask worsening operational outcomes.  
**Outcome:** Systems appear improved while becoming economically inefficient.

### Failure Mode 5: Human Superiority Fallacy
Assuming that higher human accuracy on reviewed cases guarantees system-level improvement.  
**Outcome:** Local gains fail to translate into global cost reductions.

---

## Implications

This taxonomy demonstrates that HITL effectiveness is not a function of human accuracy alone, but depends on where, when, and at what cost human intervention is applied. HITL systems must therefore be designed and evaluated as economic decision systems rather than hybrid classifiers.

---

## Positioning Statement

This work reframes human-in-the-loop decision-making from a presumed best practice into a conditional design choice. By explicitly documenting failure cases and negative results, it challenges prevailing assumptions in applied machine learning and provides a principled framework for deciding when human intervention helps—and when it hurts.
