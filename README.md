# Description du Projet

Ce projet est structuré en plusieurs dossiers pour gérer les déploiements, la surveillance, la sécurité, les tests de performance et la configuration des environnements dans un cluster Kubernetes.

---

## 1. **Déploiement des Applications**
- **Fichiers** : `values-dev.yaml`, `values-prod.yaml`, `values-test.yaml`, `deployment.yaml`, `pvc.yaml`, etc.
- **Instructions** :
  - Appliquer les fichiers YAML pour déployer les applications dans les environnements de développement, test et production.
  - Exemple : `kubectl apply -f deployment.yaml`.

---

## 2. **Surveillance et Monitoring**
- **Outils** : Prometheus et Grafana.
- **Fichiers** : `prometheus/config.yaml`, `prometheus/deployment.yaml`, `grafana/deployment.yaml`, etc.
- **Instructions** :
  - Déployer Prometheus et Grafana avec les fichiers fournis.
  - Accéder à Grafana via `kubectl port-forward`.
  - Exemple : `kubectl apply -f monitoring/prometheus/deployment.yaml`.

---

## 3. **Configuration de la Sécurité**
- **RBAC** : Définir des rôles et des RoleBindings pour chaque environnement.
- **Politiques de Réseau** : Appliquer des Network Policies pour restreindre le trafic.
- **Fichiers** : `rbac/dev-role.yaml`, `network-policies/dev-policy.yaml`, etc.
- **Instructions** :
  - Appliquer les fichiers RBAC et Network Policies.
  - Exemple : `kubectl apply -f security/rbac/dev-role.yaml`.

---

## 4. **Tests de Performance et Stress Testing**
- **Scénarios** : Définir des scénarios de test avec JMeter.
- **Résultats** : Récupérer et analyser les résultats des tests.
- **Fichiers** : `scenarios/scenario-1.yaml`, `results/dev-results.md`, etc.
- **Instructions** :
  - Appliquer les scénarios de test et récupérer les résultats.
  - Exemple : `kubectl apply -f stress-testing/scenarios/scenario-1.yaml`.

---

## 5. **Configuration des Environnements**
- **Namespaces** : Créer des namespaces pour chaque environnement.
- **Quotas et Limites** : Appliquer des quotas de ressources et des limites.
- **Fichiers** : `namespaces.yaml`, `resource-quotas/dev-quotas.yaml`, etc.
- **Instructions** :
  - Appliquer les fichiers de configuration pour les namespaces, quotas et limites.
  - Exemple : `kubectl apply -f environments/namespaces.yaml`.

---

## 6. **Orchestration avec Jenkins**
- **Pipelines CI/CD** : Configurer des pipelines pour les environnements de développement, test et production.
- **Fichiers** : `jenkins-deployment.yaml`, `pipelines/dev-pipeline.yaml`, etc.
- **Instructions** :
  - Déployer Jenkins et configurer les pipelines.
  - Exemple : `kubectl apply -f jenkins-deployment.yaml`.

---

## 7. **Cluster Configuration**
- **Minikube** : Configurer un cluster Minikube multi-nœuds.
- **Fichiers** : `minikube-setup.yaml`, `node-configurations/frontend-node.yaml`, etc.
- **Instructions** :
  - Initialiser Minikube et appliquer les configurations des nœuds.
  - Exemple : `minikube start --nodes=3`.

---

## Commandes Utiles
- **Vérifier les déploiements** : `kubectl get deployments -n <namespace>`.
- **Vérifier les pods** : `kubectl get pods -n <namespace>`.
- **Accéder à Grafana** : `kubectl port-forward -n monitoring-services svc/grafana 3000:3000`.

---
