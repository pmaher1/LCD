# Module 1: Introduction to Correlated Data

**Duration:** Weeks 1-2 (March 3 - March 17)

## Overview

This module introduces the fundamental concepts of correlated data structures, starting with the simplest case of paired data and extending to simple clustered data. It establishes the foundation for understanding why standard statistical methods are inadequate for correlated data and introduces the basic modeling approaches to handle correlation.

## Learning Objectives

By the end of this module, students should be able to:

- Understand paired data as the simplest form of correlated data structure
- Recognize the limitations of standard statistical methods when applied to correlated data
- Understand the advantage of modeling approaches, particularly with missing data
- Apply simple random effects models to paired and clustered data
- Extend concepts from paired data to exchangeable clustered data with varying cluster sizes
- Understand the distinction between within-subject and between-subject information
- Be introduced to the concept of between-cluster effects
- Gain initial exposure to Generalised Estimating Equations (GEE)

## Topics Covered

### 1. Paired Data: The Simplest Correlated Data Structure
- Definition and examples of paired data
- Paired t-tests and their limitations
- Correlation within pairs
- Examples from medical research (e.g., measurements on left and right eyes, before-and-after measurements)

### 2. Modeling Approaches and Their Advantages
- Why model correlated data explicitly?
- Handling missing data in paired structures
- Utilizing both within-subject and between-subject information
- When one observation in a pair is missing

### 3. Simple Random Effects Models
- Introduction to random effects
- The concept of subject-specific effects
- Variance components: within-subject and between-subject variability
- Basic model specification for paired data

### 4. Extension to Exchangeable Clustered Data
- Moving from pairs to clusters
- Clusters with varying numbers of individuals
- Examples: patients within hospitals, students within schools
- Exchangeable correlation structure
- Intraclass correlation coefficient (ICC)

### 5. Between-Cluster Effects
- Understanding cluster-level covariates
- Ecological vs. individual-level effects
- Interpretation of between-cluster effects

### 6. Introduction to Generalised Estimating Equations (GEE)
- Why do we need GEE?
- Basic concept of estimating equations
- Working correlation structures
- Population-average vs. subject-specific interpretations

## Key Concepts

- **Paired Data:** Two observations on the same subject or matched observations on two related subjects
- **Correlation:** The statistical dependence between observations within the same cluster or subject
- **Random Effects:** Subject-specific or cluster-specific deviations from the population mean
- **Exchangeability:** The assumption that correlations between any two observations within a cluster are the same
- **Intraclass Correlation Coefficient (ICC):** A measure of how much of the total variance is due to differences between clusters
- **GEE:** A method for estimating population-average effects while accounting for correlation

## Practical Exercises

This module includes practical exercises using both **Stata** and **R** to:
- Analyze paired data using different approaches
- Fit simple random effects models
- Compare results from standard methods vs. methods accounting for correlation
- Calculate and interpret the ICC
- Explore the impact of missing data on different analysis approaches

## Software Skills Developed

- Fitting paired t-tests
- Implementing simple random effects models
- Basic GEE model fitting
- Visualizing correlated data structures
- Calculating correlation measures

## Assessment

Selected exercises from this module will contribute to the **Module 1-2 Short Assessment** (20%), due **March 31**.

## Recommended Readings

Key sections from:
- Fitzmaurice, Laird, & Ware. *Applied Longitudinal Analysis* (2004) - Chapters on basic concepts
- Diggle et al. *Analysis of Longitudinal Data* (2002) - Introduction chapters

Additional journal articles and case studies will be provided in the course materials.

## Prerequisites

Students should be comfortable with:
- Basic statistical inference (PSI)
- Simple linear regression (RM1)
- Variance and covariance concepts (MFB)
- Correlation coefficients

## Connection to Future Modules

Module 1 establishes the foundational concepts that will be expanded throughout the course:
- **Module 2** will explore more complex longitudinal and clustered data structures
- **Module 3** will develop GEE methods more fully for continuous outcomes
- **Module 4** will expand on random effects models with sophisticated estimation methods
- **Modules 5-6** will extend these concepts to discrete and count outcomes

---

*This module introduces the core problem of correlated data and sets the stage for understanding why specialized methods are necessary. Take time to understand the fundamental concepts of correlation and random effects, as they form the basis for all subsequent modules.*
