# Longitudinal and Correlated Data (LCD)

**Semester 1, 2025**  
**Biostatistics Collaboration of Australia (BCA)**

## Course Overview

This repository contains materials for the **Longitudinal and Correlated Data** course, which covers statistical models for longitudinal and correlated data in medical research. The course develops the concept of hierarchical data structures together with appropriate statistical methods to handle the correlation inherent in these data types.

### Coordinators

- **Lyle C. Gurrin** (University of Melbourne)
- **Andrew Forbes** (Monash University)
- **Jessica Kasza** (Monash University)
- **John Carlin** (University of Melbourne & Murdoch Children's Research Institute)
- **John Holmes** (Canterbury University, New Zealand)
- **Koen Simons** (University of Gothenburg, Sweden)

## Background

Longitudinal and correlated data arise in many settings in health and medical research. Common examples include:
- Studies involving repeated measurements of individuals over time
- Clinical trials and cohort studies
- Cluster-randomised trials where participants are clustered within natural units (schools, medical practices, etc.)

The common characteristic of these data structures is **correlated measurements** either within an individual or within a cluster of individuals. Standard statistical methods assume independent observations and therefore do not accommodate this correlation, requiring more sophisticated approaches.

## Learning Outcomes

At the completion of this unit, students should be able to:

1. **Recognise** the existence of correlated or hierarchical data structures, and describe the limitations of standard methods in these settings
2. **Develop** and analytically describe appropriate models for longitudinal and correlated data based on subject matter considerations
3. **Apply** statistical software packages (Stata and R) to fit models and perform computations for longitudinal data analyses, and correctly interpret results
4. **Communicate** the results of statistical analyses of longitudinal data in language suitable for medical investigators or publication in biomedical/epidemiological journals

## Prerequisites

- Epidemiology (EPI)
- Mathematical Foundations for Biostatistics (MFB)
- Principles of Statistical Inference (PSI)
- Regression Modelling for Biostatistics 1 (RM1)

## Course Structure

The course is divided into **6 modules**, each covering approximately 2-3 weeks of study:

### [Module 1: Introduction to Correlated Data](Module1/)
Introduction to correlated data using paired data and simple clustered data

### [Module 2: Overview of Correlated and Longitudinal Data Structures](Module2/)
Different correlated and longitudinal data structures and related research questions

### [Module 3: GEE Methods for Continuous Outcomes](Module3/)
Methods for continuous outcome measures based on generalised estimating equations (GEE)

### [Module 4: Normal Mixed Models](Module4/)
Methods for continuous outcome measures based on normal mixed models with likelihood-based estimation

### [Module 5: Methods for Discrete Data](Module5/)
GEE and generalized linear mixed models (GLMM) for discrete outcomes

### [Module 6: Count Data and Transition Models](Module6/)
Methods for count data and transition models

## Workload

Expected workload: **10-12 hours per week** on average, consisting of:
- Guided readings
- Discussion posts
- Independent study
- Completion of assessment tasks

## Software Requirements

Students will need access to and working familiarity with either:
- **Stata** (version 13 or higher, current version 18.0)
- **R** (current version 4.4.2 or later)

All methods in this unit can be conducted using Stata alone or R alone, though the set of examples with Stata code is somewhat more complete than those with R code.

## Assessment

- **Module 1-2 short assessment** (20%) - Due March 31
- **Module 1-3 assignment** (30%) - Due April 28
- **Module 4-5 short assessment** (20%) - Due May 19
- **Module 4-6 assignment** (30%) - Due June 10

## Recommended Texts

Primary text:
- **Fitzmaurice G, Laird N, Ware J.** *Applied Longitudinal Analysis*, John Wiley and Sons, 2004

Additional references:
- Diggle PJ, Heagerty P, Liang K-Y, Zeger SL. *Analysis of Longitudinal Data*, 2nd Edition, Oxford University Press, 2002
- Singer JD, Willett JB. *Applied Longitudinal Data Analysis: Modeling Change and Event Occurrence*, Oxford University Press, 2003
- Verbeke G, Molenberghs G. *Linear Mixed Models for Longitudinal Data*, Springer, 2000
- Brown H, Prescott R. *Applied Mixed Models in Medicine*, 3rd Edition, Wiley, 2015

## Repository Structure

```
LCD/
├── README.md                    # This file
├── Reading/                     # Course reading materials
│   ├── Annotated/              # Annotated readings
│   └── Clean/                  # Clean study guide and materials
├── Module1/                     # Paired data and simple clustered data
├── Module2/                     # Correlated and longitudinal data structures
├── Module3/                     # GEE methods for continuous outcomes
├── Module4/                     # Normal mixed models
├── Module5/                     # Methods for discrete data
└── Module6/                     # Count data and transition models
```

## Contact

For questions about administrative aspects or course content, please contact the unit coordinator with "LCD:" in the subject line.

For general BCA queries, contact:
- **Jacqueline (Jaqē) Vaughan** or **Jeremy Platt**
- BCA Coordinating Office: 02 9562 5076/54
- Email: bca@sydney.edu.au

---

*Copyright © Department of Epidemiology and Preventive Medicine, Monash University, and Centre for Epidemiology and Biostatistics, School of Population and Global Health, University of Melbourne*
