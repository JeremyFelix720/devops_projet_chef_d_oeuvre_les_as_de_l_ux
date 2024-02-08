# REDACTION DU DOSSIER DEVOPS

## SOMMAIRE
1. Remerciements
2. Résumé du projet en anglais
3. Liste des compétences du référentiel
4. Introduction : contexte du projet, résumé exécutif
5. Partie 1 : compréhension du besoin et traduction technique de la réponse apportée
6. Partie 2 : enjeux de la mise en œuvre du projet : justification des choix et arbitrages réalisés, problèmes rencontrés et solutions apportés
7. Partie 3 : bilan de projet et améliorations envisagées
8. Conclusion : apprentissages, perspectives pour le projet professionnel envisagé

## 1. Remerciements

## 2. Résumé du projet en anglais





## 3. Liste des compétences du référentiel

### C1. Assurer le versionnement d’un code source d’une application organisée en fonctionnalités et lots à l’aide d’un logiciel de contrôle de version de manière à garantir la fiabilité du code source dans un environnement multi-contributeurs
- Les sources sont versionnées avec Git
- Git en ligne de commande
- Respect d’un gitflow
- Utilisation de Github ou Gitlab par exemple

> GIT


### C2. Contrôler l'exécution du code source à l’aide de tests et d’outils d’analyses statiques du code source afin de minimiser le risque d’erreur dans un contexte de livraison continue
- Utilisation d’un linter (natif IDE ou externe)
- Environnement de test (virtuel ou conteneurisé par exemple)
- Au moins des tests unitaires d’intégrés (pas de minimum de coverage)
- Au moins des tests fonctionnels d’intégrés (pas de minimum de coverage)
- Savoir récupérer la valeur de la couverture du code par les tests
- Exécuter les tests
- Interpréter les résultats et les erreurs

> TESTS



### C3. Automatiser les phases de tests unitaires et d’analyses statiques du code source lors du partage des sources à l’aide d’un outil d’intégration continue* de manière à prévenir les erreurs potentielles
- Configurer l’intégration continue, avec Github Actions ou Gitlab CI/CD
- Paramétrer les phases d'exécution des tests dans l’environnement de test à chaque push (sur la branche concernée)

> INTEGRATION CONTINUE (CI)

### C4. Concevoir un processus de livraison continue à l’aide d’outils d’automatisation de manière à l’intégrer au processus de développement
- À chaque push (sur la branche concernée) paramétrer les phases de build pour un environnement de pré-production
- Paramétrer les phases de livraison des builds en environnement de pré-production

> DEPLOIEMENT CONTINUE (CD)


### C5. Développer l’architecture d’une application en micro-services à l’aide d’outils et de bibliothèques logicielles adaptées afin de réduire la complexité globale du système
- Décomposer une application monolithique en plusieurs composants et services
- Utiliser un service de conteneurisation pour tous les environnements : dev, test, prod, etc
- Adapter toute la chaîne DevOps à cette nouveauté

> MICROSERVICES


### C6. Concevoir un système de veille technologique permettant la collecte, la classification, l’analyse et la diffusion de l’information aux différents acteurs de l’organisation afin d’améliorer la prise de décisions techniques
- définir des objectifs à sa veille ou encore des thématiques de veille
- planifier les temps de veille : durée, fréquence
- organiser sa collecte d’information : outils de curation, outils de sauvegarde, etc
- organiser le partage voir la diffusion des informations pertinantes

> VEILLE TECHNOLOGIQUE


### C7. Accompagner les collaborateurs au sein de l’équipe projet dans la sensibilisation et l’acculturation des méthodes d’organisation et de production DevOps de manière à optimiser le cycle de livraison d’un projet
- expliquer et partager la culture DevOps
- expliquer et partager la méthode DevOps : les rôles, les outils, les leviers, etc
- analyser un processus Devops
- préconiser des améliorations à un processus DevOps

> TRAVAIL EN EQUIPE EN MODE DEVOPS


## 4. Introduction : contexte du projet, résumé exécutif


## 5. Partie 1 : compréhension du besoin et traduction technique de la réponse apportée


## 6. Partie 2 : enjeux de la mise en œuvre du projet : justification des choix et arbitrages réalisés, problèmes rencontrés et solutions apportés


### UTILISATION DE GIT ET GITHUB (C1)
- **Utilisation de Github** > capture d'écran des repo gitHub


Pour simplifier l'organisation de mon travail, j'ai décomposé mon projet en plusieurs "microservices" (aux contenus cohérents mais plus réduits), c'est-à-dire des répertoires en local (frontend, backend et documentation), qui sont tous reliés à des répertoires distants aux contenus équivalents.



#### VERSIONNEMENT DU CODE SOURCE
- **Les sources sont versionnées avec Git**

capture d'écran avec la commande "git log"


#### NOMMAGE DES COMMITS

Pour pourvoir revenir facilement en arrière lorsqu’un bug survient, il est préférable d’avoir un historique de sauvegardes en faisant concrètement des commits (nommés de façon explicite) régulièrement à chaque fois que l’on rajoute un bout de code fonctionnel et cohérent ;  pour m’y faire penser, j’ai lancé un timmer en arrière-plan qui émet un « bip » tous les 15 minutes.

Le site gitmoji.dev m’a permit d’illustrer le nommage de mes commit de façon visuelle.


#### COMMANDE GIT QUE J'AI UTILISEES
- **Git en ligne de commande**

Liste des commandes git


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




#### GITFLOW

- **Respect d’un gitflow**

Un workflow Git est une recette ou une recommandation expliquant comment utiliser Git pour accomplir une tâche de façon cohérente et productive. Les workflows Git encouragent les développeurs et les équipes DevOps à exploiter Git de façon efficace et cohérente.


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

Supprimer de la branche fonctionnalité (je peux m'en occuper plus tard ; __mais si j'ai oublié de faire quelque chose dans cette branche après l'avoir mergée, je dois en recreer une autre pour effectuer la mise à jour__) :
```bash
git branch -d fonctionnality_branch_name
```

Passer au ticket suivant en recréant une nouvelle branche de fonctionnalité à partir de la branche develop.



#### UTILISATION DES BRANCHES



L’objectif principal de la stratégie de création de branches est de permettre à plusieurs développeurs de travailler sur différentes fonctionnalités et améliorations de la base de code, sans interférer avec le travail des autres développeurs.

Voici les principaux avantages :

- Plusieurs développeurs peuvent travailler sur la même base de code en parallèle, chacun sur leur branche de travail respective, en évitant les conflits et les problèmes de fusion.

- Les développeurs peuvent apporter des modifications plus rapidement et plus efficacement sans se soucier d’interrompre le travail des autres développeurs.

- Les modifications de la base de code sont correctement testées et vérifiées avant d’être fusionnées dans la branche principale. Cela permet de maintenir la qualité du code et réduit le risque de bugs et d’erreurs.

- Possibilité de suivre les différentes versions du code source. Cela permet de dépanner et de revenir aux versions précédentes facilement.

- Modifications effectuées sans affecter la base de code principale. Cela réduit considérablement le risque d’introduction de bugs et d’erreurs dans la production.

- Expérimentation de nouvelles fonctionnalités et idées sans casser le code source et ne intégration des branches dans la branche principale que si elles fonctionnent parfaitement.

- Meilleure communication entre les développeurs pour discuter des modifications plus facilement lors des Code Review.


Par ailleurs, c'est une bonne pratique de créer les branches de fonctionnalité sur une branche develop (une sous-branche de main) pour y integrer les évolutions constantes du code source (avec potentielement des erreurs s'y greffer) et pas directement dans la branche main qui doit être réservée à la mise en production (avec une version stable de l'application, sans anomalie et avec un ensemble de fonctionnalité cohérent et suffisant pour le déployer en ligne sans mauvaise surprise).

> schéma branches main / dev / autres branches


### C2. Contrôler l'exécution du code source à l’aide de tests et d’outils d’analyses statiques du code source afin de minimiser le risque d’erreur dans un contexte de livraison continue

### CONTROLE QUALITE DU CODE (C2)

#### CHOIX ET UTILISATION D'UN LINTER
- **Utilisation d’un linter (natif IDE ou externe)** 

- à quoi çà sert un linter
- veille sur 2 ou 3 linters
- captures d'écran du code associé (fichier de parametrage + affichage des erreurs)




#### CHOIX ET UTILISATION D'UN OUTIL DE TESTING
- **Environnement de test (virtuel ou conteneurisé par exemple)**
- **Au moins des tests unitaires d’intégrés (pas de minimum de coverage)**
- **Au moins des tests fonctionnels d’intégrés (pas de minimum de coverage)**
- **Interpréter les résultats et les erreurs**


- à quoi çà sert les tests unitaires
- veille sur 2 ou 3 outils de testing unitaires
- captures d'écran du code associé aux tests unitaires (fichier de parametrage + affichage des erreurs avec leur interprétation)


- à quoi çà sert les tests unitaires
- veille sur 2 ou 3 outils de testing n2n
- captures d'écran du code associé aux tests n2n (fichier de parametrage + affichage des erreurs avec leur interprétation)


- **Savoir récupérer la valeur de la couverture du code par les tests** > commande git

- **Exécuter les tests** > "npm run test"







## 7. Partie 3 : bilan de projet et améliorations envisagées


## 8. Conclusion : apprentissages, perspectives pour le projet professionnel envisagé

## 9. Bibliographie


https://www.bocasay.com/fr/strategie-creation-branches-expliquee/

