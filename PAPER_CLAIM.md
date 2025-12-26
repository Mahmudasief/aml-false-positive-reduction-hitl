# Research Claim: Cost-Sensitive Decision Policies for AML Systems

## Core Claim
Human-in-the-loop (HITL) interventions in anti–money laundering (AML) monitoring systems are **not inherently risk-reducing**.  
Their effectiveness depends critically on **cost asymmetry, decision thresholding, and selective human review policies** rather than model choice alone.

## Motivation
Production AML systems frequently:
- Optimize statistical metrics (AUC, recall) instead of economic loss
- Introduce human review assuming it universally reduces risk
- Ignore explicit false-positive, false-negative, and review costs

This work demonstrates that such assumptions can **increase total expected loss**.

## Key Findings
- Cost-sensitive threshold optimization can substantially reduce expected loss **without retraining models**
- Naive HITL policies often **increase total cost**, despite reducing false positives
- HITL effectiveness is **cost-regime dependent**, not universally beneficial
- Random Forest with optimized threshold outperforms Logistic Regression under asymmetric AML costs
- Selective human review policies are necessary to justify HITL deployment

## Contributions
1. A cost-aware threshold optimization framework for AML classifiers
2. An empirical evaluation of HITL policies under varying cost regimes
3. Evidence that HITL can increase expected loss when applied indiscriminately
4. Practical guidance for selective, economically justified human review

## Paper Type
Applied machine learning systems / decision analytics / financial crime risk

## Intended Audience
- Academic researchers in ML systems and decision science
- AML practitioners and risk model governance teams

## Positioning Statement
This paper reframes AML modeling as a **decision policy optimization problem**, showing that
economic modeling and system-level reasoning matter more than marginal gains in predictive accuracy.
