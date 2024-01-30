# Predictive Maintenance Framework for Metro do Porto's APU System

## Abstract

This repository contains the research and implementation of a data-driven predictive maintenance framework for the Air Production Unit (APU) system within Metro do Porto trains. Utilizing deep learning autoencoder networks, this framework aims to identify machinery failures early, reducing false alarms and enhancing maintenance efficiency.

## Background

Predictive Maintenance (PdM) is crucial in public transport for minimizing operational disruptions and shifting from reactive to predictive strategies. The APU system, crucial for various functions, including maintaining vehicle height, is the focus of this project.

## Data Description

The `MetroPT-3` dataset, used for this study, spans from February to August 2020, featuring 15,169,480 data points with 15 features from 7 analog and 8 digital sensors. The dataset is vital for anomaly detection and benchmarking machine learning algorithms.

### Analog Signals
1. TP2 (bar)
2. TP3 (bar)
3. H1 (bar)
4. DV pressure (bar)
5. Reservoirs (bar)
6. Motor Current (A)
7. Oil Temperature (ºC)

### Digital Signals
1. COMP
2. DV electric
3. TOWERS
4. MPG
5. LPS
6. Pressure Switch
7. Oil Level
8. Caudal Impulse

## Exploratory Data Analysis

We analyze the operational trends versus failure trends, finding distinct differences that can be leveraged for predicting failures.

## Approaches

1. **Binary Classification:** Initially tried using various models like Decision Trees, Random Forest, and Neural Networks. While results were impressive, this method didn't predict failures before occurrence.

2. **Time to Failure Prediction:** This method aimed to predict the time to failure but was limited in practical utility.

## Autoencoders in Anomaly Detection

1. **Sparse Autoencoders:** Focuses on sparsity in hidden layers for robust feature learning.
2. **Variational Autoencoders:** Incorporates a probabilistic approach for robustness against input noise.

### Anomaly Detection Process

- **Training Phase:** Autoencoders are trained on normal operation data.
- **Testing Phase:** The model is tested against new, unseen data to identify anomalies.

## Online Learning with Autoencoders

Our methodology involves continuous training with operational data, excluding failure instances. This includes iterative training and testing with data from subsequent months.

## Model Training and Test Results

We employ both Sparse and Variational Autoencoders on digital and analog signals. The results indicate that digital signals with Sparse Autoencoders provide the best results, achieving near 100% accuracy in predicting failures 24 hours in advance.

## Future Exploration

The plan is to explore advanced techniques like LSTM, Transformers, and Causal Forests for deeper insights and improved prediction accuracy.
