## 2.3 - INTEGRATION CONTINUE (CI)

### COMPETENCE(S) CONCERNEE(S) DANS LE REFERENTIEL

C3. Automatiser les phases de tests unitaires et d’analyses statiques du code source lors du partage des sources à l’aide d’un outil d’intégration continue de manière à prévenir les erreurs potentielles
- Configurer l’intégration continue, avec Github Actions ou Gitlab CI/CD
- Paramétrer les phases d'exécution des tests dans l’environnement de test à chaque push (sur la branche concernée)


### OBJECTIF PRINCIPAL DE CETTE PHASE DU PROJET



### REFLEXION ET APPLICATION D'UNE STRATEGIE DANS MON PROJET

#### DOCKERISATION

##### AVANTAGES
> intérets de la dockerisation (...)

Une image contient tout le code nécessaire pour son déploiement en conteneur (qui est une version spécifique d'une image déploiyée).

##### FICHIERS DE CONFIGURATION


Pour (...) , je n'ai eu besoin de ne dockeriser que le backend de l'application


Messages de Thomas :
- Parce qu'on a vercel de l'autre côté ^^ c'est plus facile. Et ça n'existe pas pour le back ^^
[17:16]
- Oui pour utiliser le back par le front il faudra ajouter une variable d'environnement et la configurer dans vercel ^^
- Vercel gère bien le front mais pas le back. Avec next il sait le gérer avec des serverless functions mais nous on veut apprendre à faire notre back ^^



Voici les différentes étapes suivies, à commencer par l'ajout des fichiers de configuration suivants :

- Dockerfile (à la racine du projet) qui permet de lister les différentes scripts à lancer lors du build de l'image. Voici une capture d'écran du contenu de ce fichier :

> capture d'écran

- .dockerignore (à la racine du projet) qui permet d'ignorer certains dossiers ou fichiers lors du build du projet en image. Voici une capture d'écran du contenu de ce fichier :

> capture d'écran



##### Push sur Docker Desktop

Docker Desktop, c'est (...) 

Ouverture de DockerHub

Connaitre la version de Docker Desktop :
```bash
docker version
```

Connexion avec Docker Desktop :
```bash
docker login
```

Création d'une image dans Docker Desktop :
```bash
docker build -t image_backend_les_as_de_l_ux .
```

> capture d'écran de DockerHub


##### Push sur DockerHub

DockerHub permet de stocker les images de nos projets (c'est comme GitHub)


Build de l'image tagguée dans DockerHub :
```bash
docker build -t jeremyfelix777/image_backend_les_as_de_l_ux:tag_v1 .
```

Pousser l'image tagguée dans DockerHub :
```bash
docker push jeremyfelix777/image_backend_les_as_de_l_ux:tag_v1
```

Si on ne spécifie aucun tag, le tag par défaut sur DesktopHub est "latest".

> capture d'écran de Render


##### Mise en prod automatique avec Render

Render sert à mettre en production automatiquement les images qui sont stockées sur DockerHub (cela fonctionne de la même façon que Vercel qui met en ligne du code source déposé sur GitHub).


Selectionner "Web service", un nom de projet, un serveur (celui situé à Frankfurk est le plus proche parmi ceux disponibles) puis cliquer sur le bouton de déploiement.

Un lien est ensuite généré par Render pour accèder au projet dockerisé mis en ligne :

https://backend-les-as-de-l-ux.onrender.com

Ce lien doit ensuite être ajouté dans le .env du frontend pour permettre l'échange de données avec le backend.




##### Bonus pas si bonus ^^ Créer une CI pour automatiser la création et l'ajout de l'image docker sur DockerHub ("impossible" sans le tuto du cours)





#### INTEGRATION CONTINUE

Le fichier de configuration qui gère l'automatisation de l'intégration continue se génère automatiquement avec Playwright à chaque push sur la branche main ou develop :

![Fichier playwright.yml](../img/fichier_config_ci_frontend.png "Fichier playwright.yml")

> Décrire chaque étape qui s'execute dans ce fichier

