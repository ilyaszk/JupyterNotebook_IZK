# myapp

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

# Projet de Prédiction et Analyse d'Appartements - Rendu Noté

Ce projet consiste à manipuler un dataset d'appartements, effectuer des analyses statistiques et des prédictions à l'aide de différents algorithmes de Machine Learning. Le projet est individuel et sera noté.

## Objectifs

### 1. Manipulation de données :
- Ajout de colonnes : `annee`, `balcon`, `garage`, `note`, `price_category`.
- Simulation d'un dataset réaliste avec entre 50 et 100 appartements.

### 2. Analyses statistiques (avec Numpy et Pandas) :
- **Surface** : Moyenne, écart-type, surface minimale et maximale.
- **Année de construction** : Moyenne, construction la plus ancienne et la plus récente.
- **Balcon** : Proportion d'appartements avec balcon.
- Comptage des catégories de prix (`low`, `normal`, `high`, `scam`).
- **Nombre de chambres** : Moyenne, médiane, variance, écart-type.

### 3. Visualisations (avec Matplotlib) :
- Diagramme à barres pour la répartition des catégories de prix.
- **Bonus** : Heatmap pour la corrélation entre l'année de construction et le prix.

### 4. Modélisation (avec Scikit-learn) :
- **Régression linéaire** pour prédire la note en fonction de la ville, de la surface et du prix.
- **Régression linéaire** pour prédire l'année en fonction de la ville, avec évaluation par R² et RMSE.
- **Classification logistique** pour prédire la présence d'un garage en fonction du prix et de la ville.
- **Classification par KNN** pour prédire la présence d'un balcon en fonction du prix et de la ville.
- Comparaison des performances (accuracy, recall, F1-score) des modèles de classification logistique et KNN.
- **Bonus ULTIME** : Classification avec **Random Forest** pour prédire la présence d'un balcon.

### 5. Mise en place d'une API :
- Créer une API pour les prédictions des points 2, 3, et 4.
- Intégration des prédictions dans un formulaire d'ajout d'appartement.

## Livrables

- Un **Jupyter Notebook** documenté contenant :
  - Le code pour la manipulation des données, les analyses statistiques, les visualisations et les modèles prédictifs.
  - Les résultats des évaluations des modèles de classification et de régression.
