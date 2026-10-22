# Classification des vins par cépage

Défi de classification multiclasse (module Machine Learning).
Objectif : classer des vins selon leur cépage avec un **recall global > 0,95**.

## Données
- 178 échantillons, 13 variables chimiques (alcool, proline, flavonoïdes, etc.)
- Label `WineVariety` : 3 classes (0 : 59, 1 : 71, 2 : 48 échantillons)
- Source : UCI Machine Learning Repository (Forina et al.)

## Démarche
1. Exploration des données (dimensions, colonnes, répartition des classes)
2. Découpage 70 % entraînement / 30 % test (stratifié)
3. Standardisation des variables (`StandardScaler`), car les échelles sont très différentes (ex. proline ~1000)
4. Modèle : régression logistique (gère le multiclasse)
5. Évaluation : rapport de classification, matrice de confusion, recall
6. Validation croisée à 5 plis pour confirmer la stabilité
7. Sauvegarde du modèle (`joblib`) et prédiction sur 2 nouveaux échantillons

## Résultats
- Recall global sur le jeu de test : **1,0** (aucune erreur sur 54 échantillons)
- Validation croisée (5 plis) : scores entre 0,97 et 1,0, **moyenne 0,985**
- Prédictions sur les nouveaux échantillons : variété 0 (A) et variété 1 (B)

## Limites
- Jeu de données petit et plutôt facile à séparer : le score parfait est à interpréter avec prudence.

## Fichiers
- `Wine Classification Challenge.ipynb` : notebook complet
- `wine.csv` : données

## Auteurs
Ben Trad Roudeina & Abdellatif Oumaima