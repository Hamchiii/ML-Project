# Projet BrakTooth Attack Dataset

## 1. Présentation du Projet

Ce projet porte sur l'analyse et la détection d'attaques Bluetooth basées sur BrakTooth. L'objectif est de développer un modèle capable soit de distinguer entre trafic normal et trafic d'attaque, soit de classifier précisément le type d'attaque (parmi 11 types, dont "normal") en se basant sur le dataset fourni par le laboratoire de recherche ISOT. Le projet s’inscrit dans le cadre d’un travail de groupe de deux personnes.

## 2. Contenu et Livrables

Le rendu final comprendra :
- **Un Notebook Jupyter** (format `.ipynb`) contenant le code, l’analyse, les commentaires et l’interprétation à chaque étape (chargement des données, prétraitement, modélisation, etc.).  
  _Astuce : Veillez à fixer la seed pour assurer la reproductibilité des résultats._
- **Un fichier CSV** contenant les prédictions sur l’ensemble de test fourni.

## 3. Description du Dataset

Le dataset, issu du laboratoire ISOT, a été constitué à l’aide d’un dispositif d’écoute active (utilisant le framework InternalBlue et un Nexus 5) et comprend :
- **Trafic normal** : échanges multimédias (documents, vidéo, audio) entre plusieurs dispositifs.
- **Trafic d'attaque** : différentes attaques BrakTooth ciblant les couches LMP et baseband.
  
Les principales caractéristiques des paquets dans le dataset sont les suivantes :
- **Protocol** : Indique le protocole utilisé (L2CAP, OBEX, SDP, RFCOMM, etc.).
- **Info** : Informations supplémentaires sur le paquet en fonction du protocole.
- **Length** : Longueur du paquet en octets.
- **Delta** : Différence de temps entre le paquet actuel et le précédent.
- **Type** : Étiquette manuelle indiquant s’il s’agit d’un trafic normal ou d’un type d’attaque particulier.

Quelques statistiques importantes tirées du dataset :
- **Nombre de paquets normaux** : 6269
- **Nombre de paquets pour chaque type d’attaque** (exemple) : AU Rand Flooding (655), Duplicated IOCAP (299), Truncated SCO Link Request (340), etc.

_Consultez le document “ISOT-BrakTooth-BrakTooth-Dataset.pdf” pour plus de détails sur la structure et la distribution du dataset._ :contentReference[oaicite:0]{index=0}&#8203;:contentReference[oaicite:1]{index=1}

## 4. Objectifs et Choix de la Tâche

Vous devez choisir entre deux approches pour le projet :
1. **Détection d’attaque** : Classer les paquets comme « attaque » ou « normal ».
2. **Classification multi-classe** : Identifier précisément le type d’attaque parmi les 11 types possibles (incluant l’état « normal »).

Il est important de préciser dans le notebook l’objectif retenu et de justifier ce choix.

## 5. Méthodologie et Étapes Clés

### 5.1. Analyse Préliminaire et Visualisation des Données
- **Exploration des données** : Création d’histogrammes, boxplots, heatmaps, et scatterplots pour comprendre la distribution des variables.
- **Nettoyage** : Suppression des doublons, gestion des valeurs manquantes et identification des variables non informatives.

### 5.2. Ingénierie des Variables
- **Transformation** : Conversion de variables catégorielles en numériques (par exemple via one-hot encoding).
- **Standardisation** : Normalisation des variables quantitatives (exemple : StandardScaler).
- **Création de descripteurs** : Combinaison ou transformation de variables existantes (somme, racine carrée, etc.) afin de mieux capturer l’information.

### 5.3. Sélection des Algorithmes
- Test de plusieurs modèles allant des méthodes simples aux méthodes plus complexes.
- Application du principe d’Occam’s razor : privilégier un modèle simple avec de bonnes performances plutôt qu’un modèle complexe et coûteux en temps de calcul, surtout si l’amélioration de la précision est marginale.

### 5.4. Évaluation et Sélection du Modèle
- **Métriques de performance** : Calcul de la précision, évaluation à l’aide d’une matrice de confusion, et vérification de la robustesse (éviter le sur-apprentissage).
- **Analyse des temps de calcul et de la consommation mémoire** : Comparaison entre différents modèles pour trouver le meilleur compromis entre performance et complexité.

_Se référer au document “project.pdf” pour plus de détails sur les instructions et critères de notation._ :contentReference[oaicite:2]{index=2}&#8203;:contentReference[oaicite:3]{index=3}

## 6. Considérations Supplémentaires

- **Documentation** : Un code bien commenté et une documentation claire sont essentiels pour expliquer le fonctionnement des fonctions et la logique derrière les choix méthodologiques.
- **Interprétation des résultats** : Même en cas de résultats négatifs, il est important d’apporter des explications et des analyses sur les performances obtenues.

## 7. Ressources et Références

- **Dataset** : ISOT BrakTooth Attack Dataset (voir le readme du dataset pour les détails sur les variables et la distribution des données).
- **Articles et conférences** : Pour citer ce dataset, utilisez la référence suivante :
  - Nandikotkur, Achyuth; Traore, Issa; Mamun, Mohammad. *Detecting BrakTooth Attacks*. In: Secrypt 2023, 20th International Conference on Security and Cryptography, 10-12 July 2023, Rome, Italy.
- **Liens utiles** :
  - [ISOT Datasets - University of Victoria](https://onlineacademiccommunity.uvic.ca/isot/2023/05/30/iot-security-datasets/)

---
