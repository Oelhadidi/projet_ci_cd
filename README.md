# Projet CI/CD

## Équipe
- OMAR ELHADIDI -  CI
- BOUTAGJAT BRAHIM -  CD


## Étapes CI/CD

### CI (Pull Requests)
1. Checkout du code
2. Lint du Dockerfile avec Hadolint
3. Build des containers Docker
4. Vérification des logs et containers
5. Lancer un test

### CD (Déploiement Continu sur main)
1. Build de l'image Docker
2. Push sur Docker Hub
3. Déploiement automatique

### CD (Livraison Continue sur tags)
1. Création d'une release GitHub
2. Build et push de l'image Docker taguée
3. Documentation de release automatique

## Livrable
- Image Docker disponible sur Docker Hub
- Tags: `elhadido/my-app:latest` pour main
- Tags: `elhadido/my-app:vX.Y.Z` pour les releases

## Guide de Déploiement pour les Stagiaires

### Prérequis
- Docker et Docker Compose installés
- Accès au Docker Hub

### Procédure de Déploiement
1. Récupérer la dernière image :
```bash
docker pull elhadido/my-app:latest
```

2. Démarrer l'application :
```bash
docker compose up -d
```

### En cas de Problème
1. Vérifier les logs :
```bash
docker logs mon-app
```
.
=======
