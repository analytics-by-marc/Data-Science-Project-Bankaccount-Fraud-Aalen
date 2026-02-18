# Data-Science-Project-Bankaccount-Fraud-Aalen

Erstellt mit Python Version 3.10.18

Der Datensatz steht auf Kaggle zur Verfügung, hier sollte Variante 3 ausgewählt werden da hier noch x1 und x2 ind en Daten enthalten sind
https://www.kaggle.com/datasets/sgpjesus/bank-account-fraud-dataset-neurips-2022

bankaccount_fraud_final ist die bereinigte Version mit den besten Modellen, einen Überblick über die Ergebnisse mit konkreten Werten und Visalisierung ist unter "presentation" verfügbar

Projektziele

    Mindestens 75 % der Betrugsfälle sollen erkannt werden
    
    Aufbau von vollständigen Fraud‑Detection‑Pipelines
    
    Umgang mit stark unausgeglichenen Daten (≈ 1.1 % Fraud)

    Vergleich verschiedener Machine Learning Modelle

    Optimierung von Precision/Recall (Score-Parameter) durch die Optimierung des Thresholds

    Visualisierung der Modellperformance

Datenvorbereitung

    Entfernen irrelevanter Spalten

    Erkennen & Imputieren fehlender Werte

    Encoding für kategoriale Variablen

    MinMax‑Skalierung

    Entfernen von Features mit geringer Varianz

    Prüfung auf Multikollinearität

Explorative Analyse

    Analyse der rate an Betrugsfällen

    Verteilungen aller Features

    Crosstabs für Einkommen, Alter, Employment Status

    Histogramme & KDE‑Plots

Modelle

Trainierte Modelle:

    Logistic Regression (mit GridSearchCV + SMOTE‑Varianten)

    Random Forest

    Gradient Boosting

    XGBoost

    LightGBM

    Neuronales Netz (TensorFlow/Keras)

Bestes Modell und Ergebnisse:  
LightGBM mit der höchsten ROC‑AUC und dem besten F1‑Score.

    LightGBM ROC‑AUC: ~0.88

    Logistic Regression und Neural Network knapp dahinter

    Threshold‑Optimierung verbessert Recall deutlich

    Precision‑Recall‑Kurven & Confusion Matrix zur Bewertung

Wichtigste angewandte Pakete:

Python, Pandas, NumPy, Scikit‑Learn, LightGBM, XGBoost, TensorFlow/Keras, Imbalanced‑Learn, Matplotlib, Seaborn
    

