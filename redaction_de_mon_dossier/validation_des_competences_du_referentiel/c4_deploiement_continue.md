## 2.4 - DEPLOIEMENT CONTINUE (CD)

### COMPETENCE(S) CONCERNEE(S) DANS LE REFERENTIEL

C4. Concevoir un processus de livraison continue à l’aide d’outils d’automatisation de manière à l’intégrer au processus de développement
- À chaque push (sur la branche concernée) paramétrer les phases de build pour un environnement de pré-production
- Paramétrer les phases de livraison des builds en environnement de pré-production

### OBJECTIF PRINCIPAL DE CETTE PHASE DU PROJET

Le déploiement continue ("Continuous Deployment" ou "CD" en anglais) est une stratégie de développement logiciel qui permet de publier automatiquement les modifications apportées dans le code source en mettant à jour la version de l'application disponible aux utilisateurs.

Les principaux avantages sont les suivants :
- il accélère la mise sur le marché en éliminant le décalage, généralement de plusieurs jours, semaines, voire mois, entre le codage et la valeur client.
- Le contrôle des versions facilite l'intégration continue en assurant le suivi des révisions apportées aux actifs d'un proje













Voici un schéma qui résume les différentes étapes du déploiement continue (partie "Ops" uniquement):

![DevOps](../img/devops.png "DevOps")


Comme le montre le schéma suivant, le déploiement continue va plus loin que l'intégration continue :

![Intégration continue et déploiement continu](../img/integration_continue_et_deploiement_continu.jpg "Intégration continue et déploiement continu")




### REFLEXION ET APPLICATION D'UNE STRATEGIE DANS MON PROJET

> Hébergement automatisé du front sur Vercel