# Mechanisms of Action Prediction | Kaggle Competition

This repository contains my code for [Mechanisms of Action Prediction Competition](https://www.kaggle.com/c/lish-moa) on Kaggle. I secured **73rd rank - Top 2%** in this competition.

## Content
- [Setup](#setup)
- [Multi Label Classification Problem](#multi-label-classification-problem)
- [Main Ideas](#main-ideas)
  - [Traditional Classification Models Don't Work Here](#traditional-classification-models-dont-work-here)
  - [Build Single Models](#build-single-models)
  - [Creating Scoring Scripts](#creating-scoring-scripts)
  - [Blending Models](#blending-models)
- [Final Submission](#final-submission)
- [Acknowledgement](#acknowledgement)

## Setup
I have used [Kaggle notebooks](https://www.kaggle.com/notebooks) only for this competition. To reproduce the code and results consider using the [Kaggle Docker Environment](https://github.com/Kaggle/docker-python) for the same. 

## Multi Label Classification Problem
- This competition was a Multi Label Classification Problem. To add it to the complexity of this category of problems:
  - There were 206 classes to predict (and 400+ more can be used for pretraining).
  - There were classes with less than 10 positive labels (highly imbalanced - x1000) and none of the Over Sampling techniques worked for me. But other kagglers were successful with augmentation ([here](https://www.kaggle.com/c/lish-moa/discussion/200600) and [here](https://www.kaggle.com/c/lish-moa/discussion/200540)).
  - Creating a good Cross Validation scheme was difficult for this one. I used Multi Label Stratified KFold splitting using [this repo](https://github.com/trent-b/iterative-stratification) and [Chris's Strategy](https://www.kaggle.com/c/lish-moa/discussion/195195) to use Drug Information for Cross Validation. 

## Main Ideas

### Traditional Classification Models Don't Work Here
- Traditional classifications models like Logistic Regression don't work for multi-label problems. But I ended up using XGBoost model as a part of final blending models. 
- I tried to use XGBoost to improve the top 20 labels adding the most loss but wasn't successful. 

### Build Single Models
I joined this competition almost 2 months late. Had 1 month to work on this competition. So I ended up starting with the following top public notebooks as my single models:
- Simple 3 Layer DNN Model 
- TabNet Model
- PyTorch Transfer Learning
- TabNet Pretraining

### Creating Scoring Files
Scoring scripts are created by using IPython convert scripts to convert a notebook to a Python file. They can be run using
```bash
!ipython script.py
```

### Blending Models
- Currently being edited.

## Final Submission
- Currently being edited.

## Acknowledgment
- Currently being edited.