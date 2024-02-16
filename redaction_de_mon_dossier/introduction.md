## 1 - INTRODUCTION

### REMERCIEMENTS

Tout d'abord, je tiens à remercier toute l'équipe pédagogique pour l'aide qu'ils m'ont apportée entre autre dans la réalisation de la partie DevOps de mon projet de fin d'étude que je vais aborder plus bas.

### CONTEXTE DU PROJET

Dans le cadre de la formation "Concepteur / Développeur d'Application DevOps" au sein de l'organisme SIMPLON, nous avions un projet chef-d'oeuvre à réaliser de A à Z sous la forme d'une application web.

Nous avons démarré ce projet relativement tôt dans le cours de l'année, ce qui nous a permi de mettre en pratique progressivement les compétences théoriques acquises.

### OBJECTIF DE CE DOSSIER

Mon objectif est de vous montrer que j'ai compris tout l'intérêt d'utiliser la méthodologie DevOps dans ce projet au travers d'explications détaillées sur le rôle de chaque outil du DevOps que j'ai mis en place concrètement (ou que je prévois d'utiliser plus tard).

### COMPOSITION DE L'EQUIPE

L’apprenant Jérémy FELIX a réalisé l’ensemble de ce projet chef-d’œuvre en totale autonomie.

### RESUME DU PROJET

L’application “Les As de l’UX” permet principalement de mettre en relation des chargés de création / refontes de site web (ou d’applications) avec les autres utilisateurs de l’application (amateurs et professionnels de l’UX design) afin de recueillir plusieurs avis extérieurs et constructifs (suivant le concept de l’intelligence collective) pour guider la mise en place de changements (destinés à être regroupés dans un PDF) pour améliorer l'UX Design les produits numériques existants sur le marché.

Mon modèle économique est simple : le client verse un somme d'argent sur un compte "Les As de l'UX" pour mettre en ligne son projet puis, une fois que le nomre maximum de commentaires a été atteint, le client selectionne les 5 meilleurs commentaires selon lui ; ce qui permet 1) aux commentateurs concernés de recevoir une partie de la somme itialement versée, 2) à "Les As de l'UX" de se dégager une marge avec l'argent restant et 3) que le client puisse télécharger le PDF de l'analyse UX globale sur son projet.

### LISTE DES COMPETENCES DU REFERENTIEL

#### C1. Assurer le versionnement d’un code source d’une application organisée en fonctionnalités et lots à l’aide d’un logiciel de contrôle de version de manière à garantir la fiabilité du code source dans un environnement multi-contributeurs
- Les sources sont versionnées avec Git
- Git en ligne de commande
- Respect d’un gitflow
- Utilisation de Github ou Gitlab par exemple

#### C2. Contrôler l'exécution du code source à l’aide de tests et d’outils d’analyses statiques du code source afin de minimiser le risque d’erreur dans un contexte de livraison continue
- Utilisation d’un linter (natif IDE ou externe)
- Environnement de test (virtuel ou conteneurisé par exemple)
- Au moins des tests unitaires d’intégrés (pas de minimum de coverage)
- Au moins des tests fonctionnels d’intégrés (pas de minimum de coverage)
- Savoir récupérer la valeur de la couverture du code par les tests
- Exécuter les tests
- Interpréter les résultats et les erreurs

#### C3. Automatiser les phases de tests unitaires et d’analyses statiques du code source lors du partage des sources à l’aide d’un outil d’intégration continue* de manière à prévenir les erreurs potentielles
- Configurer l’intégration continue, avec Github Actions ou Gitlab CI/CD
- Paramétrer les phases d'exécution des tests dans l’environnement de test à chaque push (sur la branche concernée)

#### C4. Concevoir un processus de livraison continue à l’aide d’outils d’automatisation de manière à l’intégrer au processus de développement
- À chaque push (sur la branche concernée) paramétrer les phases de build pour un environnement de pré-production
- Paramétrer les phases de livraison des builds en environnement de pré-production

#### C5. Développer l’architecture d’une application en micro-services à l’aide d’outils et de bibliothèques logicielles adaptées afin de réduire la complexité globale du système
- Décomposer une application monolithique en plusieurs composants et services
- Utiliser un service de conteneurisation pour tous les environnements : dev, test, prod, etc
- Adapter toute la chaîne DevOps à cette nouveauté

#### C6. Concevoir un système de veille technologique permettant la collecte, la classification, l’analyse et la diffusion de l’information aux différents acteurs de l’organisation afin d’améliorer la prise de décisions techniques
- Définir des objectifs à sa veille ou encore des thématiques de veille
- Planifier les temps de veille : durée, fréquence
- Organiser sa collecte d’information : outils de curation, outils de sauvegarde, etc
- Organiser le partage voir la diffusion des informations pertinantes

#### C7. Accompagner les collaborateurs au sein de l’équipe projet dans la sensibilisation et l’acculturation des méthodes d’organisation et de production DevOps de manière à optimiser le cycle de livraison d’un projet
- Expliquer et partager la culture DevOps
- Expliquer et partager la méthode DevOps : les rôles, les outils, les leviers, etc
- Analyser un processus Devops
- Préconiser des améliorations à un processus DevOps

### STRUCTURATION DES PARTIES DE VALIDATION DU REFERENTIEL

Pour chacune des parties, je préciserai :
- Compétence(s) concernée(s) dans le référentiel
- L’objectif principal de cette phase du projet
- Réflexion et application d'une stratégie dans mon projet
