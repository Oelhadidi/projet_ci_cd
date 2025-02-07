# Projet CI/CD

## Équipe
- OMAR ELHADIDI -  CI
- BOUTAGJAT BRAHIM -  CD




### Organisation des Branches et Pull Requests
- Développement sur branches features
- Pull Request obligatoire pour tout merge vers main
- Revue de code avec approbation requise
- La branche main ne contient que des commits de merge de PR

## Intégration Continue (CI)

Le CI se déclenche automatiquement sur chaque Pull Request avec les étapes suivantes :

1. Checkout du code
2. Configuration de l'environnement Docker
3. Lint du Dockerfile avec Hadolint
4. Build et démarrage des containers Docker
5. Vérification des logs MySQL et status des containers
6. Exécution des tests avec npm test
7. Nettoyage des containers

Le CI :
- Bloque automatiquement les PR contenant des erreurs
- Autorise les PR sans problème
- S'exécute sur ubuntu-latest

## Déploiement Continu (CD)

### Sur la branche main
Le CD se déclenche automatiquement après un CI réussi sur main :
1. Login sur Docker Hub
2. Build de l'image Docker
3. Push vers Docker Hub avec tag `latest`

### Sur création de tag (Livraison Continue)
Lors de la création d'un tag (format v*) :
1. Déclenchement automatique du workflow
2. Build et push de l'image Docker avec le tag correspondant
3. Création automatique d'une release GitHub avec :
   - Notes de release générées automatiquement
   - Tag correspondant à la version
   - Description standardisée

## Livrables

### Images Docker
- Latest : `elhadido/my-app:latest`
- Versions taguées : `elhadido/my-app:vX.Y.Z`
- Disponible sur : https://hub.docker.com/r/elhadido/my-app/tags



## Guide de Déploiement 

### Prérequis
- Docker et Docker Compose installés
- Accès au Docker Hub


### Lien vers dockerhub tags
- https://hub.docker.com/r/elhadido/my-app/tags



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


## Retour d'Expérience

Ce projet a été une vraie aventure ! Au début, on doit avouer qu'on était un peu perdus avec les Pull Requests,
ce qui explique notre nombre impressionnant de commits. On avait tendance à tout pousser directement sans trop réfléchir... 
Mais petit à petit, en relisant les consignes et en repensant à ce qu'on avait vu en cours, on a commencé à mieux comprendre la logique.

C'était super intéressant de mettre en place toute la chaîne CI/CD par nous-mêmes. 
Ça nous a permis de vraiment comprendre ce qu'on avait vu en cours, mais cette fois en mode "real life" ! 
On a dû se débrouiller seuls face aux problèmes, chercher des solutions, et au final, on est plutôt fiers du résultat.

- L'importance d'une bonne organisation avec Git
- Comment structurer vraiment un workflow CI/CD 
- La satisfaction de voir tout fonctionner automatiquement une fois que c'est bien configuré

Même si le début était un peu chaotique, on a fini par trouver notre rythme et produire quelque chose qui tient la route. 
 


