# **Système de Recommandation**

Ce projet porte sur l'implémentation d'un système de recommandation en utilisant l'ensemble de données **MovieLens 100K**.  
L'objectif principal est de développer un modèle basé sur le **filtrage collaboratif** pour prédire les notes des utilisateurs sur des films et proposer des recommandations personnalisées.

---

## **Ensemble de Données**

Les données utilisées proviennent du site [MovieLens](https://grouplens.org/datasets/movielens/100k/). Elles contiennent :

- `u1.base` : Ensemble d'entraînement (notes de films).
- `u1.test` : Ensemble de test.
- `u.user` : Informations sur les utilisateurs (âge, sexe, profession, etc.).
- `u.item` : Informations sur les films (titre, genre, etc.).
- `u.genre` : Liste des genres disponibles.
- `u.occupation` : Liste des professions des utilisateurs.

### **Statistiques principales** :
- **100 000** notes allant de 1 à 5.
- **943 utilisateurs**.
- **1 682 films**.

(Plus de détails dans le fichier `u.info`.)

---

## **Méthodologie**

### **1. Chargement et exploration des données :**
Les fichiers de données ont été importés et convertis en structures exploitables (listes, dictionnaires).  
Création d'une matrice utilisateur-item \( R \), où chaque coefficient \( R[u,i] \) représente la note attribuée par l'utilisateur \( u \) à l'élément \( i \).

### **2. Traitement des données manquantes :**
La matrice \( R \) contient de nombreuses valeurs manquantes (zéros). Pour y remédier :
- **Matrice \( Rr \)** : Moyenne par utilisateur (ligne).
- **Matrice \( Rc \)** : Moyenne par film (colonne).

### **3. Visualisation :**
Les matrices \( Rr \) et \( Rc \) ont été visualisées pour observer la distribution des données et valider les transformations.

### **4. Filtrage Collaboratif :**
- Méthode basée sur la matrice utilisateur-item.
- Approche :
  - Prédiction des notes pour des films non notés.
  - Recommandation des films les mieux classés.
- Utilisation de l'approximation de **bas rang (SVD)** pour améliorer les performances.

---

## **Langages et Outils Utilisés**

- **Langage** : Python
- **Bibliothèques principales** :
  - `csv` : Chargement des fichiers de données.
  - `numpy` : Calcul matriciel.
  - `matplotlib`/`pylab` : Visualisation des matrices.

---

## **Résultats**

Un système de recommandation basé sur le **filtrage collaboratif** a été implémenté, permettant :
- La **prédiction** des notes pour des films non notés.
- La **génération de recommandations** adaptées aux préférences des utilisateurs.
