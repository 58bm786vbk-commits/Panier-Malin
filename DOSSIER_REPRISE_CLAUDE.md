# PANIER MALIN — DOSSIER COMPLET DE REPRISE POUR CLAUDE
Dernière mise à jour : 18 novembre 2026

## 1. Mission de Claude

Tu reprends le projet existant **Panier Malin**. Il ne s'agit PAS de repartir de zéro ni de remplacer arbitrairement les décisions déjà prises. Commence par examiner intégralement le dépôt GitHub, comprendre l'application actuelle, identifier ce qui fonctionne, ce qui est simulé, les bugs et les dettes techniques. Ensuite seulement, propose une feuille de route et poursuis avec l'accord de l'utilisateur.

L'utilisateur n'est pas développeur et souhaite être accompagné simplement, étape par étape, avec des explications claires et sans jargon inutile. Il faut éviter de lui demander de répéter des informations déjà présentes dans ce dossier. Ne prétends jamais avoir modifié, testé, publié ou connecté quelque chose si cela n'a pas réellement été fait.

## 2. Source de vérité : dépôt et code existant

Dépôt GitHub : https://github.com/58bm786vbk-commits/Panier-Malin
Branche principale : main
Visibilité constatée le 18/11/2026 : public.
Dernière activité constatée : 17/11/2026.
Langage détecté : HTML.

Arborescence complète constatée :
- .nojekyll
- README.md
- index.html
- styles.css
- app.js
- manifest.webmanifest

Le dépôt contient une application web statique déjà conséquente. Le fichier index.html fait environ 141 Ko et contient beaucoup de HTML, CSS/JS intégrés et des fonctionnalités de menus/recettes. Ne pas se limiter au petit app.js : lire tout le code, notamment la fin de index.html où se trouvent plusieurs correctifs successifs du catalogue de recettes et du bouton « Voir d’autres menus ».

Le README décrit un prototype sans API, sans compte bancaire et sans serveur applicatif ; les données de démonstration sont stockées dans localStorage. La clé de stockage utilisée dans app.js est « panier-malin-v02 ». Le projet est prévu pour une utilisation mobile et une installation sur l'écran d'accueil iPhone via Safari / PWA. Les fichiers manifest.webmanifest et .nojekyll sont présents.

Le dépôt est public : ne jamais y ajouter de clés API, mots de passe, données privées ou informations personnelles. Avant toute modification importante, examiner l'état actuel et préserver les fonctions existantes. Préférer des changements incrémentaux, sauvegardés par commits lisibles.

## 3. Vision et objectif produit

Panier Malin est un assistant personnel de courses alimentaires, mobile-first, qui centralise au même endroit :
- préparation des menus et des repas ;
- listes de courses ;
- produits, quantités, prix et paniers ;
- comparaison et optimisation des dépenses ;
- promotions, coupons et réductions ;
- cashback ;
- cartes de fidélité et cartes cadeaux ;
- tickets de caisse et suivi des dépenses ;
- recommandations pour économiser du temps et de l'argent.

Le projet est né d'un besoin concret : simplifier les courses habituelles du samedi, notamment chez Carrefour, et mieux exploiter les promotions et remboursements. L'application doit aider à faire des économies sans rendre le parcours compliqué. L'utilisateur garde le contrôle des achats, des validations et des démarches.

Le but est une application pratique, agréable, fiable et suffisamment complète pour devenir l'outil central des courses du foyer.

## 4. Utilisation et préférences connues

- Usage prioritaire sur iPhone, avec interface web mobile installable.
- Usage en magasin, notamment Carrefour près de Sequedin / Lille, mais le projet doit pouvoir s'étendre à d'autres enseignes.
- L'utilisateur veut une interface compacte, dense en informations utiles, mais lisible.
- Navigation principale en bas de l'écran, comme dans la maquette retenue.
- Photos réalistes des produits et des plats, pas des illustrations fantaisistes ou des emojis comme substitut final.
- Préférence pour une vue synthétique où plusieurs informations utiles sont visibles simultanément.
- Conserver une identité visuelle cohérente. Une couleur de thème historique est #1F4D3A ; le code actuel contient aussi une palette bleu marine. Ne pas changer arbitrairement la charte sans présenter la proposition.
- L'utilisateur souhaite comparer les propositions visuelles lorsqu'il hésite, et a retenu la version B pour l'accueil lors des échanges de novembre 2026.
- Ne pas automatiser les demandes de cashback : l'application doit simplifier et guider, l'utilisateur effectue lui-même les validations nécessaires.
- Pour Mon Avis le Rend Gratuit, mode assisté avec ouverture du site, pas d'automatisation des actions à la place de l'utilisateur.

## 5. Fonctionnalités et intégrations souhaitées

### Magasins / enseignes prioritaires
- Carrefour (priorité d'usage)
- E.Leclerc
- Lidl

À terme, permettre de choisir le magasin ou l'enseigne avant de rechercher les produits, prix, promotions et offres disponibles. Le mode magasin doit aider l'utilisateur à préparer ses achats et à retrouver rapidement les informations utiles en rayon.

### Cashback, coupons et offres
Intégrations / services à étudier :
- Poulpeo
- Shopmium
- iGraal
- Quoty
- autres services pertinents, si cela apporte une réelle valeur.

L'application doit distinguer clairement les réductions immédiates, coupons, avantages fidélité, cashback à récupérer et paiements avec carte cadeau. Ne pas additionner comme si tout était une remise immédiate ce qui ne l'est pas. Afficher les conditions et le montant réellement estimé.

Mon Avis le Rend Gratuit : raccourci assisté vers le site officiel.

Les intégrations directes ne doivent être annoncées comme disponibles qu'après vérification des API, autorisations et conditions d'utilisation. Si aucune API officielle n'est disponible, proposer une redirection ou un accompagnement manuel plutôt que simuler une connexion réelle.

### Portefeuille
- Cartes de fidélité.
- Cartes cadeaux.
- Affichage du code-barres / code en caisse lorsque la donnée réelle le permet.
- Suivi des soldes et montants restants.
- Possibilité de retrouver rapidement les cartes en magasin.

Le prototype actuel montre une carte cadeau Carrefour de démonstration et un code-barres visuel simulé. Il ne faut pas le présenter comme un vrai code utilisable en caisse.

### Menus malins
Paramètres déjà définis par l'utilisateur :
- 3 à 4 personnes ;
- 5 repas ;
- budget « équilibre » ;
- style « variée » ;
- génération automatique de la liste de courses : oui.

Les menus doivent proposer des recettes variées, avec photos réalistes, ingrédients, quantités adaptées au nombre de personnes, préparation et ajout des ingrédients à la liste de courses. Prévoir favoris et renouvellement des propositions sans répétitions immédiates.

Les recettes préférées doivent pouvoir être retrouvées et leurs ingrédients ajoutés à la liste.

### Listes et panier
- Création et modification des listes.
- Ajout, modification, suppression de produits.
- Quantités, prix, catégories et état acheté / non acheté.
- Ajout des ingrédients d'une recette à la liste.
- Gestion du panier actif.
- Calcul des montants et économies.
- L'utilisateur doit pouvoir corriger manuellement les données.

### Tickets et dépenses
- Import / photo d'un ticket de caisse.
- Le prototype affiche une prévisualisation d'image, mais l'analyse OCR/IA est simulée ou à développer.
- À terme, extraire les articles et montants, demander confirmation/correction et alimenter l'historique des dépenses.
- Ne jamais considérer une lecture OCR comme certaine sans validation utilisateur.

## 6. Conception récente — décisions de novembre 2026

Les échanges des 17 novembre 2026 ont porté sur la refonte de Panier Malin, notamment les menus qui tournent en boucle et la conception écran par écran.

Décisions validées :
- Navigation en bas de l'écran.
- Interface compacte avec un maximum d'informations visibles.
- Photos réelles / réalistes pour les produits et les plats.
- Vue synthétique, avec plusieurs informations visibles simultanément.
- L'utilisateur a choisi la **version B** pour l'accueil.
- La version B comprend un suivi du budget courses mensuel.

Structure retenue pour l'accueil Version B :
- économies réalisées ;
- budget mensuel de courses (320 € était un exemple de maquette, pas un budget définitivement confirmé) ;
- montant dépensé ;
- pourcentage du budget consommé ;
- montant restant ;
- accès aux listes ;
- menus ;
- promotions ;
- cartes ;
- panier actif ;
- prochain repas ;
- offres / promotions du moment.

Le montant de 320 € ne doit pas être codé en dur comme budget personnel confirmé : c'était une valeur d'exemple de présentation.

### Décision encore ouverte : alimentation du budget mensuel
La méthode de calcul et d'alimentation du budget n'est pas encore validée.
Une proposition discutée :
- comptabiliser automatiquement les achats validés dans l'application ;
- permettre l'ajout manuel de dépenses ;
- permettre correction et suppression ;
- conserver un historique mensuel ;
- alerte à l'approche de la limite.
L'utilisateur n'a pas encore tranché la méthode. Ne pas implémenter comme décision définitive sans lui demander.

### Maquette finale
L'utilisateur a demandé de préparer une maquette finale écran par écran. Il a aussi dit « Je ne sais pas encore » à propos d'un point de conception non tranché dans le dernier échange. Ne pas inventer la réponse à ce point : présenter les propositions visuelles restantes et lui demander uniquement la décision indispensable au moment opportun.

## 7. Problème récent : menus qui tournent en boucle / variété des recettes

Un échange du 18 novembre porte sur la correction des menus qui se répètent / tournent en boucle.
Le code actuel contient plusieurs scripts ajoutés successivement dans index.html autour de MENU_BOOK, menuOffset, showMoreMenus, displayedMenuIds et du bouton « Voir d’autres menus ». On y trouve des corrections successives de doublons, de favoris et de tirage de recettes.
Claude doit :
1. lire tous ces scripts dans leur ordre réel ;
2. identifier les gestionnaires d'événements multiples ou fonctions redéfinies ;
3. comprendre le fonctionnement actuel du catalogue MENU_BOOK ;
4. reproduire le bug dans la mesure du possible ;
5. proposer une solution propre, unique et testable qui évite les doublons immédiats et assure un cycle de variété cohérent ;
6. éviter d'empiler un nouveau correctif en fin de fichier sans supprimer / rationaliser les anciennes implémentations.
Préserver les favoris et l'ajout des ingrédients à la liste.

## 8. État technique observé dans le code

### app.js
- localStorage avec clé panier-malin-v02.
- Données de démonstration pour produits et cartes.
- Calculs de prix initial, promotions, coupons, cashback, carte cadeau, économies et reste à payer.
- Ajout / modification / suppression de produits.
- Ajout de cartes cadeaux.
- Affichage d'un visuel de code-barres.
- Quelques offres cashback entièrement simulées.
- Import image de ticket avec prévisualisation et analyse simulée.
- Les boutons partenaires affichent actuellement un message indiquant que l'ouverture de l'application partenaire est à venir.

### index.html
- Gros fichier HTML contenant de nombreuses vues et fonctions.
- Examiner le contenu complet et repérer les fonctions en double, les scripts inline successifs et les correctifs empilés.
- Il contient notamment des fonctions de menus/recettes, paramètres de portions, favoris, ajout d'ingrédients à la liste et affichage de davantage de menus.
- Ne pas supposer que tout ce qui est visible dans l'interface est réellement connecté à un service externe.

### styles.css
- Feuille de style séparée.
- Le style actuel utilise principalement des bleus / bleu marine et des verts.
- Responsive et navigation fixe en bas sur mobile.
- Le projet comporte aussi des styles intégrés dans index.html.

### manifest.webmanifest
- PWA nommée Panier Malin.
- display standalone.
- Couleur de thème actuelle dans ce fichier : #103B69.
- Attention à la différence avec la couleur historique #1F4D3A.

### Limites et sécurité
- Prototype actuel sans backend métier ni authentification.
- Données conservées localement dans le navigateur : pas de synchronisation multi-appareils ni sauvegarde cloud garantie.
- Les données de démonstration et les offres simulées doivent être identifiées comme telles.
- Ne pas demander ni stocker de coordonnées bancaires ou identifiants de services de cashback.
- Ne pas exposer de secrets dans le dépôt public.
- Les fonctionnalités d'intégration nécessitent une étude de faisabilité et de conformité avant toute promesse.

## 9. Historique de direction produit et évolutions envisagées

Une architecture légère avait été envisagée : application web installable Safari, dépôt GitHub pour le code et l'historique, hébergement statique possible, stockage local au prototype. Toute évolution vers un backend, synchronisation ou API doit être justifiée par un besoin concret et expliquée en termes de coût et de complexité.

Fonctionnalités envisagées à moyen terme :
- recherche produits / prix / promotions selon l'enseigne ;
- comparaison des prix ;
- optimisation de panier ;
- menus et liste automatique ;
- portefeuille de cartes ;
- suivi des économies ;
- tickets et historique ;
- recommandations utiles.

Ne pas présumer que toutes ces fonctionnalités sont déjà opérationnelles.

## 10. Méthode de travail demandée à Claude

Ordre recommandé :

**Étape 1 — Audit fidèle**
- Lire README.md, index.html en entier, styles.css, app.js et manifest.webmanifest.
- Cartographier les écrans, fonctionnalités et données.
- Séparer : opérationnel / simulé / incomplet / buggué / absent.
- Repérer les fonctions en double, scripts inline, problèmes d'accessibilité et risques de perte de données.
- Faire un état des lieux sans modifier le code.

**Étape 2 — Reprise de conception**
- Reprendre la navigation basse, l'interface compacte, les photos réalistes et la home Version B.
- Détailler chaque écran et les parcours principaux.
- Respecter les décisions déjà prises et signaler clairement les choix encore ouverts.
- Présenter des maquettes / propositions avant une refonte lourde.

**Étape 3 — Stabilisation**
- Traiter d'abord le bug de répétition des menus.
- Consolider le code plutôt que multiplier les scripts correctifs.
- Tester les listes, les favoris, les portions, l'ajout des ingrédients, le panier, les calculs et le portefeuille.
- Préserver les données existantes de localStorage autant que possible ; si une migration est nécessaire, prévoir une migration sans perte et une sauvegarde.

**Étape 4 — Développement progressif**
- Prioriser les fonctions de base et leur fiabilité.
- Ensuite étudier les données produits, prix, promotions et intégrations partenaires.
- Distinguer intégration officielle, lien externe et simulation.
- Vérifier les coûts, limites et conditions avant de proposer un service externe.

**Étape 5 — Livraison**
- Expliquer précisément les fichiers modifiés.
- Fournir une version testable et les étapes simples de mise à jour / publication.
- Ne pas prétendre qu'une fonction a été testée si elle ne l'a pas été.
- Ne jamais remplacer toute l'application par un prototype simplifié sans accord.

## 11. Instructions de communication avec l'utilisateur

- Répondre en français.
- Être clair, concret, pédagogue et concis.
- L'utilisateur n'est pas développeur : expliquer les manipulations une par une.
- Ne pas noyer l'utilisateur sous des questions. Si un point essentiel manque, poser une seule question précise.
- Ne pas refaire valider les décisions déjà actées.
- Ne pas annoncer des intégrations impossibles ou non vérifiées.
- Être transparent sur les limites, les simulations et les coûts éventuels.
- Avant les opérations GitHub importantes, préciser ce qui va être modifié et préserver le dépôt.
- Le projet doit rester Panier Malin (ne pas le renommer).

## 12. Première réponse attendue de Claude

Après avoir lu le dépôt et ce dossier, répondre avec :
1. un état des lieux concret du code réellement présent ;
2. une liste des fonctions réellement opérationnelles, simulées, incomplètes et absentes ;
3. les problèmes techniques prioritaires, en particulier la logique des menus qui se répètent ;
4. une proposition de plan de reprise par étapes, sans modification immédiate ;
5. les éventuels points de conception qui restent réellement à décider.

Commencer par le dépôt réel : https://github.com/58bm786vbk-commits/Panier-Malin
