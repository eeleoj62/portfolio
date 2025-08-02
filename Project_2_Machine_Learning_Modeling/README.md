# Detecting IoT Botnet Attacks N-BaIoT

This project uses machine learning models to detect botnet attacks on IoT devices using the N-BaIoT dataset.

## Repository Structure

Project_2_Machine_Learning_Modeling
-Data
-Images
-project_2_multiclass.ipynb
-project_2.ipynb
-README.md
-.gitignore

## Notebooks Overview
-project_2 trains a binary classifier to detect whether a network event is benign or an attack
-project_2_multiclass trains a multiclass model to identify specific botnet families and the types of attacks

## REquirements
Install dependencies with:
pip install -r requirements.txt

## How to run
-download dataset from https://archive.ics.uci.edu/dataset/442/detection+of+iot+botnet+attacks+n+baiot
-place files in data/ folder
-open notebooks inside jupyter or VS code
-run cells top to bottom

## Results
Final metrics for binary classification:

Precision	Recall	F1 Score	ROC AUC
Model				
Logistic Regression	0.999325	0.999325	0.999325	0.999861
Random Forest	0.999813	0.999812	0.999813	1.000000
XGBoost	0.999963	0.999962	0.999963	1.000000

Final confusion matrix for XGBoost model for binary classification:

XGBoost Confusion Matrix:
 [[59997     3]
 [    0 20000]]

Final metrics for multiclass:
	Precision	Recall	F1 Score	ROC AUC
Model				
XGBoost	0.997821	0.997773	0.997772	0.999787
Random Forest	0.997639	0.997591	0.997590	0.999785

Final confusion matrix for XGBoost for multiclass:

XGBoost Confusion Matrix:
 [[10000     0     0     0     0     0     0     0     0     0     0]
 [    0  9999     1     0     0     0     0     0     0     0     0]
 [    0     2  9998     0     0     0     0     0     0     0     0]
 [    0     0     1  9999     0     0     0     0     0     0     0]
 [    0     0     0     0  9763   236     0     0     0     1     0]
 [    1     0     0     0     2  9997     0     0     0     0     0]
 [    0     0     0     0     0     0  9999     0     0     0     1]
 [    0     0     0     0     0     0     0 10000     0     0     0]
 [    0     0     0     0     0     0     0     0 10000     0     0]
 [    0     0     0     0     0     0     0     0     0 10000     0]
 [    0     0     0     0     0     0     0     0     0     0 10000]]

## Notes
All notebooks are structured with Markdown cells and comments
Dataset too large to upload to GitHub — please download manually
Project inspired by real-world security concerns in IoT environments