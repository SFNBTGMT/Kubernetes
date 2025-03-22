## Orchestration et Automatisation avec Jenkins

## Description
Ce dossier contient les fichiers nécessaires pour déployer Jenkins et configurer les pipelines CI/CD pour les environnements de développement, test et production.

## Instructions
- Déployer Jenkins :
Utiliser les fichiers jenkins-deployment.yaml et jenkins-service.yaml pour déployer Jenkins.
- Configurer les Pipelines :
Appliquer les fichiers YAML dans pipelines/ pour configurer les pipelines pour chaque environnement.

## Fichiers
`jenkins-deployment.yaml` : Déploiement de Jenkins.
`jenkins-service.yaml` : Service pour Jenkins.
pipelines/ :
`dev-pipeline.yaml` : Pipeline CI/CD pour l'environnement de développement.
`test-pipeline.yaml` : Pipeline CI/CD pour l'environnement de test.
`prod-pipeline.yaml` : Pipeline CI/CD pour l'environnement de production.

## executer commande

# Créer le namespace CI-CD :

kubectl create namespace ci-cd

kubectl apply -f jenkins-pvc.yaml -n ci-cd
kubectl apply -f jenkins-deployment.yaml -n ci-cd
kubectl apply -f jenkins-service.yaml -n ci-cd

# Configurer l'accès à Jenkins :
kubectl get pods -n ci-cd
kubectl get svc jenkins -n ci-cd
# lance server sur le navigateur : 
minikube service jenkins -n ci-cd --url
# pour trouver le mot de passe généré :
kubectl logs `jenkins-7f8fbbdfcd-gbbqk` -n ci-cd
