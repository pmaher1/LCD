# Module 6: Methods for Count Data and Transition Models

**Duration:** Module materials available after Module 5 completion

## Overview

This final module extends the GEE and GLMM frameworks to count outcomes and introduces an alternative modeling approach - transition (Markov) models - that is particularly useful for longitudinal data. Count data are common in medical research (number of events, disease occurrences, hospital visits, etc.), and the methods developed in this module provide appropriate tools for analyzing such data in the presence of correlation. Transition models offer a different perspective, focusing on how current values depend on past values, which is natural for many longitudinal processes.

## Learning Objectives

By the end of this module, students should be able to:

- Recognize count data and understand when Poisson and negative binomial models are appropriate
- Extend GEE methodology to count outcomes
- Fit and interpret Poisson and negative binomial GLMMs
- Understand overdispersion and how to detect and address it
- Distinguish between Poisson and negative binomial models
- Understand transition (Markov) models for longitudinal data
- Fit and interpret first-order Markov models
- Apply transition models to model change and incidence
- Choose among GEE, GLMM, and transition model approaches for longitudinal count or discrete data
- Implement all approaches in Stata and R
- Interpret and communicate results appropriately for count outcomes

## Topics Covered

### 1. Count Data in Medical Research

#### Characteristics of Count Data
- Non-negative integers
- Often skewed distributions
- Examples: number of seizures, hospital admissions, symptoms, lesions
- Rare events vs. common events

#### Why Standard Methods Fail
- Violation of normality assumptions
- Heteroscedasticity (variance changes with mean)
- Floor effect at zero
- Need for appropriate distributional models

### 2. Poisson Regression for Correlated Count Data

#### Review of Standard Poisson Regression
- The Poisson distribution
- Log link function
- Interpretation of regression coefficients (log rate ratios)
- Rate ratios and incidence rate ratios
- Exposure time and offsets

#### Extending to Correlated Count Data via GEE
- Marginal Poisson regression using GEE
- Working correlation structures for count data
- Population-average rate ratios
- Robust standard errors
- Overdispersion in GEE framework

#### Poisson GLMM (Random Effects Poisson Regression)
- Subject-specific Poisson models
- Random intercepts and random slopes
- Subject-specific rate ratios
- Estimation via numerical integration
- Interpretation of random effects variance

#### Population-Average vs. Subject-Specific for Count Data
- Similar issues as with binary data (Module 5)
- Attenuation of population-average effects
- Choosing interpretation based on research questions

### 3. Negative Binomial Models

#### Understanding Overdispersion
- Definition: variance exceeds mean
- Causes: unobserved heterogeneity, clustering, measurement error
- Detecting overdispersion
- Consequences of ignoring overdispersion

#### The Negative Binomial Distribution
- Gamma-Poisson mixture
- Additional dispersion parameter
- Reduces to Poisson when dispersion parameter = 0
- Variance-mean relationship

#### Negative Binomial Models for Correlated Data
- GEE with negative binomial family
- Negative binomial GLMMs
- Interpreting the dispersion parameter
- Model comparison: Poisson vs. negative binomial

#### Practical Implementation
- Testing for overdispersion
- Fitting negative binomial models
- Comparing model fits
- Software considerations

### 4. Transition (Markov) Models for Longitudinal Data

#### Introduction to Transition Models
- Alternative framework for longitudinal data
- Focus on how responses change over time
- Dependence on previous observations
- Autoregressive structure

#### First-Order Markov Models
- Current response depends on previous response
- Transition probabilities
- For continuous outcomes: AR(1) structure
- For discrete outcomes: transition probability matrices

#### Transition Models for Binary Outcomes
- State transition probabilities
- Modeling factors affecting transitions
- Logistic regression with lagged outcome
- Applications to disease progression

#### Transition Models for Count Outcomes
- Poisson or negative binomial with lagged count
- Modeling incidence vs. prevalence
- Changes from baseline
- Event occurrence modeling

### 5. Applications: Modeling Change and Incidence

#### Modeling Change Over Time
- Absolute change vs. relative change
- Change from baseline models
- Growth and decay processes
- Intervention effects on rate of change

#### Modeling Incidence
- New event occurrence
- Recurrent events
- Time-to-event considerations
- Competing risks

#### Choosing Among Modeling Approaches
- **GEE:** Population-average effects, robust inference
- **GLMM:** Subject-specific effects, random effects of interest, MAR missing data
- **Transition models:** Focus on temporal dynamics, dependence on past
- Hybrid approaches combining features

### 6. Advanced Topics and Practical Considerations

#### Zero-Inflated Models
- Excess zeros in count data
- Zero-inflated Poisson (ZIP)
- Zero-inflated negative binomial (ZINB)
- Hurdle models
- When to use zero-inflation models

#### Model Diagnostics for Count Data
- Residual analysis
- Checking dispersion assumptions
- Goodness of fit
- Influence diagnostics
- Checking Markov assumption in transition models

#### Software Implementation and Comparison
- Stata: `xtgee`, `mepoisson`, `menbreg`, `xtpoisson`
- R: `geepack`, `lme4::glmer()`, `glmmTMB`, `MASS::glm.nb()`
- Computational considerations
- Convergence issues

## Key Concepts

- **Count Data:** Outcomes that are non-negative integers
- **Poisson Distribution:** Probability distribution for count data with mean = variance
- **Negative Binomial Distribution:** Extension of Poisson allowing overdispersion
- **Overdispersion:** Variance exceeds the mean (more variability than Poisson predicts)
- **Rate Ratio:** Ratio of incidence rates, the measure of association in Poisson regression
- **Dispersion Parameter:** Parameter controlling the amount of overdispersion in negative binomial models
- **Transition Model:** Model where current response depends on previous response(s)
- **Markov Model:** A model where current state depends only on the most recent past state (first-order)
- **Transition Probability:** Probability of moving from one state to another
- **Zero-Inflation:** Excess zeros beyond what the count distribution predicts
- **Offset:** Known quantity (often log of exposure time) included in the model to account for varying exposure

## Mathematical Frameworks

### Poisson Regression
$$\log(E[Y_{ij}|X_{ij}]) = \beta_0 + \beta_1 X_{ij} + \log(t_{ij})$$

where $t_{ij}$ is exposure time (offset).

### Negative Binomial Regression
$$E[Y_{ij}|X_{ij}] = \mu_{ij} = \exp(\beta_0 + \beta_1 X_{ij})$$
$$\text{Var}(Y_{ij}|X_{ij}) = \mu_{ij} + \alpha \mu_{ij}^2$$

where $\alpha$ is the dispersion parameter.

### First-Order Markov Model (Binary)
$$\text{logit}(P(Y_{ij}=1|Y_{i,j-1}, X_{ij})) = \beta_0 + \beta_1 X_{ij} + \gamma Y_{i,j-1}$$

where $\gamma$ represents the effect of the previous state.

## Practical Exercises

This module includes practical exercises using both **Stata** and **R** to:
- Fit Poisson regression models using GEE and GLMM
- Detect and test for overdispersion
- Fit negative binomial models for overdispersed count data
- Compare Poisson and negative binomial models
- Compare population-average (GEE) and subject-specific (GLMM) interpretations
- Fit transition models for binary and count outcomes
- Interpret transition probabilities and autoregressive parameters
- Handle zero-inflated count data
- Choose appropriate models based on data characteristics
- Perform comprehensive model diagnostics

## Real-World Examples

Case studies included:
- Seizure counts in epilepsy trials
- Number of hospital admissions over time
- Disease recurrence in cancer studies
- Symptom counts in psychiatric studies
- Number of lesions in dermatology
- Infection counts in longitudinal studies
- Binary disease status with transitions between states

## Software Implementation

### Stata
- **Poisson GEE:** `xtgee` with `family(poisson) link(log)`
- **Poisson GLMM:** `mepoisson` or `meglm` with `family(poisson)`
- **Negative binomial GLMM:** `menbreg`
- **Transition models:** Standard regression with lagged variables
- Setting exposure offsets
- Specifying integration points

### R
- **Poisson GEE:** `geepack::geeglm()` with `family=poisson(link="log")`
- **Poisson GLMM:** `lme4::glmer()` with `family=poisson(link="log")`
- **Negative binomial GLMM:** `lme4::glmer.nb()` or `glmmTMB::glmmTMB()`
- **Standard negative binomial:** `MASS::glm.nb()`
- **Zero-inflated models:** `pscl` package or `glmmTMB`
- Creating lagged variables for transition models
- Offset specification: `offset(log(time))`

## Assessment

Selected exercises from this module will contribute to the **Module 4-6 Assignment** (30%), due **June 10**.

## Recommended Readings

Key sections from:
- **Fitzmaurice, Laird, & Ware.** *Applied Longitudinal Analysis* (2004)
  - Chapters on models for count data
  - Chapters on transition models
- **Diggle et al.** *Analysis of Longitudinal Data* (2002)
  - Chapters on generalized linear models for longitudinal data
  - Chapters on Markov models

Additional readings:
- Papers on overdispersion in count data
- Applications of negative binomial models in medical research
- Transition models for disease progression
- Zero-inflated count models

## Prerequisites

Students should have completed:
- **Modules 1-5** (all previous modules)
- Regression Modelling for Biostatistics 1 (RM1)

Essential prerequisite knowledge:
- Poisson regression for count data
- GEE methodology (Modules 3, 5)
- GLMM framework (Modules 4, 5)
- Understanding of population-average vs. subject-specific concepts
- Logistic regression (for transition models with binary outcomes)

## Course Synthesis

Module 6 completes the course by:
1. Extending all major frameworks (GEE, GLMM) to count data
2. Introducing a complementary approach (transition models) for temporal dynamics
3. Providing tools for handling overdispersion and zero-inflation
4. Reinforcing the fundamental distinctions between marginal and conditional models

## Summary Table: Choosing Among Approaches

| Data Type | Research Question | Missing Data | Recommended Approach |
|-----------|------------------|--------------|---------------------|
| Count | Population average effects | MCAR | GEE (Poisson or NB) |
| Count | Individual predictions | MAR | GLMM (Poisson or NB) |
| Count | Temporal dynamics | Any | Transition model |
| Binary/Count | Change process | Any | Transition model |
| Overdispersed count | Population average | MCAR | GEE with NB |
| Overdispersed count | Subject-specific | MAR | NB GLMM |

## Important Considerations

### Choosing Between Poisson and Negative Binomial
- Always check for overdispersion
- If present, negative binomial is preferred
- Test using likelihood ratio test (in GLMM) or examine dispersion statistics (in GEE)

### When to Use Transition Models
- When temporal dynamics are of primary interest
- When dependence on past values is scientifically meaningful
- For modeling disease progression or state changes
- When other methods fail to capture temporal patterns adequately

### Challenges with Count Data
- Convergence can be difficult with GLMMs, especially negative binomial
- Zero-inflation requires careful consideration
- Choice of offset (exposure time) affects interpretation
- Small counts can lead to unstable estimates

## Final Notes on Course Integration

This module brings together all the major themes of the course:

1. **Correlation structures:** From simple paired data (Module 1) to complex longitudinal patterns (Modules 2-6)

2. **Two major paradigms:**
   - **Marginal models (GEE):** Focus on population-average effects
   - **Conditional models (mixed models):** Focus on subject-specific effects
   
3. **Multiple data types:**
   - Continuous (Modules 3-4)
   - Binary (Module 5)
   - Count (Module 6)

4. **Alternative frameworks:**
   - Cross-sectional view (GEE, GLMM)
   - Temporal dynamics view (transition models)

5. **Practical considerations:**
   - Missing data mechanisms
   - Computational challenges
   - Model selection and diagnostics
   - Clear communication of results

---

*This final module completes your toolkit for analyzing correlated and longitudinal data. You now have methods for continuous, binary, and count outcomes, using both marginal and conditional approaches, plus transition models for temporal dynamics. The key is to match the method to your research question, data structure, and missing data pattern. Remember that clear interpretation and communication are just as important as technical correctness.*

## Looking Forward

After completing this course, you should be well-equipped to:
- Recognize correlated data structures in research settings
- Choose appropriate analytical methods
- Implement analyses using Stata or R
- Interpret results correctly (population-average vs. subject-specific)
- Communicate findings to medical investigators
- Read and critically evaluate published analyses of longitudinal and correlated data
- Serve as a statistical collaborator on projects involving these data types

Congratulations on completing Longitudinal and Correlated Data!
