# TP 3 : Apprentissage Non Supervisé

## 📋 Description

Ce TP explore les techniques de **clustering non supervisé** appliquées à la reconnaissance de chiffres manuscrits. Deux algorithmes principaux sont étudiés :
- **Classification Ascendante Hiérarchique (CAH)**
- **K-Moyennes (K-means)**

## 🎯 Objectifs

- Développer et évaluer des modèles de classification non supervisée
- Comparer les performances de la CAH et du K-means
- Analyser la structure hiérarchique des données via des dendrogrammes
- Identifier des groupements naturels dans les chiffres manuscrits

## 📊 Jeu de données : Digits

Le dataset **Digits** de scikit-learn contient :
- **1797 images** de chiffres manuscrits (0-9)
- Images en **niveaux de gris 8×8 pixels** (64 features par image)
- Valeurs de pixels variant de **0 à 16**

## 🛠️ Technologies utilisées

```python
- Python 3.x
- scikit-learn
- scipy
- numpy
- matplotlib
- seaborn
```

## 📝 Structure du TP

### Partie 1 : Exploration des données
1. Importation du jeu de données Digits
2. Détermination des dimensions
3. Affichage de la description
4. Visualisation d'échantillons d'images

### Partie 2 : Classification Ascendante Hiérarchique (CAH)
5. Génération de la matrice des liens avec `linkage()`
6. Visualisation du dendrogramme
7. Découpage du dendrogramme avec `fcluster()`
8. Attribution des classes aux images
9. Interprétation des groupements formés

### Partie 3 : K-Moyennes (K-means)
10. Clustering avec `KMeans` (10 clusters)
11. Visualisation des résultats

### Partie 4 : Comparaison des méthodes
12. Tableau de contingence (confusion matrix)
13. Analyse comparative CAH vs K-means

## 📁 Structure du projet

```
TP3_ML/
│
├── Unsupervised_Learning.ipynb        # Notebook Jupyter 
└── requirements.txt            # Dépendances du projet
```

## 🚀 Installation

### 1. Créer un environnement virtuel (recommandé)
```bash
python -m venv venv
source venv/bin/activate  # Sur Windows: venv\Scripts\activate
```

### 2. Installer les dépendances
```bash
pip install -r requirements.txt
```

## 💻 Utilisation

### Lancer le notebook Jupyter
```bash
jupyter notebook Unsupervised_Learning.ipynb
```

### Exemple de code rapide
```python
# Charger le dataset
from sklearn import datasets
digits = datasets.load_digits()

# CAH
from scipy.cluster.hierarchy import linkage, dendrogram, fcluster
matrice_liens = linkage(digits.data, method='ward')

# K-means
from sklearn.cluster import KMeans
kmeans = KMeans(n_clusters=10, random_state=42)
clusters = kmeans.fit_predict(digits.data)
```

## 📈 Résultats attendus

- **Dendrogramme** illustrant la structure hiérarchique des chiffres
- **Matrices de confusion** comparant les deux méthodes
- **Visualisations** des clusters formés
- **Analyse** des similitudes visuelles entre chiffres regroupés

## 🔍 Points clés d'analyse

- Identification du nombre optimal de clusters via le dendrogramme
- Comparaison des performances CAH vs K-means
- Observation des concordances/divergences entre les deux approches
- Interprétation des regroupements basés sur les similarités visuelles

## 📊 Guide d'interprétation des résultats

### Interprétation du clustering CAH
Points à analyser :
- **Groupements formés** : Quels chiffres sont regroupés ensemble ?
- **Similitudes visuelles** : Identifier les formes, courbes et caractéristiques communes
- **Confusions courantes** : Expliquer pourquoi certains chiffres sont confondus
  - Exemple : 1 et 7 (traits verticaux)
  - Exemple : 3 et 8 (courbes similaires)
  - Exemple : 4 et 9 (structures proches)
- **Structure hiérarchique** : Observer l'ordre de fusion dans le dendrogramme

### Comparaison CAH vs K-means
Points à analyser dans les matrices de confusion :
- **Concordances** : Où les deux méthodes attribuent les mêmes clusters
- **Divergences** : Différences significatives entre les deux approches
- **Performance par chiffre** : Quelle méthode performe mieux pour certains chiffres spécifiques
- **Stabilité** : Cohérence des regroupements entre les deux méthodes
- **Avantages/Inconvénients** :
  - CAH : Structure hiérarchique claire, interprétable
  - K-means : Plus rapide, sensible à l'initialisation

## 📚 Concepts théoriques

### CAH (Hierarchical Clustering)
- Approche **bottom-up** : chaque élément commence comme cluster individuel
- Fusion progressive basée sur la **distance euclidienne**
- Représentation via **dendrogramme**
- Méthode Ward pour minimiser la variance intra-cluster

### K-means
- Partitionnement en **K clusters prédéfinis**
- Initialisation de K centres (centroids)
- Assignation itérative + réajustement des centres
- Convergence jusqu'à stabilisation

## 📄 Livrables

- Code Python complet et commenté
- Visualisations (dendrogrammes, matrices de confusion)
- Interprétations des résultats
- Analyse comparative des deux méthodes

## 👨‍🎓 Auteur

**Réalisé par :** Hsan Khecharem

**Filière :** Licence en Sciences de l'Informatique  
**Spécialité :** Génie Logiciel et Systèmes d'Information  
**Faculté :** Faculté des Sciences de Sfax

- Email : khecharemhsan@gmail.com

---

*Pour toute question concernant ce TP, n'hésitez pas à consulter la documentation de scikit-learn et scipy.*
