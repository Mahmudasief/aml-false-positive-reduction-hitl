## Title (working)
Human-in-the-Loop Decision Systems Under Asymmetric Error Costs: When Manual Review Increases Expected Loss

## Abstract

Anti-money laundering (AML) transaction monitoring systems are typically evaluated using classification metrics such as recall or AUC, while largely ignoring downstream operational costs associated with false positives, false negatives, and human investigations. In practice, these costs dominate system performance and determine economic viability. This study examines whether cost-sensitive machine learning and human-in-the-loop (HITL) interventions can reduce total expected operational cost in AML monitoring systems, rather than merely improving predictive accuracy.

Using a supervised fraud detection setting with severe class imbalance, we evaluate baseline automated models, cost-aware decision thresholding, and multiple HITL policies, including fixed-rate and selective top-risk human review strategies. We show that cost-sensitive decision threshold optimization alone can materially reduce false positives without retraining the underlying model. However, HITL interventions do not universally improve outcomes. Across broad cost regimes, naively applied human review policies increase total expected cost despite reducing false positives.

Economic gains from HITL arise only under specific conditions: false-negative costs must be sufficiently high, human review costs sufficiently low, and human effort selectively allocated to the highest-risk alerts. In low false-negative or high human-cost regimes, HITL strictly degrades system-level performance. These findings demonstrate that the effectiveness of HITL in AML systems is cost-regime dependent and cannot be justified without explicit economic modeling.

This work provides a cautionary counterexample to prevailing assumptions that human intervention is inherently beneficial and offers principled guidance for deploying manual review only when cost asymmetry, workload, and error trade-offs jointly justify intervention.
