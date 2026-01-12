# Projet MLOps - Pipeline de Prédiction de Churn Client

## Description du Projet

Ce projet implémente un workflow MLOps complet pour un système de prédiction de churn client. Il couvre l'ensemble du cycle de vie d'un projet de Machine Learning, depuis le développement initial jusqu'au déploiement en production, en passant par le versionnement des données, l'automatisation des pipelines et la conteneurisation.

Le projet a été développé dans le cadre du cours MLOps et démontre la maîtrise des principes fondamentaux de :
- Versionnement du code source avec Git
- Versionnement des données et des modèles avec DVC
- Automatisation des pipelines ML avec intégration continue
- Déploiement en production avec Docker
- Monitoring et gestion des versions de modèles


## Table des labs

1. [Lab 1 : Du notebook au mini-système production-ready](#lab-1--du-notebook-au-mini-système-production-ready)
2. [Lab 2 : Gestion du Code Source avec Git](#lab-2--gestion-du-code-source-avec-git)
3. [Lab 3 : Versionnement des Données et Pipelines ML avec DVC](#lab-3--versionnement-des-données-et-pipelines-ml-avec-dvc)
4. [Lab 4 : Pipeline CI/CD Complet](#lab-4--pipeline-cicd-complet)
5. [Lab 5 : Déploiement Conteneurisé](#lab-5--déploiement-conteneurisé)


## Lab 1 : Du notebook au mini-système production-ready

Ce lab établit les fondations du projet en transformant un notebook exploratoire en un système ML structuré et prêt pour la production.

- Étape 1 : Initialiser la structure du projet

- Étape 2 : Préparer l'environnement Python

- Étape 3 : Générer le dataset

- Étape 4 : Préparer les données + quality checks

- Étape 5 : Entraîner, versionner et valider le modèle

- Étape 6 : Inspecter la registry et le modèle courant

- Étape 7 : Créer une API /predict qui utilise le modèle courant

- Étape 8 : Détecter une dérive des données via les logs

- Étape 9 : Gérer les versions du modèle et revenir en arrière


## Lab 2 : Gestion du Code Source avec Git

Ce lab couvre les principes fondamentaux de Git, essentiels pour tout projet MLOps. L'objectif principal est de maîtriser le versionnement du code, la gestion des branches et la résolution de conflits.

- Étape 1 : Initialiser Git dans mlops-lab-01

- Étape 2 : Premier commit du projet MLOps

- Étape 3 : Observer une modification avec git diff

- Étape 4 : Créer une branche de fonctionnalité liée au lab

- Étape 5 : Fusionner la branche feature dans la branche principale

- Étape 6 : Créer un conflit de merge sur src/train.py

- Étape 7 : Utiliser git stash dans le contexte du lab

- Étape 8 : Tester git reset sur un fichier d'expérimentation

- Étape 9 : Annuler un commit avec git revert

- Étape 10 : Rebase d'une branche feature sur la branche principale


## Lab 3 : Versionnement des Données et Pipelines ML avec DVC

Ce lab introduit DVC pour versionner les données et les modèles, complémentant ainsi Git qui ne gère que le code source.

- Initialisation de DVC dans le projet
  
- Configuration du stockage distant pour les données
  
- Ajout des datasets et modèles au tracking DVC
  
- Création de pipelines reproductibles
  
- Gestion des versions de données et modèles



## Lab 4 : Pipeline CI/CD Complet

Ce lab met en place l'automatisation complète du workflow MLOps via GitHub Actions.

- Étape 1 : Créer le dépôt GitHub et connecter le remote

- Étape 2 : Définir les secrets GitHub

- Étape 3 : Créer le workflow CI/CD

- Étape 4 : Commit et push



## Lab 5 : Déploiement Conteneurisé

Ce lab couvre la conteneurisation de l'application avec Docker pour garantir la portabilité et la cohérence entre environnements.

- Étape 1 : Vérifier l'installation de Docker

- Étape 2 : Lancer un serveur Nginx dans un conteneur

- Étape 3 : Ouvrir un shell Linux isolé dans un conteneur

- Étape 4 : Comprendre la structure d'une commande docker run

- Étape 5 : Conteneuriser l'API churn du projet mlops-lab-01

- Étape 6 : Créer un fichier requirements.txt pour l'image Docker

- Étape 7 : Créer un Dockerfile pour l'API churn

- Étape 8 : Préparer un modèle actif avant de construire l'image

- Étape 9 : Construire l'image Docker du projet churn

- Étape 10 : Lancer l'API churn dans un conteneur

- Étape 11 : Vérifier les logs générés à l'intérieur du conteneur

- Étape 12 : Orchestration locale avec Docker Compose

- Étape 13 : Démarrer l'API via Docker Compose

- Étape 14 : Lancer les services en arrière-plan et observer les logs

- Étape 15 : Lier Docker Compose au reste du cours (Git + DVC)


## Architecture du Projet dans mon VScode


<img width="316" height="831" alt="image" src="https://github.com/user-attachments/assets/af05d7b8-c9b1-4e04-844d-e823e5fe7388" />


## Technologies Utilisées

- **Python 3.9+** : Langage de programmation principal
- **Scikit-learn** : Bibliothèque de Machine Learning
- **FastAPI** : Framework pour l'API REST
- **Git** : Versionnement du code source
- **DVC** : Versionnement des données et des modèles
- **Docker** : Conteneurisation et déploiement
- **Docker Compose** : Orchestration multi-conteneurs
- **GitHub Actions** : Automatisation CI/CD
- **Pandas/NumPy** : Manipulation et analyse de données


## Auteur

**Salma Lidame**  
AI Engineer - ENSA El Jadida


## Note sur les Bonnes Pratiques

Ce projet a été réalisé en appliquant rigoureusement les principes MLOps enseignés durant le cours, avec une attention particulière portée à :

- La compréhension approfondie des mécanismes de Git, notamment la gestion du cache et de l'index
- La séparation claire entre le versionnement du code (Git) et le versionnement des données (DVC)
- L'importance de nettoyer le cache Git avant d'initialiser DVC pour éviter tout conflit
- L'automatisation complète du workflow pour garantir la reproductibilité

Chaque lab a été complété en suivant méthodiquement les instructions, en comprenant les concepts sous-jacents plutôt qu'en appliquant mécaniquement des commandes, ce qui constitue l'essence même d'une démarche MLOps professionnelle.
