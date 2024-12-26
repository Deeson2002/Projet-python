# Modélisation Prédictive de la Gravité des Accidents Routiers en France
**Contexte :**

-Les accidents de la route représentent un enjeu majeur, tant humain qu’économique. En 2021, leur coût en France était estimé à 46,3 milliards d’euros, incluant les soins médicaux, réparations, pertes de productivité et indemnisations.

-Ce projet vise à prédire la gravité des accidents routiers à partir de données socio-démographiques, environnementales et techniques, en utilisant des techniques de machine learning. L’objectif est de fournir des informations exploitables pour orienter les politiques publiques, ajuster les stratégies assurantielles, et optimiser la gestion des risques liés à la sécurité routière.

-Les analyses et prédictions réalisées dans ce projet permettront :

**Une meilleure compréhension des facteurs influençant la gravité des accidents, tels que l’âge des conducteurs, le type d’agglomération ou la présence de dispositifs de sécurité.**

**Une segmentation précise des profils d’accidents, facilitant un ciblage efficace des interventions.**

**Une optimisation des coûts sociaux et économiques liés aux accidents.**

# Problématique : 
Comment peut-on mettre en place une segmentation efficace des accidents routiers en fonction de leur gravité tout en explorant des possibilités d'optimisation des modèles prédictifs pour améliorer la précision et la performance des résultats ? 

# Plan du Projet

# 1. Préparation et Traitement des Données
-Nous utiliserons trois bases de données issues de la plateforme data.gouv.fr :

**caract-2023**

**usagers-2023**

**vehicules-2023**

-Ces bases couvrent 54 822 accidents survenus en France en 2023. Un fichier descriptif des variables est inclus dans le dépôt (Description des bases de données annuelles_2021).

-Les étapes principales seront :

**Fusion des bases de données à partir de clés communes, afin de construire une base unifiée intégrant facteurs socio-démographiques, environnementaux et techniques.**

**Nettoyage des données, incluant :**

**Détection et gestion des valeurs manquantes, doublons et valeurs aberrantes.**

**Création de variables synthétiques, comme l’âge (calculé à partir de la date de naissance), et identification de regroupements via K-means.**

**Identification et traitement des outliers à l’aide de techniques et Isolation Forest.**

-Résultat attendu : Une base de données propre et prête pour l’analyse descriptive.

# 2. Analyse Descriptive et Exploration des Données

L’analyse descriptive sera réalisée en deux étapes :

Univariée : Exploration de chaque variable pour identifier les tendances globales. Les caractéristiques des accidents seront étudiées en fonction de l’âge des conducteurs, du type d’agglomération, des dispositifs de sécurité, etc.

Bivariée : Analyse des relations entre deux variables, par exemple :

La corrélation entre la gravité des accidents et les conditions météorologiques.

L’impact du type de véhicule sur la gravité des blessures.

Nous utiliserons des visualisations graphiques (histogrammes, heatmaps, scatter plots) pour identifier des patterns et mieux comprendre les interactions complexes entre les variables.

Objectif : Confirmer que les facteurs socio-démographiques, environnementaux et techniques influencent significativement la gravité des accidents.

# 3. Modélisation Prédictive

Nous mettrons en œuvre des modèles de machine learning pour segmenter les données et prédire la gravité des accidents :

Modèles utilisés :

Random Forest

XGBoost

Évaluation des performances :

Précision

Rappel

F-mesure

Courbes ROC

Nous intégrerons également une réduction de la dimensionnalité pour optimiser les performances tout en réduisant le nombre de variables. Cette étape permettra :

Une rapidité accrue des traitements.

Une gestion plus efficace des coûts associés à l’analyse des données.

Objectif final : Identifier le modèle le plus performant et fournir des insights exploitables pour améliorer la sécurité routière.
