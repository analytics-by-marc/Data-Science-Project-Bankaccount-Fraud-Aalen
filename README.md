# Data-Science-Project-Bankaccount-Fraud-Aalen
Erstellt mit Python Version 3.10.18

🔍 Projektziele

    Mindestens 75 % der Betrugsfälle sollen erkannt werden
    
    Aufbau von vollständigen Fraud‑Detection‑Pipelines
    
    Umgang mit stark unausgeglichenen Daten (≈ 1.1 % Fraud)

    Vergleich verschiedener Machine Learning Modelle

    Optimierung von Precision/Recall (Score-Parameter) durch die Optimierung des Thresholds

    Visualisierung der Modellperformance

📂 Inhalt

    Datenvorbereitung

        Laden & Prüfen des Datensatzes

        Umgang mit fehlenden Werten

        Entfernen von Spalten mit >50 % Missing Values

        Encoding & Skalierung

        Varianzanalyse und Entfernen von Spalten

        Entfernen von Features mit hoher Korrelation

    Datenanalyse

        Verteilungen aller Features

        Crosstabs für geschützte Attribute

        Analyse der Rate an Betrugsfällen

        Density‑Plots für numerische Features

    Modelle

        Logistic Regression (mit GridSearchCV + SMOTE‑Varianten)

        Decision Trees

        Random Forest

        Gradient Boosting

        XGBoost

        LightGBM

        Neuronales Netz (TensorFlow/Keras)

    Modellvergleich

        ROC‑AUC

        Precision

        Recall

        F1‑Score

        Precision‑Recall‑Kurven

        Threshold‑Optimierung

🧹 Datenvorbereitung
1. Entfernen unnötiger Spalten
python

X = df_bankaccounts.drop(columns=["x1", "x2", "fraud_bool"])
y = df_bankaccounts["fraud_bool"]

2. Missing Values erkennen & behandeln

    Negative Werte → als fehlend markiert

    Spalten mit >50 % Missing Values entfernt

    Median‑Imputation für verbleibende Spalten

3. Encoding

    One‑Hot‑Encoding für kategoriale Variablen

    Manuelles One‑Hot‑Encoding für numerische Kategorien (income, age, month)

4. Skalierung

MinMaxScaler auf alle numerischen Features.
5. Feature Selection

    Entfernen stark korrelierter Features

    VarianceThreshold (0.01)

📊 Explorative Datenanalyse

    Fraud‑Rate: 1.103 %

    Barplots für Einkommen, Alter, Employment Status

    Crosstabs: Fraud‑Rate pro Kategorie

    Histogramme & KDE‑Plots für numerische Features

🤖 Modelle & Ergebnisse
Logistic Regression

    GridSearchCV mit:

        L1/L2‑Regularisierung

        SMOTE / BorderlineSMOTE / None

        Verschiedene Solver

    Bestes Ergebnis:

        ROC‑AUC ≈ 0.856

        Recall stark abhängig vom Threshold

LightGBM (bestes Modell)

    Hyperparameter‑Tuning über GridSearchCV

    Bestes Ergebnis:

        ROC‑AUC ≈ 0.875

        Sehr gute Trennung trotz Imbalance

        Recall bis 75 % erreichbar durch Threshold‑Tuning

Neuronales Netz

    2 Hidden Layers (64 → 32 Neuronen)

    BatchNorm + Dropout

    Class Weights für Imbalance

    Ergebnis:

        ROC‑AUC ≈ 0.862

        Sehr stabil, aber LightGBM leicht besser

🎯 Threshold‑Optimierung

Für alle Modelle wurden Precision‑Recall‑Kurven analysiert:

    Schnittpunkt Precision = Recall → optimaler F1‑Threshold

    Zusätzlich: Threshold für Recall = 0.75 berechnet

    Visualisierung aller Kurven

📈 Modellvergleich (Testdaten)
Modell	ROC‑AUC	Precision	Recall	F1
Logistic Regression	~0.86	sehr niedrig	hoch (mit Threshold)	niedrig
LightGBM	~0.88	moderat	hoch	bester F1
Neural Network	~0.86	niedrig	hoch	ähnlich LogReg

LightGBM ist das beste Modell im Projekt.
🖼 Visualisierungen

Das Projekt enthält u. a.:

    ROC‑Kurven

    Precision‑Recall‑Kurven

    Confusion Matrices

    Feature‑Verteilungen

    F1‑Score‑Threshold‑Kurven

    Modellvergleich als Balkendiagramm

🧠 Technologien

    Python

    Pandas, NumPy

    Scikit‑Learn

    XGBoost, LightGBM

    TensorFlow / Keras

    Matplotlib, Seaborn

    Imbalanced‑Learn

🚀 Fazit

Dieses Projekt zeigt einen vollständigen End‑to‑End‑Machine‑Learning‑Workflow für Fraud Detection mit stark unausgeglichenen Daten.
Durch systematische Datenvorbereitung, Modellvergleich und Threshold‑Optimierung konnte ein leistungsstarkes Modell (LightGBM) entwickelt werden.

