# Etre_ou_NePasEtre
# Rapport sur la classification binaire des données médicales

## 1. Compréhension du problème

### Description

L'objectif de ce projet est de prédire la survie des patients pendant leur séjour à l'hôpital à partir de leurs données médicales. Le jeu de données contient des informations sur 80 000 patients avec 342 variables, incluant des variables numériques, binaires et catégoriques.

### Métrique utilisée

La métrique principale est la **Balanced Accuracy Score** de Scikit-learn, car la distribution des classes est déséquilibrée (environ 3 % des patients décèdent). Cette métrique permet de mieux évaluer la performance du modèle sur des classes minoritaires.

## 2. Exploration des données

### Chargement des données

Les données sont chargées à partir d'un fichier CSV contenant l'ensemble d'entraînement avec les étiquettes associées.

### Analyse exploratoire

- Identification des types de variables : numériques, binaires, catégoriques.
- Visualisation des distributions des variables les plus importantes (âge, glucose, tension artérielle).
- Étude de la corrélation entre les variables et la variable cible (décès).
- Gestion des valeurs manquantes et nettoyage des données.

## 3. Prétraitement des données

### Techniques utilisées

- Imputation des valeurs manquantes avec la médiane ou la moyenne.
- Encodage des variables catégoriques avec OneHotEncoder.
- Normalisation des variables numériques.
- Gestion des classes déséquilibrées avec la méthode SMOTE (Synthetic Minority Oversampling Technique).

## 4. Modélisation

### Modèles testés

- Régression Linéaire
- Arbres de Décision
- Random Forest
- Gradient Boosting
- Support Vector Machine (SVM)

### Sélection des hyperparamètres

Recherche par validation croisée avec GridSearchCV pour trouver les meilleurs paramètres pour chaque modèle.

## 5. Évaluation

| Modèle              | Balanced Accuracy | Precision | Recall   |
| ------------------- | ----------------- | --------- | -------- |
| Régression Linéaire | 0.52              | 0.32      | 0.58     |
| Random Forest       | 0.51              | 0.55      | 0.63     |
| Gradient Boosting   | **0.58**          | **0.61**  | **0.70** |

Meilleur score possible avec data augmentation (LogisticRegression et SMOTE) : 0.7497358105635532 .

## 6. Interprétation des résultats

- Les modèles complexes (Gradient Boosting) permettent une meilleure prédiction des classes minoritaires.
- La gestion des classes déséquilibrées avec SMOTE améliore significativement les performances.
- La combinaison de la normalisation et de l'encodage permet d'améliorer la convergence des modèles linéaires.

## 7. Conclusion

Ce projet a permis de développer des modèles de classification binaire pour prédire la mortalité hospitalière. Le modèle Gradient Boosting a obtenu les meilleures performances. L'utilisation de techniques de prétraitement et de gestion des déséquilibres a été essentielle pour améliorer la qualité des prédictions.

## Références

- Scikit-learn Documentation : [https://scikit-learn.org/](https://scikit-learn.org/)
- Imbalanced-learn Documentation : [https://imbalanced-learn.org/](https://imbalanced-learn.org/)


