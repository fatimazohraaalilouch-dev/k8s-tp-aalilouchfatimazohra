# TP 4 Kubernetes

Travail en monôme : Fatima Zohra Aalilouch, Génie Logiciel, ENSA Al Hoceima, 2026/2027.

Le compte rendu complet (captures et réponses aux questions) est dans [`compte-rendu/compte-rendu.md`](compte-rendu/compte-rendu.md).

| Fichier | Contenu |
|---|---|
| `kind-config.yaml` | Cluster kind : 1 control-plane + 2 workers, port 30080 ouvert |
| `pod.yaml` | Pod `web` (nginx:1.27) en déclaratif |
| `whoami.yaml` | Deployment (3 réplicas) et Service NodePort 30080 |
| `rollout-history.txt` | Sortie de `kubectl rollout history deployment/whoami` |
| `compte-rendu/` | Compte rendu |
| `captures/` | Captures d'écran par partie |
