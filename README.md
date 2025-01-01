<h1>Introduction</h1>

Ce code réalise une Analyse en Composantes Principales (ACP) sur le jeu de données Iris, un ensemble classique en apprentissage automatique. Le jeu de données contient des mesures de la longueur et de la largeur des sépales et des pétales pour trois espèces d'Iris : Setosa, Versicolor et Virginica. 

Les objectifs de ce code sont :
- Effectuer des analyses univariées, bivariées et multivariées sur les données.
- Standardiser les données et appliquer une ACP pour réduire la dimensionnalité.
- Visualiser et interpréter les résultats de l'ACP.
Informations sur le jeu de données
Le jeu de données Iris contient les colonnes suivantes :
- **sepal_length** : Longueur du sépale (cm)
- **sepal_width** : Largeur du sépale (cm)
- **petal_length** : Longueur du pétale (cm)
- **petal_width** : Largeur du pétale (cm)
- **species** : Espèce de la fleur d'Iris (Setosa, Versicolor, Virginica)

### Caractéristiques des données :
- Nombre total de lignes : 150
- Nombre total de colonnes : 5
- Pas de valeurs manquantes
Structure du code
1. Bibliothèques utilisées
Les bibliothèques suivantes sont importées :
- **numpy** : Pour les calculs numériques.
- **pandas** : Pour la manipulation des données.
- **matplotlib** : Pour la création de graphiques.
- **seaborn** : Pour les visualisations avancées.
- **scipy.stats** : Pour les tests statistiques.
- **sklearn.preprocessing** : Pour la standardisation des données.
- **sklearn.decomposition** : Pour l'ACP.
- **sklearn.datasets** : Pour charger des jeux de données d'exemple.
2. Étapes effectuées
#### A. Analyse univariée
- Les statistiques descriptives sont calculées à l'aide de `df.describe()`.
- Des histogrammes avec courbes KDE sont tracés pour chaque variable.
- Le test de Shapiro-Wilk est utilisé pour vérifier la normalité.
- Les valeurs aberrantes sont identifiées à l'aide de boxplots.

#### B. Analyse bivariée
- Les relations par paire sont visualisées à l'aide de `sns.pairplot()`.
- Une heatmap est utilisée pour montrer les corrélations entre variables.
- Des boxplots comparent les variables quantitatives entre espèces.
- Le test de Kruskal-Wallis vérifie les différences significatives entre espèces pour chaque variable.

#### C. Analyse multivariée avec l'ACP
1. Préparation des données :
   - Les données sont séparées en variables explicatives (**X**) et variable qualitative (**y**).
   - Les données sont standardisées à l'aide de `StandardScaler`.
2. Application de l'ACP :
   - L'ACP est réalisée avec `sklearn.decomposition.PCA`.
   - La variance expliquée et les valeurs propres sont calculées et tabulées.
   - Un scree plot est généré pour déterminer le nombre optimal de composantes principales.
3. Contributions des variables :
   - Les contributions des variables à chaque composante principale sont calculées.
   - Les contributions sont exprimées en pourcentages.
4. Contributions individuelles :
   - Les contributions des points de données individuels à chaque composante principale sont calculées et converties en pourcentages.

#### D. Visualisation
- Pairplots avec une coloration par espèce.
- Scree plot pour afficher la variance expliquée par chaque dimension.
- Heatmap de la matrice de corrélation.
- Cercle de corrélation (code partiellement fourni).
3. Résultats
#### A. Tableaux
- Statistiques descriptives des variables.
- Valeurs propres, variance expliquée et variance cumulée.
- Contributions des variables à chaque composante principale.
- Contributions des points individuels à chaque composante principale.

#### B. Visualisations
- Histogrammes et tracés KDE pour l'analyse univariée.
- Pairplot et boxplots pour l'analyse bivariée.
- Heatmap pour les corrélations.
- Scree plot.
- Cercle de corrélation pour les contributions des variables.
Instructions d'utilisation
1. Installez les bibliothèques nécessaires avec pip :
   ```bash
   pip install numpy pandas matplotlib seaborn scipy scikit-learn
   ```
2. Chargez et exécutez le code dans un IDE Python ou un Jupyter Notebook.
3. Suivez les résultats structurés dans la console et les visualisations pour interpréter les résultats.
Interprétation des résultats de l'ACP
- La première composante principale (PC1) explique 92 % de la variance, indiquant que la majorité de la variabilité du jeu de données est capturée par cette dimension.
- La variance expliquée cumulée atteint 98 % avec deux composantes (PC1 et PC2), ce qui est suffisant pour représenter les données.
- La variable **petal_length** contribue le plus à PC1, suivie de **petal_width**.
- La visualisation des contributions individuelles offre une perspective sur les points de données les plus influents dans chaque composante principale.
Améliorations potentielles
- Améliorer la visualisation du cercle de corrélation.
- Ajouter des modèles de clustering ou de classification en utilisant les dimensions réduites.
- Fournir des insights supplémentaires sur l'amélioration des tâches avales comme la classification ou la régression grâce à l'ACP.
