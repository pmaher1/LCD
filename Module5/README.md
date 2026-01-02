# Module 5: Methods for Discrete Data - GEE and Generalized Linear Mixed Models (GLMM)

**Duration:** Weeks 12-13 (May 19 - June 2)

## Overview

This module extends the methods from Modules 3 and 4 to handle discrete (primarily binary) outcomes. While the fundamental approaches remain the same - marginal models via GEE and conditional models via mixed models - the non-linear nature of models for discrete data introduces important new complexities. Most notably, the distinction between population-average and subject-specific effects becomes much more pronounced, and the interpretation of parameters requires careful attention.

## Learning Objectives

By the end of this module, students should be able to:

- Extend GEE methodology to binary and other discrete outcomes
- Fit and interpret marginal logistic regression models using GEE
- Understand Generalized Linear Mixed Models (GLMM) for discrete data
- Fit and interpret logistic mixed models (random effects logistic regression)
- Understand why marginal and conditional models give different parameter estimates for non-linear models
- Distinguish between population-average and subject-specific interpretations for discrete outcomes
- Understand the computational challenges of GLMMs
- Choose between GEE and GLMM based on research questions and data characteristics
- Implement both approaches in Stata and R
- Communicate results appropriately for binary outcomes

## Topics Covered

### 1. Binary Outcomes and Logistic Regression: Extension to Correlated Data

#### Review of Standard Logistic Regression
- Binary outcomes in medical research
- Odds ratios and their interpretation
- Link functions and the logit link
- Assumptions of standard logistic regression

#### Challenges with Correlated Binary Data
- Why standard logistic regression fails with correlated data
- Examples: repeated binary measurements, clustered trials
- Underestimation of standard errors when correlation is ignored
- Need for specialized methods

### 2. Marginal Models for Binary Outcomes: GEE Approach

#### Extending GEE to Binary Data
- Generalized estimating equations framework
- Specifying the marginal mean structure
- Logit link for binary outcomes
- Working correlation structures for discrete data

#### Population-Average Interpretation
- Odds ratios as population-average effects
- Averaging over the population
- Interpretation in cluster-randomized trials
- Interpretation in longitudinal studies

#### Practical Implementation
- Fitting marginal logistic models with GEE
- Choosing working correlation structures
- Robust standard errors for binary outcomes
- Model diagnostics and goodness of fit

### 3. Generalized Linear Mixed Models (GLMM) for Binary Outcomes

#### The GLMM Framework
- Extending linear mixed models to non-normal distributions
- Random effects on the logit scale
- Subject-specific logistic regression
- Variance components in GLMMs

#### Logistic Mixed Models
- Random intercepts logistic regression
- Random slopes in logistic models
- Interpretation of random effects
- Subject-specific odds ratios

#### Estimation Challenges
- No closed-form likelihood for GLMMs
- Numerical integration methods: Gauss-Hermite quadrature
- Laplace approximation
- Penalized quasi-likelihood (PQL) - why it can be biased
- Adaptive quadrature
- Computational burden and convergence issues

### 4. Population-Average vs. Subject-Specific Parameters

#### Why They Differ for Non-Linear Models
- In linear models: marginal = conditional (with certain random effects structures)
- In non-linear models: marginal ≠ conditional
- Mathematical explanation of the divergence
- The attenuation effect

#### Magnitude of Differences
- Subject-specific effects are typically larger (odds ratios further from 1)
- Amount of attenuation depends on random effects variance
- Examples demonstrating the difference
- When the difference matters practically

#### Choosing the Right Interpretation
- What is your research question?
- Population-level policy questions → population-average (GEE)
- Individual-level predictions → subject-specific (GLMM)
- Cluster-randomized trials: often population-average
- Prognosis and prediction: usually subject-specific

### 5. Advantages and Disadvantages of Each Approach

#### GEE for Binary Outcomes

**Advantages:**
- Population-average interpretation often more relevant
- Robust to correlation misspecification
- Computationally simpler and more stable
- Consistent estimates even if correlation is wrong
- Well-suited for cluster-randomized trials

**Disadvantages:**
- Cannot provide subject-specific predictions
- Requires MCAR for missing data (more restrictive than GLMMs)
- Cannot estimate random effects or variance components
- May have poor small-sample properties

#### GLMM for Binary Outcomes

**Advantages:**
- Subject-specific interpretation
- Can predict individual outcomes
- Valid under MAR missing data
- Estimates variance components
- Can separate within and between effects

**Disadvantages:**
- Computationally intensive
- Convergence problems common
- Strong distributional assumptions
- More complex interpretation
- Subject-specific effects may not be of primary interest

### 6. Practical Considerations and Case Studies

#### Model Specification
- Choosing covariates and interactions
- Time as a covariate in longitudinal studies
- Categorical vs. continuous time
- Cross-level interactions in hierarchical models

#### Hypothesis Testing
- Wald tests
- Likelihood ratio tests (for GLMMs)
- Testing random effects
- Multiple comparison considerations

#### Model Diagnostics
- Residual analysis for binary outcomes (limited utility)
- Influence diagnostics
- Goodness of fit measures
- Checking convergence

#### Software Comparison
- Stata: `xtgee` for GEE, `melogit` for GLMM
- R: `geepack` for GEE, `lme4::glmer()` for GLMM
- Comparing output across programs
- Computational speed and stability

## Key Concepts

- **GLMM (Generalized Linear Mixed Model):** Extension of linear mixed models to non-normal distributions
- **Marginal Model:** Model for population-average response (via GEE)
- **Conditional Model:** Model for subject-specific response given random effects (via GLMM)
- **Population-Average Effect:** Average effect across all subjects in the population
- **Subject-Specific Effect:** Effect for a particular subject, conditional on their random effects
- **Odds Ratio:** Measure of association for binary outcomes
- **Working Correlation:** Assumed correlation structure in GEE (may be misspecified)
- **Random Effects Variance:** Variability in subject-specific effects (in GLMM)
- **Numerical Integration:** Computational method for approximating integrals in GLMM estimation
- **Attenuation:** The phenomenon where population-average effects are closer to the null than subject-specific effects

## Mathematical Relationships

For logistic regression with random intercepts:

**Subject-Specific Model (GLMM):**
$$\text{logit}(P(Y_{ij}=1|X_{ij}, b_i)) = \beta_0 + \beta_1 X_{ij} + b_i$$

**Population-Average Model (approximation from GLMM):**
$$\text{logit}(P(Y_{ij}=1|X_{ij})) \approx \frac{\beta_0 + \beta_1 X_{ij}}{\sqrt{1 + c^2 \sigma_b^2}}$$

where $c \approx 0.588$ for the logit link and $\sigma_b^2$ is the random effects variance.

This shows how the population-average effect ($\beta_1/\sqrt{1 + c^2 \sigma_b^2}$) is attenuated relative to the subject-specific effect ($\beta_1$).

## Practical Exercises

This module includes extensive practical exercises using both **Stata** and **R** to:
- Fit marginal logistic models using GEE
- Compare different working correlation structures for binary outcomes
- Fit logistic mixed models (GLMMs) with random intercepts
- Fit logistic mixed models with random slopes
- Compare GEE and GLMM results on the same dataset
- Calculate and interpret population-average vs. subject-specific odds ratios
- Explore the relationship between random effects variance and attenuation
- Handle convergence issues in GLMMs
- Compare different numerical integration methods
- Analyze cluster-randomized trials with binary outcomes

## Real-World Examples

Case studies included:
- Cluster-randomized trials with binary health outcomes
- Longitudinal studies of disease incidence
- Dental studies with binary outcomes (caries presence/absence)
- Multi-site clinical trials
- Family studies with binary genetic traits
- Studies with repeated binary diagnostic tests

## Software Implementation

### Stata
- **GEE:** `xtgee` with `family(binomial)` and `link(logit)`
- **GLMM:** `melogit` or `meglm` with `family(binomial)`
- Specifying random effects and integration points
- Comparing model outputs

### R
- **GEE:** `geepack::geeglm()` with `family=binomial(link="logit")`
- **GLMM:** `lme4::glmer()` with `family=binomial(link="logit")`
- Setting number of quadrature points: `nAGQ` argument
- Alternative packages: `GLMMadaptive`, `glmmTMB`
- Extracting and reporting results

## Assessment

Selected exercises from this module will contribute to the **Module 4-6 Assignment** (30%), due **June 10**.

Note: Week 14 (June 2) is designated for questions about Assignment No. 2, with no new material introduced.

## Recommended Readings

Key sections from:
- **Fitzmaurice, Laird, & Ware.** *Applied Longitudinal Analysis* (2004)
  - Chapters on marginal models for discrete data
  - Chapters on generalized linear mixed models
- **Diggle et al.** *Analysis of Longitudinal Data* (2002)
  - Chapters on discrete outcome data
- **Molenberghs & Verbeke.** *Models for Discrete Longitudinal Data* (2005)
  - Comprehensive treatment

Seminal papers:
- **Zeger & Liang (1986).** "Longitudinal data analysis for discrete and continuous outcomes." *Biometrics*
- **Neuhaus, Kalbfleisch, & Hauck (1991).** "A comparison of cluster-specific and population-averaged approaches for analyzing correlated binary data." *International Statistical Review*

Additional readings:
- Papers comparing GEE and GLMM for binary data
- Applications in cluster-randomized trials
- Missing data in discrete outcome analysis

## Prerequisites

Students should have completed:
- **Modules 1-4** (all previous modules)
- Regression Modelling for Biostatistics 1 (RM1) - including logistic regression

Essential prerequisite knowledge:
- Standard logistic regression for binary outcomes
- Odds ratios and their interpretation
- GEE methodology from Module 3
- Mixed models framework from Module 4
- Understanding of population-average vs. subject-specific concepts

## Connection to Future Modules

- **Module 6** will extend these concepts to count data using Poisson and negative binomial models
- The fundamental distinction between population-average (GEE) and subject-specific (GLMM) approaches carries through
- Transition models in Module 6 provide a third framework for longitudinal discrete data

## Critical Comparisons: Continuous vs. Binary Outcomes

| Aspect | Continuous (Modules 3-4) | Binary (Module 5) |
|--------|-------------------------|-------------------|
| **Marginal = Conditional?** | Yes (under certain conditions) | No - they differ substantially |
| **Interpretation challenge** | Moderate | High - must specify population-average vs. subject-specific |
| **Estimation difficulty** | Easier | Harder (especially GLMM) |
| **Convergence issues** | Rare | Common in GLMM |
| **Attenuation effect** | None | Present - affects magnitude of effects |

## Important Notes

1. **The population-average vs. subject-specific distinction is CRUCIAL** in this module. Unlike continuous outcomes where these interpretations often coincide, for binary outcomes they give meaningfully different results.

2. **GLMMs for binary data can be computationally challenging.** Be prepared for:
   - Longer computation times
   - Convergence warnings
   - Need to adjust integration points or try different optimizers

3. **Choice of method should be driven by the research question:**
   - Asking about intervention effects in a population? → GEE (population-average)
   - Predicting individual outcomes? → GLMM (subject-specific)

4. **Missing data considerations matter more** with binary outcomes - understand whether your data are MCAR or MAR and choose methods accordingly.

---

*This is one of the most conceptually challenging modules in the course. The key insight is that for non-linear models, marginal and conditional specifications lead to different parameter values with different interpretations. Take time to understand this distinction thoroughly, as it's essential for correctly interpreting and communicating results from analyses of correlated binary data.*
