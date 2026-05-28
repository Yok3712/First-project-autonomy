# Filtre de Kalman 1D

Mon premier projet d'estimation d'état, réalisé pour me préparer à un master
en technologie autonome. Le filtre de Kalman reconstruit la vraie valeur d'une
grandeur (ici une position) à partir de mesures de capteur bruitées.

## Le problème

Les capteurs d'un robot ou d'un véhicule autonome (GPS, accéléromètre, LiDAR...)
ne donnent jamais une valeur exacte : chaque mesure contient une erreur aléatoire.
Comment retrouver la vraie valeur à partir de ces mesures imparfaites ?

## La solution

Le filtre de Kalman combine, à chaque pas de temps :
- une **prédiction** (ce qu'on croyait savoir),
- une **correction** par la nouvelle mesure.

Le **gain de Kalman** arbitre entre les deux : faut-il faire plus confiance à la
mesure ou à la prédiction ? C'est le cœur de l'algorithme.

## Résultat

Le graphique montre :
- en rouge, les mesures bruitées du capteur (dispersées),
- en bleu, l'estimation du filtre (lissée, qui converge vers la vérité),
- en vert pointillé, la vraie valeur (50).

L'estimation bleue part d'une valeur ignorante (0), apprend rapidement, puis se
stabilise autour de la vraie valeur — bien plus stable que les mesures brutes.

## Comment le lancer

Ouvre le notebook dans Google Colab (aucune installation requise) :

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/TON_PSEUDO/premier-projet-autonomie/blob/main/filtre_kalman_1d.ipynb)

Puis exécute les cellules de haut en bas.

## Technologies

- Python
- NumPy (calcul numérique)
- Matplotlib (visualisation)

## Limites et suite

Version 1D simplifiée (une seule variable, modèle de prédiction minimal). La suite
naturelle : étendre à 2D (position + vitesse) avec une formulation matricielle.
