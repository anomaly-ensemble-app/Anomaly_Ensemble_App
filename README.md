# Anomaly_Ensemble_App

![PyPI](https://img.shields.io/pypi/v/anomaly-ensemble-app?label=pypi%20package) ![CI](https://github.com/devosmitachatterjee2018/Anomaly_Ensemble_App/actions/workflows/ci.yml/badge.svg)

## Table of contents ##
- [A statement of need](#A-statement-of-need)
  - [Overview of Anomaly_Ensemble_App](#Overview_of_Anomaly_Ensemble_App)
  - [Features](#Features)
  - [Target audience](#Target-audience)
- [Functionality](#Functionality)
- [Installation instructions](#Installation-instructions)
  - [Prerequisites](#Prerequisites)
  - [App installation](#App-installation)
- [Demo](#Demo)
  - [Data](#Data)
  - [Code](#Code)
- [Community guidelines](#Community-guidelines)
  - [Contribute to the software](#Contribute-to-the-software)
  - [Report issues or problems with the software](#Report-issues-or-problems-with-the-software)
  - [Seek support](#Seek-support)
- [Software license](#Software-license)

## A statement of need ##

### Overview of Anomaly_Ensemble_App ###
Anomaly_Ensemble_App is an anomaly detection python library that is based on the ensemble learning algorithm to derive better predictions. It combines multiple independent anomaly detection models such as Isolation Forest, DBSCAN, ThymeBoost, One-Class Support Vector Machine, Local Outlier Factor and TADGAN. Then, it returns the output according as the average prediction of the individual models is above a certain threshold. This package is specially designed for univariate time series.

**Process Flow Diagram:**

<img src="Anomaly_Ensemble_App.png" width="800" height="500">

### Features ###
1. Handles time series data.
2. Deals with trends and seasonality.
3. Provides options to choose anomaly detection models for ensemble learning.
4. Suggests hyperparameters for each anomaly detection model.
4. Provides execution time for each anomaly detection model.
6. Provides more accurate anomaly predictions. 

**Choice of hyperparameters:**
1. Isolation Forest
    - contamination = Percentage of expected outliers.

2. DBSCAN 
    - min_samples: For n-dimensional data, min_samples = 2\*n, where n = the dimensionlity of the data.
    - eps: eps = the point of maximum curvature of the k-NN distance graph.
  
3. ThymeBoost
    - seasonal_period: seasonal_period = first expected seasonal period at the maximum amplitude, computed using Fast Fourier Transform.

4. One-Class Support Vector Machine
    - kernel: Best optimal kernal using Optuna hyperparameter optimization framework.

5. Local Outlier Factor
    - alg: Best optimal algorithm using Optuna hyperparameter optimization framework.

6. TADGAN
    - epochs: Best optimal epoch using Orion hyperparameter optimization framework.

## Functionality ##
There are several modules in the package. Each module has several functions.

1. **Module: anomaly_libs module**

2. **Module: anomaly_data_preprocessing module**
  - min\_samples = find\_min\_samples(df)
     - Definition: This function is used to find an hyperparameter for DBSCAN.
       -- Find min\_samples: min\_samples is chosen as 2\*n, where n = the dimensionlity of the data.
     - Input Parameters: df is the dataset.
     - Output: Returns min\_samples as 2\*n, where n = the dimensionlity of the data.

  * eps = find\_eps(df)
     - Definition: This function is used to find an hyperparameter for DBSCAN.
       -- Find eps: eps is chosen as the point of maximum curvature of the k-NN distance graph.
     - Input Parameters: df is the dataset.
     - Output: Returns eps.

  3. p = find\_seasonal\_period(df)
     - Definition: This function is used to find an hyperparameter for Thymeboost.
       -- Find p: seasonal\_period is chosen as the first expected seasonal period at the maximum amplitude, computed using Fast Fourier Transform.
     - Input Parameters: df is the dataset.
     - Output: Returns seasonal\_period.

  4. output = detrend(df, id\_column, time\_column, time\_format):
     - Definition: This function is used to identify trend and then, detrend a time series.
       -- Identify trend: Augmented Dickey Fuller Test (ADF test) is used to capture trend of the time series.
       -- Detrend: 'detrend' function is used from the 'scipy' module for detrending the time series.
     - Input Parameters: 
       -- df is the dataset.
       -- id\_column is the column over which the function will iterate.
       -- time\_column is the datetime column.
       -- time\_format is the datetime format of time\_column.
     - Output: Returns detrended time series.

  5.  output = deseasonalise(df, id_column, time_column, time_format)
     - Definition: This function is used to determine seasonality and then, deseasonlise a time series.
       -- Determine seasonality: Autocorrelation function is used to check seasonality.
       -- Deseasonalise: 'seasonal_decompose' function is used from the 'statsmodel' module for deseasonalising the time series.
     - Input Parameters: 
       -- df is the dataset.
       -- id\_column is the column over which the function will iterate.
       -- time\_column is the datetime column.
       -- time\_format is the datetime format of time\_column.
     - Output: Returns deseasonalised time series.

  6. (best_nu, best_kernel) = parameters_oc_svm(X, y, trials=10)
     - Definition: This function is used to parameters for One Class SVM.
       -- Best optimal kernal using Optuna hyperparameter optimization framework
     - Input Parameters: 
       -- df is the dataset.
       -- id\_column is the column over which the function will iterate.
       -- time\_column is the datetime column.
       -- time\_format is the datetime format of time\_column.
     - Output: Returns best_nu and best_kernel.

3. **Module: anomaly_models module**
  1. min\_samples = find\_min\_samples(df)
     - Definition: This function is used to find an hyperparameter for DBSCAN.
       -- Find min\_samples: min\_samples is chosen as 2\*n, where n = the dimensionlity of the data.
     - Input Parameters: df is the dataset.
     - Output: Returns min\_samples as 2\*n, where n = the dimensionlity of the data.


**Not implemented yet:**
1. 95% confidence interval (+-1.96/sqrt(n))

### Target audience ###
Anomaly_Ensemble_App should be of interest to readers who are involved in outlier detection for time series data.

## Installation instructions ##

### Prerequisites ###
Anomaly_Ensemble_App has been developed and tested in Python Version: v3.7 and requires some libraries.

```python3 -m pip install -r "topath\requirements.txt"```

### Application installation ###
```python3 -m pip install Anomaly_Ensemble_App```

## Demo ##

### Data ###
Use exemplary datasets 

### Code ###

```from anomaly_ensemble_app.anomaly_main import *```

## Community guidelines ##

### Contribute to the software ###
To contribute fixes, feature modifications or enhancements, a pull request can be created in the [Pull requests](https://github.com/devosmitachatterjee2018/Anomaly_Ensemble_App/pulls) tab of the project GitHub repository. When contributing to the software, the folowing should be included.
1. Description of the change;

2. Check that all tests pass;

3. Include new tests to report the change.

### Report issues or problems with the software ###
Any feature request or issue can be submitted to the the [Issues](https://github.com/devosmitachatterjee2018/Anomaly_Ensemble_App/issues) tab of the project GitHub repository. When reporting issues with the software, the folowing should be included.
1. Description of the problem;

2. Error message;

3. Python version and Operating System.

### Seek support ###
If any support needed, the authors can be contacted by e-mail @volvo.com. 

## Software license ##
Anomaly_Ensemble_App is released under the MIT License.

