# Description du Projet

Ce projet est structuré en plusieurs dossiers pour gérer les déploiements, la surveillance, la sécurité, les tests de performance et la configuration des environnements dans un cluster Kubernetes.

---

## 1. **Déploiement des Applications**
- **Fichiers** : `values-dev.yaml`, `values-prod.yaml`, `values-test.yaml`, `deployment.yaml`, `pvc.yaml`, etc.
- **Instructions** :
  - Appliquer les fichiers YAML pour déployer les applications dans les environnements de développement, test et production.
  - Exemple : `kubectl apply -f deployment.yaml`.

![Image](https://github.com/user-attachments/assets/7b387319-cd18-484a-8933-43dacd1f167b)
---

## 2. **Surveillance et Monitoring**
- **Outils** : Prometheus et Grafana.
- **Fichiers** : `prometheus/config.yaml`, `prometheus/deployment.yaml`, `grafana/deployment.yaml`, etc.
- **Instructions** :
  - Déployer Prometheus et Grafana avec les fichiers fournis.
  - Accéder à Grafana via `kubectl port-forward`.
  - Exemple : `kubectl apply -f monitoring/prometheus/deployment.yaml`.

![Image](https://github.com/user-attachments/assets/c4e3af36-6b5b-4027-8ce1-5411418fe93d)
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

![image](https://github.com/user-attachments/assets/3ff64b70-ca11-44f8-a75f-86fb07789678)
![Image](https://github.com/user-attachments/assets/5232ec6c-5df4-431b-b50b-55f16cc7f5d4)

---

## 7. **Cluster Configuration**
- **Minikube** : Configurer un cluster Minikube multi-nœuds.
- **Fichiers** : `minikube-setup.yaml`, `node-configurations/frontend-node.yaml`, etc.
- **Instructions** :
  - Initialiser Minikube et appliquer les configurations des nœuds.
  - Exemple : `minikube start --nodes=3`.

![Image](https://github.com/user-attachments/assets/a032d44d-6040-4b40-9d99-619910d7cfaa)
---

## Commandes Utiles
- **Vérifier les déploiements** : `kubectl get deployments -n <namespace>`.
- **Vérifier les pods** : `kubectl get pods -n <namespace>`.
- **Accéder à Grafana** : `kubectl port-forward -n monitoring-services svc/grafana 3000:3000`.

---
