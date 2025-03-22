# environnement Configuration

## Description
Ce dossier contient les fichiers nécessaires pour configurer les namespaces, quotas de ressources et limites pour les environnements de développement, test et production.

## Instructions
- Configurer les Namespaces :
Utiliser le fichier namespaces.yaml pour créer les namespaces.
- Définir les Quotas de Ressources :
Appliquer les fichiers YAML dans resource-quotas/ pour définir les quotas pour  chaque environnement.
- Définir les Limites de Ressources :
Appliquer les fichiers YAML dans limit-ranges/ pour définir les limites pour chaque environnement.

## Fichiers
`namespaces.yaml` : Définition des namespaces.
resource-quotas/ 
`dev-quotas.yaml` : Quotas de ressources pour l'environnement de développement.
`test-quotas.yaml` : Quotas de ressources pour l'environnement de test.
`prod-quotas.yaml` : Quotas de ressources pour l'environnement de production.
limit-ranges/ 
`dev-limits.yaml` : Limites de ressources pour l'environnement de développement.
`test-limits.yaml` : Limites de ressources pour l'environnement de test.
`prod-limits.yaml` : Limites de ressources pour l'environnement de production.


## executer commande

kubectl apply -f environments/namespaces.yaml
kubectl apply -f environments/resource-quotas/dev-quotas.yaml
kubectl apply -f environments/resource-quotas/test-quotas.yaml
kubectl apply -f environments/resource-quotas/prod-quotas.yaml
kubectl apply -f environments/limit-ranges/dev-limits.yaml
kubectl apply -f environments/limit-ranges/test-limits.yaml
kubectl apply -f environments/limit-ranges/prod-limits.yaml
