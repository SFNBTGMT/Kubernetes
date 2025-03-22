# Cluster Configuration

## Description
Ce dossier contient les fichiers nécessaires pour configurer un cluster Minikube multi-nœuds. Les configurations spécifiques pour chaque nœud sont incluses dans le sous-dossier `node-configurations`.

## Instructions
1. Initialiser Minikube  :
    - Utiliser le fichier `minikube-setup.yaml` pour initialiser le cluster Minikube.
2. Configurer les Nœuds :
    - Appliquer les configurations des nœuds en utilisant les fichiers YAML dans `node-configurations/`.

## Fichiers
- `minikube-setup.yaml` : Script pour initialiser Minikube.
- `node-configurations/` :
    - `frontend-node.yaml` : Configuration du nœud frontend.
    - `backend-node.yaml` : Configuration du nœud backend.
    - `devops-node.yaml` : Configuration du nœud DevOps.

##  executer Commandes
minikube start --nodes=3 
kubectl apply -f cluster-configuration/node-configurations/frontend-node.yaml
kubectl apply -f cluster-configuration/node-configurations/backend-node.yaml
kubectl apply -f cluster-configuration/node-configurations/devops-node.yaml
