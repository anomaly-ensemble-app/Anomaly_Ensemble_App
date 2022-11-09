# Anomaly_Ensemble_App v0.0.1

![PyPI](https://img.shields.io/pypi/v/anomaly-ensemble-app?label=pypi%20package) ![CI](https://github.com/devosmitachatterjee2018/AnomalyDetectionApp/actions/workflows/ci.yml/badge.svg)

## Table of contents ##
- [A statement of need](#A-statement-of-need)
  - [Overview of Anomaly_Ensemble_App](#Overview_of_Anomaly_Ensemble_App)
  - [Features](#Features)
  - [Target audience](#Target-audience)
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
Anomaly_Ensemble_App is an anomaly detection python library that is based on the ensemble learning algorithm to derive better predictions. It combines the predictions of multiple independent anomaly detection models such as Isolation Forest, DBSCAN, ThymeBoost, One-Class Support Vector Machine, Local Outlier Factor and TADGAN. Then, it returns the output according as the average prediction of the individual models is above a certain threshold.

**Process Flow Diagram:**

<img src="AnamalyDetectionApp.png" width="800" height="500">

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
    - alg: Best optimal kernal using Optuna hyperparameter optimization framework.

6. TADGAN
    - epochs: Best optimal epoch using Orion hyperparameter optimization framework.

### Target audience ###
AnomalyDetectionApp should be of interest to readers who are involved in outlier detection for time series data.

## Installation instructions ##

### Prerequisites ###
AnomalyDetectionApp has been developed and tested in Python Version: v3.7 and requires some libraries.

```python3 -m pip install -r "topath\requirements.txt"```

### Application installation ###
```python3 -m pip install Anomaly_Ensemble_App```

## Demo ##

### Data ###
Use exemplary datasets 

### Code ###

```from Anomaly_Ensemble_App.anomaly_main import *```

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

