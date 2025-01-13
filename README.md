# Dépression des Étudiants 


## Description du Projet

Ce projet vise à analyser les facteurs associés à la dépression chez les étudiants à partir d'un ensemble de données anonymisées. En utilisant des méthodes statistiques et des modèles d'apprentissage automatique, nous cherchons à prédire la probabilité qu'un étudiant soit en dépression. L'objectif final est de fournir des insights utiles pour la prévention.

## Contexte
La dépression est un trouble psychologique qui touche un grand nombre de personnes, y compris les étudiants. Comprendre les causes et les facteurs de risque est essentiel pour anticiper les comportements à risque et proposer des mesures de soutien adaptées.

## Étapes de l'analyse 
Le projet suit les étapes suivantes :


### Exploration des Données :

![Capture d’écran 2025-01-13 195414](https://github.com/user-attachments/assets/b1e54819-4ff5-4b4b-a1e6-c4512901e3b3)

- Chargement et nettoyage des données.
- Analyse descriptive pour identifier les tendances générales.

### Analyse Statistique :
- Création de graphiques (bar plots et box plots) pour les variables qualitatives et quantitatives afin d'analyser la répartition de nos données.
- Tests statistiques (Chi-deux pour les variables qualitatives, Kruskal-Wallis pour les variables quantitatives) afin d'identifier les facteurs significatifs.

### Préparation des Données :
- Transformation des variables catégoriques en variables binaires.
- Division des données en ensembles d'entraînement et de test.

### Modélisation :
- Création d'un modèle de régression logistique pour prédire la dépression.
- Évaluation de la qualité du modèle à l'aide de la courbe ROC.
- Exploration d'autres modèles comme les arbres de décision, Random Forest, AdaBoost, et SVM.

## Résultats
### Régression Logistique

![Capture d’écran 2025-01-13 194349](https://github.com/user-attachments/assets/51484df8-04b5-45ec-b11f-bcafebbd8c4d) 

Le premier modèle utilisé est une régression logistique. Les résultats montrent un AUC (Area Under the Curve) de 0,90 sur l'ensemble d'entraînement et 0,90 sur l'ensemble de test, autrement dit le modèle est capable de prédire 9 fois sur 10 le bon résultat, indiquant une bonne capacité de prédiction.
Enfin, le modèle ne présente ni overfitting ni underfitting puisque les courbes de validation et de test sont assez proches, ce qui accentue sa robustesse.



L'équation du modèle final est la suivante :

**ln(p/(1-p)) = −1.8913 − 0.1000 × Age + 0.0521 × Note_a_l’ecole + 0.1157 × Heures_de_travail + 1.9041 × Pression_Academique_5.0 + 0.4483 × Habitudes_alimentaires_Moderate + 1.0410 × Habitudes_alimentaires_Unhealthy + 2.5692 × Suicidaire_Yes + 0.4110 × Stress_financier_2.0 + 1.0448 × Stress_financier_3.0 + 1.4930 × Stress_financier_4.0 + 2.1803 × Stress_financier_5.0 + 0.2788 × Prblml_mentaux_famille_Yes**

### Modèles Alternatifs
Plusieurs autres modèles ont été testés :

- Arbre de Décision : Le modèle montre une bonne capacité de prédiction, mais il présente un léger overfitting.
- Random Forest : Ce modèle présente un surajustement important, le rendant moins efficace.
- AdaBoost et SVM : Ces deux modèles offrent de bonnes performances, avec des scores équilibrés entre les ensembles d'entraînement et de test. Le SVM a été retenu comme modèle final.

### Optimisation du SVM

![Capture d’écran 2025-01-13 195244](https://github.com/user-attachments/assets/07d8d7c6-5560-4cb3-9c90-5426c47abc3c)

Un nouveau modèle avec une recherche d'hyperparamètres a été effectuée pour optimiser le modèle SVM. Le modèle présente une bonne performance et un faible risque d'overfitting ou d'underfitting. 

![Capture d’écran 2025-01-13 195148](https://github.com/user-attachments/assets/b6289d39-bd10-4085-80cd-08abda447328)


Toutefois, les résultats finaux n'ont pas montré d'amélioration significative par rapport au modèle de base, puisque dans les deux cas (avec et sans optimisation), la précision générale est de 0,81 ce qui est plus faible que le score obtenu avec la régression linéaire.


## Conclusion
La régression linéaire a été retenu comme le meilleur modèle pour prédire la dépression chez les étudiants, avec un score de précision globale de plus de 89 %. Ce modèle pourrait être utilisé pour identifier les étudiants à risque et orienter les efforts de prévention.

## Perspectives d'Amélioration
- Utilisation de modèles plus avancés comme les réseaux de neurones.
- Collecte de données supplémentaires pour affiner les prédictions.
- Étude de l'impact de nouvelles variables comme le contexte familial ou les interactions sociales.


Projet réalisé par Nesho Kanthakumar

