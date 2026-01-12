# Lab 6 : Déploiement K8s d’un système MLOps Churn

Ce lab démontre le déploiement d'une application MLOps complète sur Kubernetes :
- Conteneurisation avec Docker
- Déploiement Kubernetes avec manifests
- Gestion de configuration avec ConfigMaps et Secrets
- Health checks et probes
- Volumes persistants
- NetworkPolicy


## Étape 1 : Préparer l'environnement Kubernetes
<img width="921" height="290" alt="etape 1" src="https://github.com/user-attachments/assets/085d9b5b-2186-4410-8dd6-24aa072840a9" />


## Étape 2 : Préparer l'image Docker de l'API churn

Vérifier que le Dockerfile est correctement configuré pour l'API FastAPI.

<img width="1371" height="240" alt="etape 2" src="https://github.com/user-attachments/assets/d1d22738-0e84-4f32-9d66-5d69a37c412b" />

## Étape 3 : Créer le dossier des manifests Kubernetes

<img width="1078" height="917" alt="etape 3" src="https://github.com/user-attachments/assets/58f4db97-2891-42fc-aab7-1647d20a5331" />

## Étape 4 : Construire l'image Docker (tag versionné)

<img width="1092" height="931" alt="etape 4" src="https://github.com/user-attachments/assets/2c98c8db-e3bc-4005-883b-cf5172c2563a" />

## Étape 5 : Charger explicitement l'image dans Minikube

Rendre l'image Docker disponible dans le cluster Minikube.

<img width="947" height="488" alt="etape 5" src="https://github.com/user-attachments/assets/9d157e55-c5f3-406a-8d92-6f73b9c71b02" />

## Étape 6 : Deployment Kubernetes pour l'API churn

Créer et déployer le manifest Deployment pour l'API.

<img width="955" height="377" alt="etape 6" src="https://github.com/user-attachments/assets/2fc1dbbe-cd7e-4519-9f63-a4f9d1309149" />

## Étape 7 : Exposer l'API via un Service NodePort

Créer un Service Kubernetes pour exposer l'API à l'extérieur du cluster.

<img width="952" height="818" alt="etape 7" src="https://github.com/user-attachments/assets/c251ba45-5846-4028-abab-009d32e4d65a" />

test sur Postman : 
<img width="1055" height="982" alt="etape 7 - postman" src="https://github.com/user-attachments/assets/8641df78-6fa5-4cac-bed0-1604f515fdef" />

## Étape 8 : Injecter la configuration MLOps via ConfigMap

Gérer la configuration de l'application via ConfigMap Kubernetes.

<img width="1196" height="832" alt="etape 8" src="https://github.com/user-attachments/assets/fa772dd5-1483-4898-b347-7b7a086f9b5d" />

## Étape 9 : Gérer les secrets (MONITORING_TOKEN)

Sécuriser les informations sensibles avec Kubernetes Secrets.
- Création du fichier `secret.yaml`
- Encodage des secrets en base64
- Injection sécurisée dans les pods

<img width="986" height="842" alt="etape 9" src="https://github.com/user-attachments/assets/cf290fe3-d9ea-49fc-8cba-7eecad0ac27d" />

## Étape 10 : Mise en place des endpoints de santé et des probes Kubernetes pour l'API Churn

Ajouter des endpoints de santé à l'API FastAPI pour les health checks Kubernetes.

<img width="1030" height="620" alt="etape 10" src="https://github.com/user-attachments/assets/6d8ec8c9-503b-4abe-a65a-3a10b6ab7d39" />

## Étape 11 : Ajouter les probes (liveness / readiness / startup)

Configurer les probes Kubernetes pour la gestion automatique de la santé des pods.

<img width="1002" height="508" alt="etape 11" src="https://github.com/user-attachments/assets/7013df49-3d4a-4843-aa7d-7252340df4bd" />

## Étape 12 : Volume persistant pour registry + logs

Configurer un volume persistant pour stocker les logs et le registry des modèles.

<img width="1005" height="905" alt="etape 12" src="https://github.com/user-attachments/assets/e7a3a4f7-692f-49b1-af8a-499ee5c8c25c" />

## Étape 13 : NetworkPolicy

Sécuriser le réseau en limitant les communications entre les pods.

<img width="1002" height="378" alt="etape 13" src="https://github.com/user-attachments/assets/3e1831e8-8773-49da-bebb-b3c6a0bb7741" />

## Étape 14 : Vérifications finales

Valider le déploiement complet et tester l'API en production.

health : 

<img width="717" height="677" alt="etape 14 - health" src="https://github.com/user-attachments/assets/043a2a49-d896-4aa4-9c50-d3e663b0dd2c" />

predict : 

<img width="775" height="838" alt="etape 14 - predict" src="https://github.com/user-attachments/assets/66580df4-a9e3-4a86-9d4e-34b5d14f36c6" />

finalement : 

<img width="1006" height="718" alt="etape 14" src="https://github.com/user-attachments/assets/675fad6a-8304-47c0-b713-9b66008b7ea9" />


## Architecture finale

<img width="356" height="393" alt="image" src="https://github.com/user-attachments/assets/1b5f1fbe-9f24-4823-8003-756cb21aa51b" />

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
