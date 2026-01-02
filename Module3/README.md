# Module 3: Methods for Continuous Outcomes Based on Generalised Estimating Equations (GEE)

**Duration:** Weeks 5-7 (March 31 - April 21)

## Overview

This module develops Generalised Estimating Equations (GEE) as a comprehensive method for analyzing correlated continuous outcome data. GEE provides a marginal modeling approach that focuses on population-average effects while properly accounting for the correlation structure within clusters or individuals. This is the first of two major approaches to modeling correlated data covered in this course.

## Learning Objectives

By the end of this module, students should be able to:

- Understand the marginal model approach to correlated data
- Specify and interpret marginal models for continuous outcomes
- Understand how GEE generalizes standard regression for correlated data
- Choose and specify appropriate working correlation structures
- Understand and apply robust (sandwich) standard errors
- Interpret GEE results in terms of population-average effects
- Understand the relationship between random effects and marginal specifications
- Implement GEE models in Stata and R
- Compare GEE results with naive analyses that ignore correlation
- Recognize situations where GEE is appropriate vs. inappropriate

## Topics Covered

### 1. The Marginal Model Approach

#### What is a Marginal Model?
- Focus on the mean response in the population (population-average)
- Modeling the marginal expectation E[Y|X]
- Contrast with conditional (subject-specific) models
- Why marginal models answer certain research questions

#### Generalizing Standard Regression
- Standard linear regression assumes independent observations
- GEE allows for correlated error terms
- Maintaining the same mean structure as standard regression
- Separating mean structure from correlation structure

### 2. Working Correlation Structures

#### Types of Working Correlation Structures
- **Independence:** Assumes no correlation (naive approach)
- **Exchangeable:** Constant correlation between any two observations within a cluster
- **Autoregressive (AR-1):** Correlation decreases with time separation
- **Unstructured:** Different correlation for each pair of time points
- **Other structures:** m-dependent, stationary, etc.

#### Choosing a Working Correlation Structure
- Based on the study design and data
- Exploratory analysis to examine correlation patterns
- Trade-offs between complexity and efficiency
- Impact on estimation and inference

#### Working Correlation vs. True Correlation
- Why it's called "working" correlation
- Consistency of GEE estimates even with misspecified correlation
- Impact of correlation misspecification on efficiency

### 3. Generalised Estimating Equations Methodology

#### The GEE Approach
- Estimating equations: generalizing score equations
- Quasi-likelihood framework
- Iterative estimation algorithm
- Convergence issues and diagnostics

#### Mathematical Framework
- Specification of the mean model
- Specification of the variance function
- Specification of the working correlation matrix
- Building the GEE system

### 4. Robust (Information Sandwich) Standard Errors

#### Why Robust Standard Errors?
- Protection against misspecification of correlation structure
- Empirical vs. model-based standard errors
- The sandwich estimator explained
- When robust SEs are valid and when they're not

#### Model-Based vs. Robust Standard Errors
- Efficiency gains with correct correlation structure
- Comparing different SE estimates
- Impact of small sample sizes on robust SEs
- Degrees of freedom adjustments

### 5. Random Effects Specifications and Relationship to Marginal Models

#### Connecting Random Effects to Marginal Models
- How random effects imply a marginal correlation structure
- Marginal interpretation of random effects models
- When do they give the same results?
- When do they diverge?

#### Population-Average vs. Subject-Specific Effects
- Interpretation differences
- Magnitude of effects
- Collapsibility
- Which interpretation answers your research question?

### 6. Practical Implementation

#### Model Building with GEE
- Specifying the mean structure
- Choosing predictors and interactions
- Testing hypotheses about mean parameters
- Model diagnostics for GEE

#### Software Implementation
- **Stata:** The `xtgee` command and options
- **R:** The `gee`, `geepack`, and `geeM` packages
- Syntax and output interpretation
- Extracting and reporting results

## Key Concepts

- **Marginal Model:** A model for the population-average response as a function of covariates
- **Population-Average Effect:** The average effect in the population, averaging over all subjects
- **Working Correlation:** The assumed correlation structure used in estimation (may differ from true correlation)
- **GEE:** A method for estimating regression parameters in the presence of correlated data
- **Robust Standard Errors:** Standard errors that are consistent even if the correlation structure is misspecified
- **Sandwich Estimator:** A method for computing robust standard errors
- **Quasi-Likelihood:** A generalization of likelihood that doesn't require full distributional assumptions
- **Exchangeable Correlation:** All pairs of observations within a cluster have the same correlation

## Practical Exercises

This module includes extensive practical exercises using both **Stata** and **R** to:
- Fit GEE models with different working correlation structures
- Compare results across different correlation specifications
- Calculate and interpret robust standard errors
- Compare GEE results with naive (independence) models
- Explore the impact of correlation misspecification
- Perform hypothesis tests using GEE
- Diagnose model fit and detect outliers

## Real-World Examples

Case studies included:
- Clinical trials with repeated outcome measurements
- Dental health studies with measurements on multiple teeth
- Family studies with correlated outcomes among relatives
- Longitudinal cohort studies tracking health outcomes over time

## Assessment

Selected exercises from this module will contribute to the **Module 1-3 Assignment** (30%), due **April 28**.

Note: Week 7 (April 21) is designated for questions about Assignment No. 1, with no new material introduced.

## Recommended Readings

Key sections from:
- **Fitzmaurice, Laird, & Ware.** *Applied Longitudinal Analysis* (2004)
  - Chapters on marginal models and GEE
- **Diggle et al.** *Analysis of Longitudinal Data* (2002)
  - Chapters on marginal models and estimating equations
- **Liang & Zeger (1986).** "Longitudinal data analysis using generalized linear models." *Biometrika*
  - Seminal paper introducing GEE

Additional readings:
- Papers comparing GEE with mixed models
- Applications of GEE in medical research
- Technical papers on robust inference

## Prerequisites

Students should have completed:
- **Module 1** (Introduction to Correlated Data)
- **Module 2** (Overview of Correlated Data Structures)
- Regression Modelling for Biostatistics 1 (RM1)

Essential prerequisite knowledge:
- Linear regression for continuous outcomes
- Hypothesis testing and confidence intervals
- Correlation and covariance concepts
- Basic understanding of random effects (from Module 1)

## Connection to Future Modules

- **Module 4** will present an alternative approach using likelihood-based mixed models for continuous outcomes
  - Direct comparison of GEE vs. mixed models
  - Understanding when to use each approach
- **Module 5** will extend GEE to discrete (binary) outcomes
- **Module 6** will extend GEE to count outcomes

## Important Considerations

### When to Use GEE

GEE is particularly appropriate when:
- Primary interest is in population-average effects
- Data are clustered or longitudinal
- Correlation structure may be uncertain
- Robust inference is desired
- Missing data are missing completely at random (MCAR)

### When GEE May Not Be Ideal

- Primary interest is in subject-specific predictions
- Missing data are not MCAR (see Module 4 for alternatives)
- Small number of clusters (robust SEs may be unreliable)
- Interest in variance components or random effects
- Complex correlation structures that are scientifically interesting

## Key Skills Developed

By completing this module, students will:
1. Understand the conceptual framework of marginal models
2. Be able to specify and fit GEE models for continuous outcomes
3. Know how to choose appropriate working correlation structures
4. Understand the role and interpretation of robust standard errors
5. Be able to interpret population-average effects
6. Recognize the relationship between marginal and conditional models
7. Develop proficiency in Stata/R for GEE analysis

---

*This module introduces one of the two major paradigms for analyzing correlated data. Understanding the marginal modeling approach and its implementation through GEE is crucial for the remainder of the course. Pay special attention to the interpretation of population-average vs. subject-specific effects, as this distinction becomes even more important in later modules dealing with non-linear models.*
