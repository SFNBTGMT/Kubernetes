## Surveillance, Monitoring et Reporting avec Prometheus et Grafana

## Description
Ce dossier contient les fichiers nécessaires pour déployer Prometheus et Grafana, et configurer les dashboards et alertes pour la surveillance des applications.

## Instructions
- Déployer Prometheus :
Utiliser les fichiers deployment.yaml, service.yaml, et config.yaml dans le dossier prometheus/ pour déployer Prometheus.
- Déployer Grafana :
Utiliser les fichiers deployment.yaml, service.yaml, et les fichiers dans dashboards/ dans le dossier grafana/ pour déployer Grafana et configurer les dashboards.

## Fichiers
prometheus/ 
`deployment.yaml` : Déploiement de Prometheus.
`service.yaml` : Service pour Prometheus.
`config.yaml` : Configuration de Prometheus.
grafana/ 
`deployment.yaml` : Déploiement de Grafana.
`service.yaml` : Service pour Grafana.
dashboards/`wordpress-dashboard.json` : Dashboard Grafana pour WordPress.

## executer commande
kubectl apply -f monitoring/prometheus/config.yaml
kubectl apply -f monitoring/prometheus/deployment.yaml
kubectl apply -f monitoring/prometheus/service.yaml
kubectl apply -f monitoring/prometheus/prometheus-alerts.yaml
kubectl apply -f monitoring/grafana/deployment.yaml
kubectl apply -f monitoring/grafana/service.yaml

kubectl get pods -n monitoring-services

kubectl get deployments -n monitoring-services
kubectl get services -n monitoring-services


## Port Forwarding :
# Utilisez le port forwarding pour accéder à Grafana depuis votre machine locale.

kubectl port-forward -n monitoring-services svc/grafana 3000:3000
# navigateur :
http://localhost:3000
