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

**Scénario 1 : "Un utilisateur crée un nouveau compte"**
- Rémy se rend sur l'application "Les As de l'UX" (vérifier que la page de connexion est affichée par defaut lors de l'ouverture de l'application)
- se crée un nouveau compte (vérifier que, lorsqu'il clique sur le bouton "pas de compte ? créez-en un !", il soit bien redirigé vers la page "Création / Modification de votre compte")
- rempli son pseudonyme (vérifier que le champs n'accepte que le type "string")
- rempli sa date de naissance (vérifier que le champs n'accepte que le type "date")
- rempli son adresse e-mail (vérifier que le champs n'accepte que le type "e-mail")
- rempli sa ville (vérifier que le champs n'accepte que le type "string")
- rempli son code postal (vérifier que le champs n'accepte que le type "number")
- rempli son numéro de téléphone (vérifier que le champs n'accepte que le type "string")
- rempli son mot de passe (vérifier que le champs n'accepte que le type "string" ET vérifier que les carractères sont bien remplacés par des "*" lorsque l'on clique sur le bouton "masquer" et réciproquement aussi)
- confirme son mot de passe
- consulte les Conditions Générales d'Utilisation (vérifier que le lien "CGU" le redirige bien vers la page "CGU")
- revient en arrière (vérifier que, lorqu'il clique sur le bouton "retour", il soit bien redirigé vers la page "Création / Modification de votre compte" sans avoir perdu les informations renseignées précédement)
- accepte les Conditions Générales d'Utilisation (vérifier que la coche est cochée lorsqu'il clique dessus et réproquement aussi)
- valide le formulaire (vérifier que lorsque le bouton d'envoi du formulaire est cliqué, cela enregistre bien toutes les informations textuelles et l'image de l'avatar renseignées)

**Scénario 2 : "Un utilisateur se connecte à son compte"**
- Rémy se rend sur l'application "Les As de l'UX" (vérifier que la page de connexion est affichée par defaut lors de l'ouverture de l'application)
- rempli son mot de passe (vérifier que le champs n'accepte que le type "string" ET vérifier que les carractères sont bien remplacés par des "*" lorsque l'on clique sur le bouton "masquer" et réciproquement aussi)
- rempli son adresse e-mail (vérifier que le champs n'accepte que le type "e-mail")
- se connecte à l'application (vérifier que, si l'email et le mot de passe existent dans la base de données, il soit redirigé vers la page "Home" de l'application ET vérifier qu'aucun élément du footer ne soit sélectionné)  

**Scénario 3 : "Un client publie un projet"**
- Voir le scénario "Un utilisateur se connecte à son compte"
- Rémy se rend dans la rubrique "Projets" (vérifier qu'il est bien redirigé vers la page "projets" ET que l'option "projet" du footer est bien surligné)
- rempli/modifie un nouveau projet (vérifier que le bouton "+" le redirige bien vers la page "Création/Modification d'un projet")
- rempli le titre (vérifier que le champs n'accepte que le type "string")
- rempli/modifie l'URL du projet (vérifier que le champs n'accepte que le type "string")
- ajoute/remplace la photo pour illustrer la bannière (vérifier que l'aperçu s'affiche bien)
- rempli/modifie la description du projet (vérifier que le champs n'accepte que le type "string")
- ajoute un nouveau scenario à analyser (vérifier que le champs n'accepte que le type "string" ET que, lorsque l'on clique sur le bouton "valider le scénario", le texte renseigné dans le champs se rajoute bien à la suite dans la To Do List en dessous)
- ajoute un deuxième et un troisième scénario
- supprime le deuxième scénario (vérifier que, lorsque l'on clique sur le bouton "poubelle" dans un élément de la liste, le scénario ciblé est bien supprimé)
- ajoute une nouvelle page à analyser (vérifier que le champs n'accepte que le type "string" ET que, lorsque l'on clique sur le bouton "valider la page", le texte renseigné dans le champs se rajoute bien à la suite dans la To Do List en dessous)
- ajoute une deuxième et une troisième page
- supprime la deuxième page (vérifier que, lorsque l'on clique sur le bouton "poubelle" dans un élément de la liste, la page ciblée est bien supprimée)
- selectionne le budget (vérifier que la valeur du menu déroulant change bien en fonction de l'option selectionnée ET que l'indication du nombre de participants soit cohérente par rapport à la valeur précédente renseignée)
- met le projet en favoris
- valide le formulaire (vérifier que lorsque le bouton d'envoi du formulaire est cliqué, cela enregistre bien toutes les informations textuelles et l'image de la bannière renseignées)

**Scénario 4 : "Un utilisateur publie un commentaire"**
- Voir le scénario "Un utilisateur se connecte à son compte"
- se connecte sur son compte ou en crée un s'il n'en a pas
- se rend dans la rubrique "projets" (vérifier que lorsqu'il clique sur l'option "projets" du footer, il soit bien redirigé vers la page "projets" et que l'option devienne surlignée)
- met un projet en favoris (vérifier qu'en cliquant sur le bouton "favoris", la carte se place bien dans la sous-rubrique "projets favoris")
- se renseigne sur un projet en particulier (vérifier qu'en cliquant sur le bouton "voir plus", il soit bien redirigé vers la page "projet" correspondante)
- se rend dans l'analyse UX (vérifier qu'en cliquant sur le bouton "voir l'analyse UX", il soit bien redirigé vers la page "analyse" correspondante à ce projet)
- se renseigne sur les problèmes d'accessibilité (vérifier qu'en cliquant sur le bouton "problèmes d'accessibilité", il soit bien redirigé vers la page "problèmes d'accessibilité" correspondante à ce projet)
- consulte les lois de l'UX correspondante (vérifier que le carroussel soit fonctionnel et ne contient que les fiches mémos liées à cette catégorie "accessibilité" et que, parmi ces fiches, elles soient à l'état "débloquées" par l'utilisateur de l'application)
- consulte le projet en ligne (vérifier qu'en cliquant sur le bouton "accèder au projet en ligne", il soit bien redirigé sur le projet en ligne correspondant)
- signale un problème d'accessibilité rencontré (vérifier que le champs n'accepte que le type "text")
- (...)
-
-


**Scénario 5 : "Un client (admin) effectue le classement des 5 meilleurs commentaires"**
- Voir le scénario "Un utilisateur se connecte à son compte"
- se connecte sur son compte ou en crée un s'il n'en a pas
- (...)
-
-
-
-

Pour chacun des champs de formulaire mentionnés ci-dessus : vérifier que le champs est surligné lorsqu'il clique dessus et qu'il revient à son état initial lorsqu'il clique en dehors du champs




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



