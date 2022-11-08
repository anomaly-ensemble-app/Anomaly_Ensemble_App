# AnomalyDetectionApp v0.1

![PyPI](https://img.shields.io/pypi/v/anomaly-devosmita?label=pypi%20package)

## Table of contents ##
- [A statement of need](#A-statement-of-need)
  - [Overview of AnomalyDetectionApp](#Overview_of_AnomalyDetectionApp)
  - [Features](#Features)
  - [Target audience](#Target-audience)
- [Installation instructions](#Installation-instructions)
  - [Prerequisites](#Prerequisites)
  - [App installation](#App-installation)
- [Demo](#Demo)
  - [Basic example](#Basic-example)
- [Community guidelines](#Community-guidelines)
  - [Contribute to the software](#Contribute-to-the-software)
  - [Report issues or problems with the software](#Report-issues-or-problems-with-the-software)
  - [Seek support](#Seek-support)
- [Tests](#Tests)
- [Software license](#Software-license)

## A statement of need ##

### Overview of AnomalyDetectionApp ###
AnomalyDetectionApp is an anomaly detection python library that is based on the ensemble learning algorithm to derive better predictions. It combines the predictions of multiple independent anomaly detection models such as Isolation Forest, DBSCAN, ThymeBoost, One-Class Support Vector Machine, Local Outlier Factor and TADGAN. Then, it returns the output according as the average prediction of the individual models is above a certain threshold.

Process Flow Diagram:

### Features ###

1. Provides more accurate anomaly predictions.
2. Suggests hyperparameters for each anomaly detection model.

### Target audience ###

AnomalyDetectionApp should be of interest to readers, mainly within the area of data science.

## Installation instructions ##

### Prerequisites ###
AnomalyDetectionApp has been developed and tested in Python Version: v3.7 and requires the following libraries.
1. ;

### Application installation ###
```python3 -m pip install anomaly_devosmita```

## Demo ##
To access the the exemplary dataset 
```from anomaly_devosmita import example```

### Basic example ###

## Community guidelines ##

### Contribute to the software ###
To contribute fixes, feature modifications or enhancements, a pull request can be created in the [Pull requests](https://github.com/devosmitachatterjee2018/Anomaly/pulls) tab of the project GitHub repository. When contributing to the software, the folowing should be included.
1. Description of the change;

2. Check that all tests pass;

3. Include new tests to report the change.

### Report issues or problems with the software ###
Any feature request or issue can be submitted to the the [Issues](https://github.com/devosmitachatterjee2018/Anomaly/issues) tab of the project GitHub repository. When reporting issues with the software, the folowing should be included.
1. Description of the problem;

2. Error message;

3. Python version and Operating System.

### Seek support ###
If any support needed, the authors can be contacted by e-mail <@gmail.com>. 

## Tests ##

## Software license ##
AnomalyDetectionApp is released under the MIT License.

