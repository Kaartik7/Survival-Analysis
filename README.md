**Efficacy of Different Treatment Modalities for Cannabis Addiction**

Simulation-Based Survival Analysis Study
Authors: Kaartik Issar, Tanya Thaker

**Overview**

This project investigates the effectiveness of three treatment modalities used in cannabis addiction therapy—Cognitive Behavioral Therapy (CBT), CBT combined with Motivational Enhancement Therapy (CBT+MET), and Peer Support—through a simulation-based survival analysis framework.

Using published abstinence/relapse rates, we simulate time-to-event data (time to achieving six months of abstinence) under three different levels of censoring: 10%, 30%, and 60%. We then evaluate the performance of parametric survival models (Weibull, Lognormal, Log-logistic) and assess how censoring impacts:

**Model fit**

Estimation of treatment effects

Confidence interval widths

Interpretation of treatment efficacy

The project is implemented in R, using packages such as tidyverse, survival, and dplyr.

**Objectives**

Simulate realistic addiction-treatment time-to-event data with varying censoring rates.

Evaluate parametric survival models to determine which distribution best fits the underlying data-generating process.

Compare treatment effectiveness across CBT, CBT+MET, and Peer Support interventions.

Analyze the effect of censoring on statistical inference—particularly confidence intervals and effect-size estimation.

Interpret the implications for real-world addiction-treatment studies.

**Methodology Summary**
Data Generation

Each treatment modality is simulated with sample size n = 500.

Success probabilities are derived from literature:

CBT: 51% abstinence

CBT+MET: 81% abstinence

Peer Support: 86% abstinence

Relapse outcomes follow a binomial distribution.

Time-to-event is bounded between 0–6 months.

Datasets are generated under 10%, 30%, and 60% censoring.

Modeling

We apply:

Kaplan–Meier estimators

Weibull, Lognormal, and Log-logistic survival models (survreg)

Likelihood Ratio Tests to compare null vs. treatment-augmented models

Confidence interval analysis to evaluate precision under different censoring levels

**Key Findings**
1. Best-Fit Model: Lognormal Distribution

Across all censoring scenarios, lognormal survival models produced the straightest transformed Kaplan–Meier lines, indicating the strongest distributional fit.

2. Treatment Effects Are Statistically Significant

Likelihood ratio tests consistently reject the null model
(p ≈ 2.7e−07 for 10% censoring dataset),
supporting that treatment type significantly influences abstinence duration.

3. Censoring Increases Uncertainty

Mean confidence-interval widths:

Censoring	Mean CI Width
10%	0.4858
30%	0.5032
60%	0.5233

Higher censoring → less precise estimates → attenuated treatment-effect coefficients.

4. Treatment Effect Sizes Shrink with More Censoring

Estimated treatment coefficients decrease as censoring increases, highlighting:

Reduced statistical power

Underestimation of true treatment effects

The need for careful censoring-handling in addiction research

**Visualizations**

The project includes:

Kaplan–Meier curves

Distribution-transformed diagnostic plots for each model

Line plots tracking confidence-interval widths across censoring levels

All visualizations are generated directly through the R script.
