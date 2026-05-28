# Filtre de Kalman 1D

Mon premier projet d'estimation d'état, réalisé pour me préparer à un master
en systèmes autonomes. Le filtre de Kalman reconstruit la vraie valeur d'une
grandeur (ici une position) à partir de mesures de capteur bruitées.

## Le problème

Les capteurs d'un robot ou d'un véhicule autonome (GPS, accéléromètre, LiDAR...)
ne donnent jamais une valeur exacte : chaque mesure contient une erreur aléatoire.
Comment retrouver la vraie valeur à partir de ces mesures imparfaites ?

## La solution

À chaque pas de temps, le filtre combine :
- une **prédiction** (ce qu'on croyait savoir),
- une **correction** par la nouvelle mesure.

Le **gain de Kalman** arbitre entre les deux. C'est le cœur de l'algorithme.

## Résultat

Le graphique montre les mesures bruitées (rouge), l'estimation lissée du filtre
(bleu) qui converge vers la vraie valeur (vert pointillé, 50).

## Comment le lancer

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Yok3712/First-project-autonomy/blob/main/Filtre_Kalman.ipynb)

## Technologies

- Python, NumPy, Matplotlib

## Limites et suite

Version 1D simplifiée. Suite : étendre à 2D (position + vitesse) en formulation matricielle.
