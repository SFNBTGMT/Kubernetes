## Configuration de la Sécurité et des Accès
## Description
Ce dossier contient les fichiers nécessaires pour définir et appliquer les rôles RBAC et les politiques de réseau pour les environnements de développement, test et production.

## Instructions
- Définir les Rôles RBAC :
Utiliser les fichiers YAML dans rbac/ pour définir les rôles pour chaque environnement.
- Appliquer les Politiques de Réseau :
Utiliser les fichiers YAML dans network-policies/ pour appliquer les politiques de réseau pour chaque environnement.

## Tâches

### Configuration de RBAC

- **Namespace `Development` :**
  - **Role** : `dev-role` avec accès complet aux ressources de développement.
  - **RoleBinding** : Lier `dev-role` aux utilisateurs du groupe de développement.

- **Namespace `Testing` :**
  - **Role** : `test-role` avec accès limité aux actions de test.
  - **RoleBinding** : Lier `test-role` aux utilisateurs du groupe de test.

- **Namespace `Production` :**
  - **Role** : `prod-role` avec accès restreint aux actions critiques en production.
  - **RoleBinding** : Lier `prod-role` aux utilisateurs du groupe de production.

### Définition des Network Policies

- **Namespace `Development` :**
  - Autoriser uniquement le trafic interne entre les pods de développement.

- **Namespace `Testing` :**
  - Restreindre le trafic à des IPs spécifiques et autoriser uniquement le trafic interne.

- **Namespace `Production` :**
  - Restreindre le trafic à des services spécifiques et interdire les communications non sécurisées.

## Fichiers
rbac/
`dev-role.yaml` : Rôle RBAC pour l'environnement de développement.
`test-role.yaml` : Rôle RBAC pour l'environnement de test.
`prod-role.yaml` : Rôle RBAC pour l'environnement de production.
network-policies/
`dev-policy.yaml` : Politique de réseau pour l'environnement de développement.
`test-policy.yaml` : Politique de réseau pour l'environnement de test.
`prod-policy.yaml` : Politique de réseau pour l'environnement de production.

## executer commande
# Créer les namespaces
kubectl create namespace development
kubectl create namespace testing
kubectl create namespace production
# Appliquer les configurations RBAC
kubectl apply -f security/rbac/dev-role.yaml
kubectl apply -f security/rbac/test-role.yaml
kubectl apply -f security/rbac/prod-role.yaml
# Appliquer les Network Policies
kubectl apply -f security/network-policies/dev-policy.yaml
kubectl apply -f security/network-policies/test-policy.yaml
kubectl apply -f security/network-policies/prod-policy.yaml
# Vérifier les rôles et les bindings
kubectl get roles --namespace=development
kubectl get rolebindings --namespace=development

kubectl get roles --namespace=testing
kubectl get rolebindings --namespace=testing

kubectl get roles --namespace=production
kubectl get rolebindings --namespace=production
# Vérifier les Network Policies
kubectl get networkpolicies --namespace=development

kubectl get networkpolicies --namespace=testing

kubectl get networkpolicies --namespace=production
