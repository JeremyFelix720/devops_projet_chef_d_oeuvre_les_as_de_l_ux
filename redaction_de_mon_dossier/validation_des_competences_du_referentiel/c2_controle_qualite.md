## 2.2 - CONTROLE QUALITE

### COMPETENCE(S) CONCERNEE(S) DANS LE REFERENTIEL

C2. Contrôler l'exécution du code source à l’aide de tests et d’outils d’analyses statiques du code source afin de minimiser le risque d’erreur dans un contexte de livraison continue
- Utilisation d’un linter (natif IDE ou externe)
- Environnement de test (virtuel ou conteneurisé par exemple)
- Au moins des tests unitaires d’intégrés (pas de minimum de coverage)
- Au moins des tests fonctionnels d’intégrés (pas de minimum de coverage)
- Savoir récupérer la valeur de la couverture du code par les tests
- Exécuter les tests
- Interpréter les résultats et les erreurs

### OBJECTIF PRINCIPAL DE CETTE PHASE DU PROJET




### REFLEXION ET APPLICATION D'UNE STRATEGIE DANS MON PROJET

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

- à quoi çà sert les tests End To End
- veille sur 2 ou 3 outils de testing n2n
- captures d'écran du code associé aux tests e2e (fichier de parametrage + affichage des erreurs avec leur interprétation)

Les tests "End To End" (ou "e2e"), c'est-à-dire "de bout en bout", permettent de vérifier que :
- la partie frontend d'une application se comporte comme prévu du début à la fin. Le testeur doit se mettre dans la peau d’un utilisateur et dérouler les tests comme s’il utilisait véritablement l’outil mis à sa disposition
- le frontend est correctement intégré avec le backend ou d'autres webservices.

Les tests e2e sont obligatoires car ils sont les seuls tests permettant de vérifier le parfait fonctionnement de l’application du point de vue du métier (c'est-à-dire, que sa valeur pratique est cohérente par rapport à la raison d'être de l'application).

Généralement, les tests e2e doivent être réalisés juste avant la mise en production de l'application.

##### LISTES DES SCENARIOS

Il n'est pas pertinent de tester tous les cas de figure possibles auquel l'utilisateur pourrait être confronté. Pour être pertinent, un test e2e doivent être calqués sur les scénarios qui modèlisent les attentes du métier (simplifiés pour n’exécuter que les étapes critiques passantes ou non passantes). Chaque scenario est donc un ensemble de cas de tests.

Voici quelques scénarios utilisateur identitifiés et priorisés par ordre d'importance par rapport à la logique métier :

**Scénario 1 : "Un client publie un projet"**
- John se rend sur l'application "Les As de l'UX"
- se connecte sur son compte ou en crée un s'il n'en a pas
- se rend dans la rubrique "Projets"

Si c'est pour créer un nouveau projet :
- rajoute un nouveau projet (vérifier que le bouton "+" redirige bien vers la page "Création/Modification d'un projet")
- rempli le nom du projet
- rempli (...)
- valide le formulaire (vérifier que lorsque le bouton d'envoi du formulaire est cliqué, cela enregistre bien toutes les informations renseignées dans la rubrique "Projets")

Si c'est pour modifier un projet existant :
- modifie un projet existant (vérifier que le bouton "Modifier le projet" redirige bien vers la page "Création/Modification d'un projet")
- modifie le nom du projet
- modifie (...)
-
- valide la création ou la 




**Scénario 2 : "Un utilisateur publie un commentaire"**
- John se rend sur l'application "Les As de l'UX"
- se connecte sur son compte ou en crée un s'il n'en a pas
-
-
-
-
-

**Scénario 3 : "Un client (admin) effectue le classement des 5 meilleurs commentaires"**
- John se rend sur l'application "Les As de l'UX"
- se connecte sur son compte ou en crée un s'il n'en a pas
-
-
-
-
-


Exemple de scénario :
Il pourrait aussi être bien plus complexe :

- John se rend sur le site e-commerce X
- recherche le produit Y
-change une option
- l’ajoute à son panier
- sur la page panier il change la quantité
- recherche un second produit, le produit Z, issu de la market place
- l’ajoute au panier
- choisi l’option de livraison “retrait en magasin” pour le produit Y
- choisi l’option de livraison “livraison rapide” pour le produit Z
- ajoute un code promo
- règle une partie du panier avec une carte cadeau
- règle le solde avec un compte Amazon Pay




Les tests e2e doivent être automatisés car ils sont effectués de façon récurente à chaque push.


- **Savoir récupérer la valeur de la couverture du code par les tests** > commande git

- **Exécuter les tests** > "npm run test"



