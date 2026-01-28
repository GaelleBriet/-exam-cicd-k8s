# Partie 1 – Conteneurisation & CI/CD (20 pts)
## Partie 1.1 (10 pts)
### Travail demandé
**Créer un Dockerfile permettant :**

    Build reproductible
    Image légère
    Lancement de l’API via variable d’environnement APP_PORT

**Contraintes**

    Interdiction de l’image latest
    L’application doit écouter sur 0.0.0.0

**Livrables**

    Dockerfile

Build l'image docker :
```bash
docker build -t simple-api .
```
Lancer le conteneur :
```bash
docker run -e APP_PORT=3000 -p 3001:3000 simple-api
```

----

## Partie 1.2 – CI/CD (10 pts)

### Travail demandé
**Créer un pipeline avec au minimum :**

Build : Build & tests (fourni)
Push : Push de l'image sur Dockerhub
Health : Test automatique du endpoint /health

**Contraintes**

    Pipeline bloquant en cas d’échec
    Tag d’image basé sur le commit (sha ou tag)

**Livrables**
.gitlab-ci.yml ou workflow GitHub Actions


----

## Partie 2 – Kubernetes (20 pts)

### Travail demandé
**Déployer l’application sur Kubernetes avec :**

    Deployment
    Service
    ConfigMap
    LivenessProbe
    ReadinessProbe

**Contraintes**

    2 réplicas minimum
    Rolling update sans interruption
    Fichiers séparés

**Livrables**

k8s/
├── deployment.yaml
├── service.yaml
└── configmap.yaml

**Causes d’échec automatique**

    Pipeline non bloquant
    Absence des probes dans kubernetes (LivenessProbe, ReadinessProbe)
    L'application ne se deploie pas

---

**Rendu final**

Dossier de projet au format nom-prenom.zip contenant :

    Projet (SUPPRIMER LE DOSSIER node_modules !!)
    Fichiers kubernetes
    README :
        Architecture
        Choix techniques
        Commandes clés
