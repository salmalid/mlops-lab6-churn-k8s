# Lab 6 : Déploiement K8s d’un système MLOps Churn

Ce lab démontre le déploiement d'une application MLOps complète sur Kubernetes :
- Conteneurisation avec Docker
- Déploiement Kubernetes avec manifests
- Gestion de configuration avec ConfigMaps et Secrets
- Health checks et probes
- Volumes persistants
- NetworkPolicy


## Étape 1 : Préparer l'environnement Kubernetes
![alt text](<etape 1.png>)

## Étape 2 : Préparer l'image Docker de l'API churn

Vérifier que le Dockerfile est correctement configuré pour l'API FastAPI.

![alt text](<etape 2.png>)

## Étape 3 : Créer le dossier des manifests Kubernetes

![alt text](<etape 3.png>)

## Étape 4 : Construire l'image Docker (tag versionné)

![alt text](<etape 4.png>)

## Étape 5 : Charger explicitement l'image dans Minikube

Rendre l'image Docker disponible dans le cluster Minikube.

![alt text](<etape 5.png>)

## Étape 6 : Deployment Kubernetes pour l'API churn

Créer et déployer le manifest Deployment pour l'API.

![alt text](<etape 6.png>)

## Étape 7 : Exposer l'API via un Service NodePort

Créer un Service Kubernetes pour exposer l'API à l'extérieur du cluster.

![alt text](<etape 7.png>)

test sur Postman : 
![alt text](<etape 7 - postman.png>)

## Étape 8 : Injecter la configuration MLOps via ConfigMap

Gérer la configuration de l'application via ConfigMap Kubernetes.

![alt text](<etape 8.png>)

## Étape 9 : Gérer les secrets (MONITORING_TOKEN)

Sécuriser les informations sensibles avec Kubernetes Secrets.
- Création du fichier `secret.yaml`
- Encodage des secrets en base64
- Injection sécurisée dans les pods

![alt text](<etape 9.png>)

## Étape 10 : Mise en place des endpoints de santé et des probes Kubernetes pour l'API Churn

Ajouter des endpoints de santé à l'API FastAPI pour les health checks Kubernetes.

![alt text](<etape 10.png>)

## Étape 11 : Ajouter les probes (liveness / readiness / startup)

Configurer les probes Kubernetes pour la gestion automatique de la santé des pods.

![alt text](<etape 11.png>)

## Étape 12 : Volume persistant pour registry + logs

Configurer un volume persistant pour stocker les logs et le registry des modèles.

![alt text](<etape 12.png>)

## Étape 13 : NetworkPolicy

Sécuriser le réseau en limitant les communications entre les pods.

![alt text](<etape 13.png>)

## Étape 14 : Vérifications finales

Valider le déploiement complet et tester l'API en production.

health : 
![alt text](<etape 14 - health.png>)

predict : 
![alt text](<etape 14 - predict.png>)

finalement : 

![alt text](<etape 14.png>)


### Architecture finale
┌─────────────────────────────────────────┐
│         Minikube Cluster                │
│  ┌───────────────────────────────────┐  │
│  │  churn-api-service (NodePort)     │  │
│  │  Port: 30080                      │  │ 
│  └─────────────┬─────────────────────┘  │
│  ┌─────────────▼─────────────────────┐  │
│  │  churn-api Deployment             │  │
│  │  Replicas: 2                      │  │
│  │  ┌─────────┐    ┌─────────┐       │  │
│  │  │ Pod 1   │    │ Pod 2   │       │  │
│  │  └─────────┘    └─────────┘       │  │
│  └───────────────────────────────────┘  │
│  ┌───────────────────────────────────┐  │
│  │  ConfigMap + Secret + PVC         │  │
│  └───────────────────────────────────┘  │
└─────────────────────────────────────────┘

## Technologies Utilisées

- **Python 3.12** : Langage de programmation principal
- **FastAPI** : Framework pour l'API REST
- **Docker** : Conteneurisation de l'application
- **Kubernetes** : Orchestration de conteneurs
- **Minikube** : Cluster Kubernetes local
- **kubectl** : CLI pour gérer Kubernetes
- **Scikit-learn** : Bibliothèque de Machine Learning
- **DVC** : Versionnement des données et modèles


## Auteur

**Salma Lidame**  
AI Engineer - ENSA El Jadida
Cours : MLOps