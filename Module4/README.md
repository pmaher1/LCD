# Module 4: Methods for Continuous Outcomes Based on Normal Mixed Models

**Duration:** Weeks 9-11 (April 28 - May 19)

## Overview

This module introduces the second major approach to analyzing correlated continuous data: likelihood-based mixed models (also called multilevel models or hierarchical linear models). While Module 3 focused on the marginal modeling approach via GEE, this module develops the conditional modeling framework that explicitly includes random effects and uses likelihood-based estimation. This approach offers different interpretations and handles missing data differently than GEE.

## Learning Objectives

By the end of this module, students should be able to:

- Understand the mixed model (conditional/hierarchical) framework for correlated data
- Specify and interpret linear mixed models with random intercepts and slopes
- Understand likelihood-based estimation: Maximum Likelihood (ML) and Restricted Maximum Likelihood (REML)
- Distinguish between fixed effects and random effects
- Separate within-subject and between-subject effects
- Compare and contrast mixed models with GEE approaches
- Understand the relationship between classical repeated measures ANOVA and modern mixed models
- Understand how missing data mechanisms affect different estimation approaches
- Implement mixed models in Stata and R
- Interpret subject-specific predictions and population-average effects from mixed models

## Topics Covered

### 1. The Mixed Model Framework

#### What is a Mixed Model?
- Combination of fixed effects and random effects
- Conditional (subject-specific) model specification
- Hierarchical/multilevel structure
- Variance components model

#### Components of a Mixed Model
- **Fixed effects:** Population-level parameters (same as in standard regression)
- **Random effects:** Subject-specific or cluster-specific deviations
- **Within-subject errors:** Residual variation after accounting for random effects
- Model specification and notation

#### Random Intercepts Models
- Subject-specific intercepts
- Interpretation and visualization
- Variance components: between-subject and within-subject
- Intraclass correlation in the mixed model framework

#### Random Slopes Models
- Subject-specific slopes (growth rates)
- Correlation between random intercepts and slopes
- Unstructured vs. simplified covariance structures
- Interpretation of variance components

### 2. Likelihood-Based Estimation

#### Maximum Likelihood (ML) Estimation
- Likelihood function for mixed models
- Assumptions: multivariate normality
- Properties of ML estimators
- Why ML can bias variance estimates downward

#### Restricted Maximum Likelihood (REML)
- Accounting for degrees of freedom lost in estimating fixed effects
- Unbiased estimation of variance components
- When to use ML vs. REML
- Implications for model comparison

#### Estimation Algorithms
- Expectation-Maximization (EM) algorithm
- Newton-Raphson and Fisher scoring
- Convergence issues and diagnostics
- Computational considerations

#### Inference for Fixed Effects
- Standard errors and confidence intervals
- Hypothesis tests (Wald tests, likelihood ratio tests)
- Degrees of freedom considerations
- Small sample corrections

#### Inference for Random Effects
- Testing variance components
- Boundary constraints (variances must be non-negative)
- Likelihood ratio tests for random effects
- BLUPs: Best Linear Unbiased Predictors

### 3. Alternative Approaches to Estimation

#### Weighted/Generalised Least Squares (GLS)
- When the correlation structure is known
- Efficient estimation with known covariance
- Relationship to likelihood-based methods
- Historical perspective

#### Comparison of Estimation Methods
- GEE vs. likelihood-based mixed models
- Efficiency considerations
- Robustness to misspecification
- Computational burden

### 4. Separating Between-Subject and Within-Subject Effects

#### Why Separate These Effects?
- Different research questions
- Ecological fallacy and Simpson's paradox
- Contextual effects in clustered data

#### Centering Strategies
- Grand-mean centering
- Group-mean (cluster-mean) centering
- Between-within decomposition
- Interpretation of centered predictors

#### Practical Implementation
- Creating within-subject and between-subject variables
- Fitting models with decomposed effects
- Comparing within vs. between effects
- Testing equality of effects

### 5. Classical Repeated Measures ANOVA and Modern Approaches

#### Traditional Repeated Measures ANOVA
- Compound symmetry assumption
- Sphericity and the Greenhouse-Geisser correction
- Multivariate approach to repeated measures
- Limitations of classical ANOVA

#### Relationship to Mixed Models
- Mixed models as a generalization of RM-ANOVA
- Relaxing the compound symmetry assumption
- Handling unbalanced data and missing observations
- Flexible covariance structures

#### When to Use Classical vs. Modern Approaches
- Balanced designs with no missing data: similar results
- Unbalanced or incomplete data: mixed models preferred
- Complex correlation patterns: mixed models more flexible

### 6. Missing Data Mechanisms and Implications

#### Missing Data Mechanisms
- **MCAR (Missing Completely At Random):** Missingness unrelated to any variable
- **MAR (Missing At Random):** Missingness related to observed data only
- **MNAR (Missing Not At Random):** Missingness related to unobserved data

#### Implications for GEE
- GEE requires MCAR for unbiased estimates
- Weighted GEE for MAR (advanced topic)
- Limitations when data are not MCAR

#### Implications for Likelihood-Based Methods
- ML/REML valid under MAR (ignorable missingness)
- More robust to missing data than GEE
- Importance of including variables related to missingness
- When missingness is MNAR: need specialized methods

#### Practical Considerations
- Assessing the missing data mechanism
- Sensitivity analyses
- Multiple imputation as an alternative

## Key Concepts

- **Mixed Model:** A model containing both fixed effects and random effects
- **Fixed Effects:** Parameters that are constant across all subjects in the population
- **Random Effects:** Parameters that vary randomly across subjects or clusters
- **Variance Components:** Variances of random effects and residual errors
- **REML:** Restricted Maximum Likelihood, an estimation method that provides unbiased variance estimates
- **BLUPs:** Best Linear Unbiased Predictors of random effects for specific subjects
- **Subject-Specific Effect:** Effect for a particular subject, conditional on their random effects
- **Between-Subject Effect:** Association across different subjects
- **Within-Subject Effect:** Association from changes within the same subject
- **MAR:** Missing At Random, a missing data mechanism where missingness depends only on observed data

## Practical Exercises

This module includes extensive practical exercises using both **Stata** and **R** to:
- Fit random intercepts and random slopes models
- Compare ML and REML estimation
- Obtain and interpret BLUPs (predicted random effects)
- Decompose effects into within-subject and between-subject components
- Compare mixed model results with GEE results
- Explore the impact of missing data on different estimation approaches
- Fit classical repeated measures ANOVA and compare with mixed models
- Conduct likelihood ratio tests for variance components
- Visualize subject-specific trajectories

## Real-World Examples

Case studies included:
- Growth studies: height/weight trajectories in children
- Clinical trials: treatment effects over time
- Educational research: student outcomes clustered within schools
- Dental studies: tooth measurements within individuals
- Studies with dropout: comparing complete case vs. full likelihood analysis

## Software Implementation

### Stata Commands
- `mixed`: For fitting linear mixed models
- `meglm`: Generalized linear mixed models framework
- Options for specifying random effects, covariance structures
- Post-estimation commands for predictions, residuals, BLUPs

### R Packages and Functions
- `lme4::lmer()`: Primary function for linear mixed models
- `nlme::lme()`: Alternative with more flexible covariance structures
- `lmerTest`: For p-values and degrees of freedom
- Model specification syntax
- Extracting and plotting results

## Assessment

Selected exercises from this module will contribute to the **Module 4-5 Short Assessment** (20%), due **May 19**.

## Recommended Readings

Key sections from:
- **Fitzmaurice, Laird, & Ware.** *Applied Longitudinal Analysis* (2004)
  - Chapters on linear mixed effects models and likelihood-based inference
- **Verbeke & Molenberghs.** *Linear Mixed Models for Longitudinal Data* (2000)
  - Comprehensive treatment of theory and applications
- **Singer & Willett.** *Applied Longitudinal Data Analysis* (2003)
  - Growth modeling perspective
- **Diggle et al.** *Analysis of Longitudinal Data* (2002)
  - Chapters on random effects models

Additional readings:
- Papers on missing data mechanisms and implications
- Comparisons of GEE and mixed models
- Applications in various medical research contexts

## Prerequisites

Students should have completed:
- **Modules 1-3** (Introduction to Correlated Data, Overview, and GEE methods)
- Principles of Statistical Inference (PSI) - for likelihood concepts
- Regression Modelling for Biostatistics 1 (RM1)

Essential prerequisite knowledge:
- Understanding of likelihood and maximum likelihood estimation
- Random effects concepts from Module 1
- GEE methodology from Module 3
- Linear regression

## Connection to Future Modules

- **Module 5** will extend mixed models to discrete outcomes (Generalized Linear Mixed Models)
  - Similar framework but with non-normal distributions
  - Additional complexity in estimation and interpretation
- **Module 6** will apply these concepts to count data
- Throughout Modules 5-6: continued comparison of marginal (GEE) vs. conditional (mixed model) approaches

## GEE vs. Mixed Models: Key Comparisons

| Aspect | GEE (Module 3) | Mixed Models (Module 4) |
|--------|----------------|-------------------------|
| **Target of inference** | Population-average | Subject-specific (can also get population-average) |
| **Estimation** | Quasi-likelihood | Full likelihood (ML/REML) |
| **Correlation** | Working correlation (may be misspecified) | Modeled via random effects |
| **Standard errors** | Robust (sandwich) | Model-based |
| **Missing data** | Requires MCAR | Valid under MAR |
| **Software** | Generally simpler | May be more complex |
| **Variance components** | Not directly modeled | Explicitly estimated |
| **Subject-specific predictions** | Not available | Available via BLUPs |

## Important Considerations

### When to Use Mixed Models

Mixed models are particularly appropriate when:
- Interest in subject-specific predictions or effects
- Missing data are MAR but not MCAR
- Interest in variance components (how much variation is between vs. within subjects)
- Hierarchical/multilevel structure is of scientific interest
- Within-subject and between-subject effects need to be separated

### Challenges with Mixed Models

- More assumptions than GEE (distributional assumptions)
- Can be computationally intensive with complex random effects
- Model selection for random effects structure can be challenging
- Interpretation is more complex with non-linear models (Module 5)

---

*This module presents the second major framework for correlated data analysis. Understanding the differences between marginal (GEE) and conditional (mixed model) approaches is crucial. Both are important tools, and choosing between them depends on your research questions, missing data patterns, and interpretation goals. The concepts from this module become especially important in Module 5 when we move to non-normal outcomes.*
