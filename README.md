# Modélisation prédictive de la gravité des accidents routiers en France : effets des facteurs socio-démographiques, techniques et environnementaux

# PROJET DE PYTHON POUR LA DATA SCIENCE

**Encadré par:**

-Monsieur BENHELAL

**Réalisé par :**

-ROUCHI Wail

-HOUNKPEVI Crespin Elisée

-DJENONTIN Deeson

**Contexte :**

-Les accidents de la route représentent un enjeu majeur, tant humain qu’économique. En 2021, leur coût en France était estimé à 46,3 milliards d’euros, incluant les soins médicaux, réparations, pertes de productivité et indemnisations.

-Ce projet vise à prédire la gravité des accidents routiers à partir de données socio-démographiques, environnementales et techniques, en utilisant des techniques de machine learning. L’objectif est de fournir des informations exploitables pour orienter les politiques publiques, ajuster les stratégies assurantielles, et optimiser la gestion des risques liés à la sécurité routière.

-Les analyses et prédictions réalisées dans ce projet permettront :

**Une meilleure compréhension des facteurs influençant la gravité des accidents, tels que l’âge des conducteurs, le type d’agglomération ou la présence de dispositifs de sécurité.**

**Une segmentation précise des profils d’accidents, facilitant un ciblage efficace des interventions.**

**Une optimisation des coûts sociaux et économiques liés aux accidents.**

# Problématique : 

Comment mettre en place une segmentation efficace des accidents routiers selon leur gravité, tout en explorant des pistes d'optimisation des modèles prédictifs pour maximiser la précision et la rapidité des résultats ?

# Plan du Projet

# 1. Préparation et Traitement des Données
-Nous utiliserons trois bases de données issues de la plateforme data.gouv.fr :

**caract-2023 : Contient des informations sur les caractéristiques des accidents (date, heure, conditions météorologiques ...).**

**usagers-2023 : Regroupe des données sur les usagers impliqués dans les accidents (âge, sexe ...).**

**vehicules-2023 : Fournit des détails sur les véhicules impliqués (type de véhicule ...).**

-Ces bases couvrent 54 822 accidents survenus en France en 2023. Un fichier descriptif des variables est inclus dans le dépôt (Description des bases de données annuelles_2021).

-Les étapes principales seront :

**Élimination de quelques variables indésirables pour notre étude.**

**Fusion des bases de données à partir de clés communes, afin de construire une base unifiée intégrant facteurs socio-démographiques, environnementaux et techniques.**

**Nettoyage des données, incluant :**

*1) Détection et gestion des valeurs manquantes, des doublons et des valeurs erronées.*

*2) Création de variables synthétiques, comme l’âge (calculé à partir de la date de naissance), et identification de regroupements via K-means.*

*3) Identification et traitement des outliers à l’aide de techniques et Isolation Forest.*

**-Résultat attendu : Une base de données propre et prête pour l’analyse descriptive.**

# 2. Analyse Descriptive et Exploration des Données

-L’analyse descriptive sera réalisée en deux étapes :

1) Univariée : Exploration de chaque variable pour identifier les tendances globales. Les caractéristiques des accidents seront étudiées en fonction de l’âge des conducteurs, du type d’agglomération, des dispositifs de sécurité, etc.

**-Nous utiliserons également des cartographies analytiques pour mieux mettre en évidence les tendances géographiques et les effets environnementaux, ainsi que leur impact sur la gravité des accidents.**

2) Bivariée : Analyse des relations entre différentes variables, par exemple :

*La corrélation entre la gravité des accidents et les conditions d’éclairage.*

*L’impact du type de véhicule sur la gravité des blessures.*

**-Nous utiliserons des visualisations graphiques pour identifier des patterns et mieux comprendre les interactions complexes entre les variables.**

**-Ainsi, l'objectif de cette partie sera de confirmer que les facteurs socio-démographiques, environnementaux et techniques influencent de manière significative la gravité des accidents, tout en identifiant les variables les plus déterminantes. Cela nous permettra d’obtenir une vision plus claire de notre problématique avant de la modéliser et de la concrétiser à travers des modèles prédictifs.**

# 3. Modélisation Prédictive

-Pour quantifier cette corrélation et obtenir des prédictions concrètes, nous choisissons d'utiliser les modèles RandomForestClassifier et XGBClassifier, qui sont bien adaptés à la segmentation des données. Ces modèles seront évalués en termes de performance à l’aide de recall, du score F1, des matrices de confusion et des courbes ROC.

-L’évaluation nous montrera quel modèle est le plus efficace, celui offrant la meilleure capacité de prédiction.

-Enfin, une réduction du nombre de variables sera réalisée à travers l'identification des variables les plus importantes pour simplifier le modèle tout en préservant sa précision. Cette approche permettra d’optimiser le modèle, de réduire les coûts de collecte de données et d'accélérer le traitement des informations, ce qui est essentiel dans le cadre d’une étude à grande échelle impliquant des métadonnées.

**-Ainsi, l'objectif de ce travail sera de répondre à notre problématique en segmentant efficacement les accidents selon leur gravité et en identifiant les variables les plus importantes, tout en optimisant les modèles pour une prédiction précise et rapide.**

# Imports et installations nécessaires pour le projet 

import pandas as pd

import numpy as np

import matplotlib.pyplot as plt

import seaborn as sns

import plotly.express as px

import plotly.graph_objects as go

from sklearn.ensemble import IsolationForest, RandomForestClassifier

from sklearn.cluster import KMeans

from sklearn.preprocessing import StandardScaler

from sklearn.model_selection import train_test_split, cross_val_score

from sklearn.metrics import classification_report, accuracy_score, confusion_matrix, roc_curve, roc_auc_score, f1_score

from sklearn.feature_selection import SelectFromModel

from sklearn.preprocessing import label_binarize

from scipy.stats import chi2_contingency

import xgboost as xgb

from matplotlib import colormaps

pip install nbformat

# Référence

**Galiana, Lino. 2023.** *Python pour la Data Science*. [https://doi.org/10.5281/zenodo.8229676](https://doi.org/10.5281/zenodo.8229676).
