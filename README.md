# Systeme-de-recommandation
Ce projet porte sur l'implémentation d'un système de recommandation en utilisant l'ensemble de données MovieLens 100K. L'objectif principal est de développer un modèle basé sur le filtrage collaboratif pour prédire les notes des utilisateurs sur des films et proposer des recommandations personnalisées.

## Ensemble de Données ##
Les données utilisées proviennent du site MovieLens, et contiennent :

- u1.base : Ensemble d'entraînement (notes de films).
- u1.test : Ensemble de test.
- u.user : Informations sur les utilisateurs (âge, sexe, profession, etc.).
- u.item : Informations sur les films (titre, genre, etc.).
- u.genre : Liste des genres disponibles.
- u.occupation : Liste des professions des utilisateurs.

Les données comportent (voir document u.info) :
- 100 000 notes allant de 1 à 5.
- 943 utilisateurs.
- 1 682 films.

## Méthodologie ##
	> Chargement et exploration des données :
Les fichiers de données ont été importés et convertis en structures exploitables (listes, dictionnaires).
Création d'une matrice utilisateur-item R, où chaque coefficient R[u,i] représente la note attribuée par l'utilisateur u à l'élément i.

	> Traitement des données manquantes :
La matrice R contient de nombreuses valeurs manquantes (zéros).
Pour y remédier 2 types de matrices ont été créées à partir d'un calcul de moyenne pour remplacer les valeurs manquantes :
- Matrice Rr : Moyenne par utilisateur (ligne).
- Matrice Rc : Moyenne par film (colonne).

	> Visualisation :
Visualisation des matrices Rr et Rc pour comprendre la distribution des données et valider les transformations.

	> Système de recommandation basé sur le filtrage collaboratif :
Méthode basée sur une matrice utilisateur-item.
Approche : Prédire les notes des utilisateurs sur des films non notés et recommander les films les mieux classés.
Utilisation de l'approximation de bas rang (SVD).

## Langages et outils utilisés ##
Python : manipulation et analyse des données.
Bibliothèques : csv (chargement des fichiers de données), numpy (calcul matriciel), matplotlib/pylab (visualisation des matrices).

## Résultats ##
Finalement, un système de recommandation basé sur le filtrage collaboratif a été implémenté, permettant :
- La prédiction des notes pour des films non notés.
- La génération de recommandations adaptées aux préférences des utilisateurs.




