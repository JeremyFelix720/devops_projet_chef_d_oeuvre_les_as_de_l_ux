## 2.1 - UTILISATION DE GIT ET GITHUB

### COMPETENCE(S) CONCERNEE(S) DANS LE REFERENTIEL

C1. Assurer le versionnement d’un code source d’une application organisée en fonctionnalités et lots à l’aide d’un logiciel de contrôle de version de manière à garantir la fiabilité du code source dans un environnement multi-contributeurs
- Les sources sont versionnées avec Git
- Git en ligne de commande
- Respect d’un gitflow
- Utilisation de Github ou Gitlab par exemple


### OBJECTIF PRINCIPAL DE CETTE PHASE DU PROJET

intéret de git / gitHub + gitflow + des branches +


#### UTILISATION DES BRANCHES

L’objectif principal de la stratégie de création de branches est de permettre à plusieurs développeurs de travailler sur différentes fonctionnalités et améliorations de la base de code, sans interférer avec le travail des autres développeurs.

Voici les principaux avantages :

- Plusieurs développeurs peuvent travailler sur la même base de code en parallèle, chacun sur leur branche de travail respective, en évitant les conflits et les problèmes de fusion.

- Les développeurs peuvent apporter des modifications plus rapidement et plus efficacement sans se soucier d’interrompre le travail des autres développeurs.

- Les modifications de la base de code sont correctement testées et vérifiées avant d’être fusionnées dans la branche principale. Cela permet de maintenir la qualité du code et réduit le risque de bugs et d’erreurs.

- Possibilité de suivre les différentes versions du code source. Cela permet de dépanner et de revenir aux versions précédentes facilement.

- Modifications effectuées sans affecter la base de code principale. Cela réduit considérablement le risque d’introduction de bugs et d’erreurs dans la production.

- Expérimentation de nouvelles fonctionnalités et idées sans casser le code source et ne intégration des branches dans la branche principale que si elles fonctionnent parfaitement.

- Meilleure communication entre les développeurs pour discuter des modifications plus facilement lors des Code Review (c'est-à-dire, l'examen systématique du code source d'un logiciel par des tiers dont le but est de trouver des bugs ou des vulnérabilités).


### REFLEXION ET APPLICATION D'UNE STRATEGIE DANS MON PROJET


#### GESTION DE PROJET

Pour me permettre de diviser le travail en plusieurs petits bouts de fonctionnalité cohérents est l'outil de gestion de projet Trello. J'ai spécifiquement utilisé la méthodologie Agile KANBAN en réalisant plusieurs colonnes dans lesquelles j'ai rajouté au fur et à mesure des "tickets" datés comme on peut le voir sur la capture d'écran suivante :

> Capture d'écran du tableau kanban sur Trello

Les branches de fonctionnalité que j'ai créées découlent naturelement des tickets référencés sur Trello.


#### ENVIRONNEMENT DE DEVELOPPEMENT

J'ai choisi d'utiliser l'IDE "Visual Studio Code" pour une question de facilité d'utilisation.


#### GITFLOW

Un workflow Git est une recette ou une recommandation expliquant comment utiliser Git pour accomplir une tâche de façon cohérente et productive. Les workflows Git encouragent les développeurs et les équipes DevOps à exploiter Git de façon efficace et cohérente.

Pour m'aider à respecter une méthodologie de gitflow, j'ai installé l'extenssion "Git Graph" sur mon IDE afin de pouvoir visualiser les différentes branches et sous-branches ainsi que les commits qui leur sont associés.

> Capture d'écran de git Graph


Etant seul dans le cadre de ce projet, j'ai décider d'autovalider les pull requests sur GitHub mais cela ne m'a pas empecher de travailler de façon structurée (comme si j'étais en groupe) en créant des branches de fonctionnalité sur une branche develop (une sous-branche de main) pour y integrer les évolutions constantes du code source (avec potentielement des erreurs s'y greffer) et pas directement dans la branche main qui doit être réservée à la mise en production (avec une version stable de l'application, sans anomalie et avec un ensemble de fonctionnalité cohérent et suffisant pour le déployer en ligne sans mauvaise surprise).

> schéma branches main / dev / autres branches


Voici la procédure que j’ai appliquée pour envoyer une branche de fonctionnalité sur GitHub afin d’effectuer la validation collective (uniquement lorsqu'une branche de travail est entièrement terminée) :

Rejoindre la branche "develop" :
```bash
git checkout develop
```
Permet de récupérer les dernieres modifications sur la branche develop depuis la branche develop du dépôt distant
```bash
git pull origin develop 
```

Rejoindre sa branche de travail :
```bash
git checkout fonctionnality_branch_name
```

Fusion de ma branche de fonctionnalité avec la branche "develop" en local :
```bash
git rebase develop  # contrairement à git merge, git rebase ne supprime pas les commits.
```

Export de ma fonctionnalité (rajoutée au develop) dans le develop du répertoire distant :
```bash
git push --set-upstream origin fonctionnality_branch_name
```

> Faire valider sa Pull Request (sur gitHub) par ses collègues (ou par un formateur)

Sur GitHub :
- Aller dans "Pull requests" > "New pull request"
- Choisir la branche "develop" à gauche et la branche de fonctionnalité à droite
- Créer la pull request
- Retourner dans "Pull requests" (normalement, cela ouvre la Pull Request automatiquement)
- Vérifier le code au préalable
- Cliquer sur "Merge pull request" puis "Confirm merge"


Si la pull request de ma fonctionnalité a été validé à l'unanimité sur gitHub, mettre à jour la branche develop locale qui a été fusionnée sur gitHub :
```bash
git checkout develop
git pull origin develop
```

Supprimer de la branche fonctionnalité :
```bash
git branch -d fonctionnality_branch_name
```

Passer au ticket suivant en recréant une nouvelle branche de fonctionnalité à partir de la branche develop.


#### ORGANISATION DES DOSSIERS


Pour simplifier l'organisation de mon travail, j'ai décomposé mon projet en plusieurs "microservices" (aux contenus cohérents mais plus réduits), c'est-à-dire des répertoires en local (frontend, backend et documentation), qui sont tous reliés à des répertoires distants aux contenus équivalents.

> Capture d'écran des repo gitHub


#### VERSIONNEMENT DU CODE SOURCE

Pour pouvoir revenir facilement en arrière lorsqu’un bug survient, j'ai pris l'habitude de faire des commits (sauvegarde du code en local) afin de conserver un historique des modifications effectuées dans le code, comme en témoigne la capture d'écran suivante :

> capture d'écran avec la commande "git log"


Pour me rappeler de faire des commits régulièrement (à chaque ajout de code fonctionnel et cohérent), j’ai lancé un timmer en arrière-plan qui émet un « bip » tous les 15 minutes.

Cela m'a également permit de nommer plus efficacement mes commits. A noter que le site gitmoji.dev m’a permit d’illustrer le nommage de mes commit de façon visuelle.


#### COMMANDE GIT QUE J'AI UTILISEES

Voici une liste des commandes git que j'ai utilisées : 

- Cloner un répertoire :
git clone https://github.com/nom_depositaire/repository_name my_project_name 


- Créer une branche de travail sur le dépot local (pour developper une fonctionnalité correspondant à un ticket)
git branch fonctionnality_branch_name

- Créer une branche de travail sur le dépot distant (à partir d'une branche locale existante)
git push --set-upstream origin develop

- Se déplacer sur une branche :
git checkout fonctionnality_branch_name

- Créer une branche et se déplacer dessus :
git checkout -b fonctionnality_branch_name

- Voir le nom de la branche sur laquelle on se trouve actuellement :
git branch

- Renommer une branche :
git branch -m new_branch_name

- Voir l'historique des commits de sa branche de travail
git log


- Ajouter tous les fichiers (ou seulement certains) dans la zone d'index pour le prochain commit :
git add .

- Faire une sauvegarde local de son code source :
git commit -m "message de commit"

- Envoyer le code source depuis le dépot local vers le dépot distant :
git push

- Réinitialiser les derniers changements (ne marche pas si on a fait un push avant) :
git stash

- Réinitialiser les derniers changements depuis son dernier commit :
git stash apply

- Revenir au commit précedent :
git reset --soft HEAD^
git reset --soft branch_name

