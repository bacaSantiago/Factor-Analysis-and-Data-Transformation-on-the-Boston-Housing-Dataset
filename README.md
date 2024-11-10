# Factor Analysis and Data Transformation on the Boston Housing Dataset

---

## Overview

This project focuses on conducting a multivariate analysis of the Boston Housing dataset, specifically applying data transformations and factor analysis techniques. The analysis uses advanced statistical methods to uncover latent structures within the data and explores relationships between variables through Maximum Likelihood Estimation (MLE), Principal Factor Analysis, and Varimax rotation. The study aims to enhance interpretability and facilitate deeper insights into the socioeconomic and environmental characteristics of Boston neighborhoods.

---

## Dataset

The Boston Housing dataset includes 14 variables that describe various physical and socioeconomic characteristics of neighborhoods in Boston. These variables range from crime rates and pollution levels to median home values and educational aspects.

### Variables

- **crim**: Per capita crime rate.
- **zn**: Proportion of residential land zoned for lots over 25,000 square feet.
- **indus**: Proportion of non-retail business acres per town.
- **chas**: Charles River dummy variable (1 if tract bounds the river; 0 otherwise).
- **nox**: Nitric oxides concentration (parts per 10 million).
- **rm**: Average number of rooms per dwelling.
- **age**: Proportion of owner-occupied units built before 1940.
- **dis**: Weighted distances to five Boston employment centers.
- **rad**: Index of accessibility to radial highways.
- **tax**: Property tax rate per $10,000.
- **ptratio**: Pupil-teacher ratio by town.
- **b**: Proportion of Black residents by town.
- **lstat**: Percentage of population with low socioeconomic status.
- **medv**: Median value of owner-occupied homes (in thousands of dollars).

---

## Data Transformation

To address skewness and distribution irregularities, the dataset variables undergo a series of transformations. These transformations aim to normalize the data, improve symmetry, and prepare the data for factor analysis by stabilizing variances.

### Transformation Details

- **Logarithmic Transformation**: Applied to variables with significant skewness, such as `crim`, `indus`, `nox`, `rm`, `dis`, `rad`, `tax`, and `medv`.
- **Scaling**: Variables like `zn` and `b` are scaled by a constant to adjust their range without changing distribution shape.
- **Exponential Transformation**: Used on `ptratio` to compress its range.
- **Power Transformation**: Applied to `age` to alter its distribution and improve symmetry.
- **Square Root Transformation**: Used on `lstat` to reduce skewness.

Visualizations (boxplots and histograms) are included in the project to compare original and transformed variables, highlighting changes in scale and symmetry post-transformation.

---

## Factor Analysis

Factor analysis is employed to reduce dimensionality and identify latent structures within the dataset. Three approaches are implemented to explore relationships between observed variables and underlying factors.

### Methodology

1. **Maximum Likelihood Estimation (MLE)**: This approach estimates factor loadings and specific variances by maximizing the likelihood of the observed data under a factor model. It assumes that the observed data follows a multivariate normal distribution.

2. **Principal Factor Analysis**: Using the correlation matrix, this method computes communalities for each variable, adjusts the matrix, and applies spectral decomposition to derive factor loadings.

3. **Varimax Rotation**: An orthogonal rotation technique applied to enhance interpretability, making each factor load more distinctly on a subset of variables. Varimax rotation is particularly useful for clarifying the factor structure.

### Factor Analysis Model

The model is represented by the equation:

   \( X = QF + U + \mu \)

Where:

- \( X \): Observed variables.
- \( Q \): Factor loadings.
- \( F \): Latent factors.
- \( U \): Unique factors (specific to each observed variable).
- \( \mu \): Mean vector of \( X \).

Key assumptions include:

1. Independence and zero mean of factors \( F \).
2. Independence of unique factors \( U \) from each other and from \( F \), with diagonal covariance matrix \( \Xi \).

### Rotations and Interpretations

The Varimax rotation maximizes the variance of squared loadings within each factor, improving interpretability by clarifying which variables are associated with each factor. After rotation, factors become more distinct, making it easier to understand underlying themes like urban density, housing quality, and socioeconomic disparity.

---

## Correlation Analysis

Pearson correlations between the original variables and factor scores are calculated for each method (MLE, Principal Factors, and MLE with Varimax). Heatmaps visualize these correlations, revealing patterns and underlying relationships.

### Insights from Correlation Analysis

- **Factor 1**: Generally associated with urban density indicators like `crim`, `indus`, `nox`, and `tax`, suggesting a socioeconomic dimension.
- **Factor 2**: Reflects housing quality aspects through correlations with `rm` and `medv`.
- **Factor 3**: Tends to represent accessibility and urban spread based on variables like `dis` and `rad`.

Each heatmap highlights how the different factor extraction methods alter the relationships, with Varimax rotation providing the most distinct and interpretable factors.

---

## Dependencies

- **Pandas**: For data manipulation.
- **NumPy**: For numerical operations, including data transformations.
- **Matplotlib** and **Seaborn**: For visualizing transformations and factor loadings.
- **FactorAnalyzer**: For performing factor analysis, enabling MLE, principal factor extraction, and Varimax rotation.

---

## Resources

- [FactorAnalyzer Documentation](https://factor-analyzer.readthedocs.io/en/latest/factor_analyzer.html)
- *Applied Multivariate Statistical Analysis* by Johnson & Wichern – For theoretical foundations of factor analysis and rotations.

---

## Applications

This project serves as a framework for understanding complex socioeconomic relationships within a dataset, providing a foundation for:

1. **Exploratory Data Analysis (EDA)** in socioeconomic and environmental studies.
2. **Dimensionality Reduction** in multivariate datasets.
3. **Feature Extraction** in predictive modeling, using derived factors as input features.
4. **Urban Planning and Policy-Making** insights by identifying core factors affecting urban environments.

---

This analysis successfully demonstrates the use of data transformations and factor analysis in handling multivariate data. By aligning the Boston Housing dataset with the assumptions of factor analysis, the project uncovers latent dimensions that explain the variation in socioeconomic and environmental characteristics across neighborhoods, providing a rich foundation for further analysis or predictive modeling.
