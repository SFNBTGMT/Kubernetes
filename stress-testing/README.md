# Tests de Performance et Stress Testing
## Description
Ce dossier contient les fichiers nécessaires pour définir et exécuter les scénarios de tests de performance et de stress, et analyser les résultats pour les environnements de développement, test et production.

## Instructions
- Définir les Scénarios de Test :
Utiliser les fichiers YAML dans scenarios/ pour définir les scénarios de tests de performance et de stress.
- Analyser les Résultats :
Consulter les fichiers dans results/ pour les résultats des tests pour chaque environnement.

## Fichiers
scenarios/
`scenario-1.yaml` : Scénario de test de performance 1.
`scenario-2.yaml` : Scénario de test de performance 2.
results/
`dev-results.md` : Résultats des tests de performance pour l'environnement de développement.
`test-results.md` : Résultats des tests de performance pour l'environnement de test.
`prod-results.md` : Résultats des tests de performance pour l'environnement de production.


## executer commande
kubectl apply -f stress-testing/scenarios/scenario-1.yaml
kubectl apply -f stress-testing/scenarios/scenario-2.yaml
kubectl apply -f stress-testing/jmeter-test-scripts.yaml
kubectl apply -f stress-testing/results-fetcher.yaml

# Surveiller les Jobs :
kubectl get jobs -n development
# Déployez le pod :
kubectl apply -f stress-testing/results-fetcher.yaml
# Récupérez les Résultats :
kubectl cp development/results-fetcher:/results/scenario-1.jtl ./results/scenario-1.jtl
kubectl cp development/results-fetcher:/results/scenario-2.jtl ./results/scenario-2.jtl
