## Déploiement et Gestion des Applications

## Description

Ce dossier contient les fichiers nécessaires pour déployer et gérer les applications WordPress et MySQL, incluant les Persistent Volumes Claims (PVC).

## Instructions

- Déployer WordPress :
Utiliser les fichiers deployment.yaml, service.yaml, et pvc.yaml dans le dossier wordpress/ pour déployer l'application WordPress.
- Déployer MySQL :
Utiliser les fichiers deployment.yaml, service.yaml, et pvc.yaml dans le dossier mysql/ pour déployer la base de données MySQL.

## Fichiers

wordpress/ 
`deployment.yaml` : Déploiement de l'application WordPress.
`service.yaml` : Service pour l'application WordPress.
`pvc.yaml` : Persistent Volume Claim pour WordPress.
mysql/ 
`deployment.yaml` : Déploiement de la base de données MySQL.
`service.yaml` : Service pour MySQL.
`pvc.yaml` : Persistent Volume Claim pour MySQL.


## executer commande
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
# creer trois namespaces distincts :
kubectl create namespace development
kubectl create namespace testing
kubectl create namespace production

\applications\wordpress\helm
# Pour le développement
helm install wordpress-dev bitnami/wordpress -f values-dev.yaml --namespace development

# Pour le test
helm install wordpress-test bitnami/wordpress -f values-test.yaml --namespace testing

# Pour la production
helm install wordpress-prod bitnami/wordpress -f values-prod.yaml --namespace production
# verifier
kubectl get pods -n development
helm list --namespace development
