# 🩺 Cancer Health Improvement Prediction App

Application web interactive de prédiction de l'amélioration de la santé des patients atteints de cancer, basée sur un ensemble de modèles de Machine Learning.

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Streamlit](https://img.shields.io/badge/framework-streamlit-red.svg)
![ML](https://img.shields.io/badge/ML-ensemble-green.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

## 📋 Description

Cette application utilise un **modèle d'ensemble (Voting Classifier)** combinant plusieurs algorithmes de classification pour prédire si un patient atteint de cancer connaîtra une amélioration de son état de santé :

- ✅ **Classe 1** : Amélioration
- ❌ **Classe 0** : Non amélioration

Le modèle prend en compte diverses caractéristiques cliniques, biologiques et thérapeutiques pour fournir une prédiction avec probabilités associées.

## 🎯 Fonctionnalités

- 📊 Interface interactive avec Streamlit pour saisir les données patient
- 🤖 Modèle d'ensemble combinant XGBoost, CatBoost, LightGBM et Random Forest
- 📈 Visualisation des probabilités de prédiction
- 📁 Support de chargement de données (CSV ou upload manuel)
- 💾 Cache intelligent pour optimiser les performances
- 🎨 Interface utilisateur intuitive avec organisation en colonnes

## 🧠 Modèles utilisés

L'application utilise un **Voting Classifier** avec pondération optimisée :

| Modèle | Poids | Hyperparamètres clés |
|--------|-------|----------------------|
| XGBoost | 1 | learning_rate=0.2, max_depth=3, n_estimators=100 |
| CatBoost | 1 | depth=4, iterations=200, learning_rate=0.1 |
| LightGBM | 4 | learning_rate=0.2, max_depth=3, n_estimators=200 |
| Random Forest | 1 | n_estimators=100, max_depth=None |

Le vote est effectué en mode **soft** pour exploiter les probabilités de chaque modèle.

## 📊 Features utilisées

L'application utilise **17 features** réparties en plusieurs catégories :

### Données démographiques et cliniques
- `age_at_diagnosis` : Âge au diagnostic
- `taille` : Taille du patient

### Marqueurs biologiques
- `CA19-9` : Marqueur tumoral CA19-9
- `ACE` : Antigène carcinoembryonique (CEA)

### Caractéristiques tumorales
- `volume_colon` : Volume du côlon
- `nombre_metastaes` : Nombre de métastases
- `tumor_size_total` : Taille totale de la tumeur

### Traitements médicamenteux
- `capécitabine`, `oxaliplatine`, `irinotécan`
- `bévacizumab`, `panitumumab`, `cetuximab`

### Types de traitement
- `chimiothérapie_exclusive` : Chimiothérapie seule
- `chirurgie` : Intervention chirurgicale

### Marqueurs génétiques
- `RAS_0.0`, `RAS_2.0` : Statut RAS
