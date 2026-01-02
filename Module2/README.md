# Module 2: Overview of Different Correlated and Longitudinal Data Structures

**Duration:** Weeks 3-4 (March 17 - March 31)

## Overview

This module provides a comprehensive overview of different types of correlated and longitudinal data structures commonly encountered in health and medical research. It introduces the two major problem types (cluster-randomised trials and repeated-measures longitudinal studies) and develops simple approaches to analyzing these data structures, including graphical displays and summary measures.

## Learning Objectives

By the end of this module, students should be able to:

- Identify and distinguish between different types of correlated data structures
- Understand the specific research questions addressed by cluster-randomised trials
- Understand the specific research questions addressed by repeated-measures longitudinal studies
- Create appropriate graphical displays for longitudinal data (trajectory plots, correlation plots)
- Apply the summary measures approach to longitudinal data analysis
- Understand the design effect in cluster-randomised trials
- Apply simple approaches to analyzing cluster-randomised trials
- Recognize when more sophisticated methods are needed

## Topics Covered

### 1. Major Types of Correlated Data Structures

#### Cluster-Randomised Trials (CRTs)
- Definition and rationale for cluster randomization
- Examples: school-based interventions, community trials
- Units of randomization vs. units of analysis
- Why cluster randomization is sometimes necessary
- Ethical and practical considerations

#### Repeated-Measures Longitudinal Studies
- Definition of longitudinal data
- Types of longitudinal studies: cohort studies, clinical trials with follow-up
- Time as a key variable
- Growth curves and trajectories
- Attrition and dropout in longitudinal studies

### 2. Graphical Displays for Longitudinal Data

#### Trajectory Plots
- Individual trajectories over time
- Spaghetti plots for visualizing individual patterns
- Average trajectories by group
- Identifying outliers and unusual patterns

#### Pairwise Correlations
- Correlation matrices for repeated measures
- Visualizing correlation patterns
- Time-dependent correlation structures
- Identifying appropriate correlation models

### 3. Summary Measures Approach to Analysis

#### Concept of Summary Measures
- Reducing repeated measures to a single summary per individual
- Types of summary measures: slopes, areas under curves, maximum values, time to event

#### Advantages of Summary Measures
- Simplicity: uses standard statistical methods
- Robustness to missing data (in some cases)
- Clear interpretation

#### Limitations of Summary Measures
- Loss of information
- Difficulty handling irregular timing
- Cannot separate within-subject and between-subject effects
- Limited flexibility for complex patterns

#### Practical Implementation
- Choosing appropriate summary measures
- Examples from clinical trials
- Software implementation in Stata and R

### 4. Cluster-Randomised Trials: Design and Analysis

#### Design Effect
- Definition and calculation
- Relationship to intraclass correlation coefficient (ICC)
- Impact on sample size requirements
- How clustering inflates variance

#### Simple Approaches to Analysis
- Cluster-level analysis (treating clusters as units)
- Individual-level analysis ignoring clustering (why it's wrong)
- Adjusting standard errors for clustering
- Pros and cons of different approaches

#### Power and Sample Size Considerations
- Why more clusters are needed than individuals in parallel designs
- Trade-offs between number of clusters and cluster size
- Variance estimation

### 5. Research Questions in Different Study Types

#### Questions in CRTs
- Intervention effects at the cluster level
- Intervention effects at the individual level
- Understanding contamination and spillover effects

#### Questions in Longitudinal Studies
- How does the outcome change over time?
- Do groups differ in their trajectories?
- What factors predict individual differences in change?
- When does change occur (critical periods)?

## Key Concepts

- **Cluster-Randomised Trial (CRT):** An experimental design where groups (clusters) rather than individuals are randomized to interventions
- **Longitudinal Data:** Repeated measurements on the same individuals over time
- **Trajectory:** The path of change for an individual over time
- **Summary Measure:** A single value that summarizes an individual's repeated measurements
- **Design Effect:** The factor by which the sample size must be increased to account for clustering
- **Intraclass Correlation Coefficient (ICC):** The proportion of total variance attributable to between-cluster differences
- **Spaghetti Plot:** A graph showing individual trajectories as separate lines
- **Attrition:** Loss of participants over time in longitudinal studies

## Practical Exercises

This module includes practical exercises using both **Stata** and **R** to:
- Create trajectory plots and other visualizations for longitudinal data
- Calculate pairwise correlations between time points
- Implement summary measures approaches
- Calculate design effects for CRTs
- Compare naive vs. cluster-adjusted analyses
- Explore the impact of ICC on design effect

## Software Skills Developed

- Creating spaghetti plots and mean trajectory plots
- Calculating correlation matrices
- Computing summary measures (slopes, AUCs, etc.)
- Cluster-level aggregation
- Calculating design effects
- Adjusting standard errors for clustering

## Real-World Examples

Module materials include case studies such as:
- School-based nutrition interventions (CRT example)
- Growth studies in children (longitudinal example)
- Clinical trials with repeated outcome measurements
- Community-based health promotion programs

## Assessment

Selected exercises from this module will contribute to the **Module 1-2 Short Assessment** (20%), due **March 31**.

## Recommended Readings

Key sections from:
- Fitzmaurice, Laird, & Ware. *Applied Longitudinal Analysis* (2004) - Chapters on exploratory data analysis and summary measures
- Diggle et al. *Analysis of Longitudinal Data* (2002) - Chapters on exploring longitudinal data
- Selected journal articles on cluster-randomised trials

Additional readings on:
- Design and analysis of cluster-randomised trials
- Graphical methods for longitudinal data
- Summary measures in clinical trials

## Prerequisites

Students should have completed:
- **Module 1** (Introduction to Correlated Data)
- Regression Modelling for Biostatistics 1 (RM1)

Key concepts from Module 1 that will be built upon:
- Understanding of correlation within clusters
- Intraclass correlation coefficient
- Random effects concepts

## Connection to Future Modules

Module 2 sets up the specific problems that will be addressed with advanced methods:
- **Module 3** will develop GEE methods that can handle the full longitudinal data (not just summaries)
- **Module 4** will introduce mixed models that separate within- and between-subject effects
- **Module 5** will extend these methods to binary and other discrete outcomes
- **Module 6** will cover count outcomes and special models for transitions

## Important Notes

This module emphasizes the importance of:
1. **Understanding your data structure** before choosing analysis methods
2. **Exploratory analysis** through graphics to understand patterns and identify issues
3. **Recognizing limitations** of simple approaches (even when they're appealing)
4. **Considering the research question** when choosing between analysis approaches

The simple methods introduced here (especially summary measures) are legitimate approaches for certain problems, but this module also highlights when more sophisticated methods from later modules are necessary.

---

*This module is crucial for developing intuition about different correlated data structures. Spend time creating and interpreting graphs of your data - this will help you understand the correlation patterns and make better modeling choices in later modules.*
