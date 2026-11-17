# ARCADIA BREAKOUT 🕹️

Casse-briques rétro original, conçu pour téléphone en portrait, indépendant des autres projets Arcadia.

## V1.7 — Malus et briques spéciales

- **Malus Turbo (!) :** balle accélérée x1,45 pendant 9 secondes. Retour à la vitesse normale après expiration.
- **Malus Mini (-) :** raquette réduite à 39 unités (contre ~72) pendant 12 secondes, puis taille normale.
- Les deux malus apparaissent aléatoirement parmi les bonus existants, sans créer de nouvelles capsules systématiques. Le ralentissement neutralise Turbo et la raquette XXL neutralise Mini.
- Dès le **niveau 2**, certaines briques renforcées demandent **2 impacts** pour disparaître. Leur apparence se fissure/change après le premier coup.
- Dès le **niveau 4**, jusqu'à **2 briques métalliques indestructibles** apparaissent et font rebondir la balle même en mode traversante. Les tirs laser ne les détruisent pas.
- **Fin de niveau :** seules les briques destructibles doivent être éliminées ; les indestructibles ne bloquent jamais le passage au niveau suivant.
- Les HP des briques et les durées des malus font partie de la sauvegarde. Les anciennes sauvegardes V1.6 sont reprises avec des briques à 1 HP.
- La progression et les modes monnayeur restent inchangés.

## V1.6 — Monnayeur épuré et pièce de 50 centimes

- La page d'accueil affiche d'abord le logo **ARCADIA BREAKOUT**, puis **INSERT COIN**.
- Le pied de page redevient neutre : il n'annonce plus le secret.
- Quatre pièces virtuelles disposées en **2 × 2** : 50 centimes, 1 franc, 2 francs, 5 francs.
- **50 centimes** : partie classique à 3 vies ; même enregistrement de record que le jeu classique historique.
- Les légendes révélant les avantages, la phrase d'explication et le bouton Mode classique sont retirés : seuls les noms des pièces et Retour au jeu restent.
- Le message « CREDIT ACCEPTED » n'apparaît que durant l'animation d'insertion.
- Les trois autres pièces et leur gameplay, les records séparés et les sauvegardes restent inchangés.

## V1.5 — Easter egg INSERT COIN

- Toucher le texte **★ INSERT COIN ★** en haut du jeu pour ouvrir un monnayeur rétro 8-bit (création graphique, pas photo).
- Pièces françaises stylisées façon arcade, dont **2 francs polygonale 1993** fidèle aux grandes lignes de la référence apportée par le testeur.
- Appuyer sur la pièce déclenche une animation en escalier vers la fente, des petits bips originaux et **CREDIT ACCEPTÉ** ; le nouveau mode démarre après l'animation.
- Pièces **virtuelles**, sans achat ni paiement.
- **Classique** : 3 vies, bonus habituels.
- **1 franc** : 5 vies.
- **2 francs** : 5 vies et bonus traversante activé pendant les 12 premières secondes de jeu.
- **5 francs** : aucune vie perdue, et balle traversante permanente à chaque niveau, y compris après perte d'une balle.
- Les records sont **séparés par mode** (classique, 1F, 2F, 5F). Le record classique historique est conservé dans sa clé d'origine.
- La sauvegarde locale inclut le mode de pièce pour pouvoir reprendre une partie dans les mêmes conditions.
- Depuis une partie en cours, l'ouverture du monnayeur met en pause. **Insérer une nouvelle pièce démarre une nouvelle partie** : la progression précédente est remplacée.
- L'interface du monnayeur est fermable avec Retour au jeu ou ✕, et n'affecte pas la sauvegarde si aucune pièce n'est insérée.
- Depuis la V1.6, insérer **50 centimes** permet de revenir au mode classique.

## V1.4.1 — Easter egg Goldorak

- Utilise le Spazer détouré depuis l'image fournie, sous forme d'une ressource WebP transparente, `spazer.webp` (~3,5 Ko).
- Passage **de haut-gauche vers bas-droite** en environ 4,5 secondes, derrière les briques et sans collision.
- Largeur **98 unités Canvas** sur 360 (~27 % du terrain), opacité **17 %** pour ne pas gêner la partie.
- Tirage indépendant à chaque niveau : **15 % aucun passage**, **65 % un passage**, **20 % deux passages**.
- Le premier passage survient après ~10–25 secondes de jeu actif ; le second, si prévu, après une attente supplémentaire aléatoire.
- L'animation s'arrête en pause et le calendrier des passages fait partie de la sauvegarde ; la reprise n'en génère pas artificiellement davantage.
- Ressource ajoutée au cache offline de la PWA.

## V1.4 — Vitesse et sauvegarde locale

- Chaque niveau augmente la vitesse de balle de départ : environ **3,9 unités/frame** au niveau 1, **6,4 au niveau 7**, plafond **8,6** pour le lancement.
- Les rebonds accélèrent légèrement le jeu, avec vitesse plafonnée à 9,1 unités/frame.
- La partie est enregistrée automatiquement toutes les 2 secondes en jeu, et lors d'une pause, d'un changement de niveau, d'une sortie d'application ou d'une actualisation.
- La sauvegarde inclut score, niveau, vies, briques détruites, balles en mouvement, bonus et effets temporaires.
- Au lancement, un écran **PARTIE SAUVEGARDÉE** propose **CONTINUER** ou **NOUVELLE PARTIE**.
- La reprise s'effectue en pause ; après un **Game Over**, la sauvegarde de partie est supprimée mais le record personnel reste conservé.
- Les données sont enregistrées avec `localStorage` sur le navigateur/appareil utilisé : **pas de synchronisation entre appareils**, et effacer les données de Chrome/PWA peut supprimer la partie.

## V1.3.2 — Passage de niveau visible et actualisation

- Affiche un écran **NIVEAU 02 / PYRAMIDE** avant de lancer le niveau suivant, et ainsi de suite.
- Le bouton **CONTINUER** n'efface plus la partie et ne réinitialise ni score ni vies.
- Vérifie la version du jeu en revenant dans la PWA et périodiquement, recharge si une mise à jour est publiée.
- Pour passer au niveau suivant, détruire toutes les briques du niveau courant ; un Game Over recommence au niveau 1.

## V1.3 — Niveaux variés et bonus rares

- 10 dispositions de briques distinctes : Classique, Pyramide, Damier, Vagues, Forteresse, Invaders, Zigzag, Arcades, Escalier et Final rétro.
- Après le niveau 10, le cycle de formes repart avec difficulté accrue et couleurs décalées.
- Bonus **aléatoires sans plafond par niveau** : 9 % de chance par brique éligible, avec au moins 5 briques détruites entre deux tirages réussis et au maximum deux capsules simultanément à l'écran.
- La progression, les vies restantes et le score sont conservés en passant au niveau suivant. Le record reste dans le stockage local.

## V1.2 — Six bonus à récupérer avec la raquette

Les capsules sont lâchées aléatoirement lors de la destruction des briques :

- **3** : multiballe, deux balles supplémentaires
- **F** : traversante, détruit les briques sans rebondir pendant 12 secondes
- **X** : raquette XXL pendant 15 secondes
- **S** : ralentissement des balles pendant 12 secondes
- **+** : vie supplémentaire (maximum 5 vies)
- **L** : laser automatique pendant 10 secondes (deux tirs réguliers)

Chaque capsule descend jusqu'à la raquette. Les bonus sont volontaires : on peut laisser passer une capsule. Apparition rare (voir les limites V1.3 ci-dessus).

## V1.1 — Bonus et immersion

- Bonus tombant **3** : transforme la balle en **trois balles simultanées** (rattraper le bonus avec la raquette)
- Bonus tombant **F** : **balle traversante** pendant 12 secondes, détruit les briques successives sans rebondir
- Mode plein écran PWA Android et bouton « ⛶ ÉCRAN » en cours de partie
- La barre de navigation système Android reste sous le contrôle du téléphone : un geste peut la réafficher

## V1

- Balle ronde, briques colorées, raquette contrôlée au doigt, à la souris ou aux flèches du clavier
- 3 vies, niveaux progressifs, score et record mémorisé localement
- Sons rétro activables, pause et reprise
- Application PWA installable sur Android, jouable hors ligne après le premier chargement
- Aucun NAS, compte utilisateur, base de données ou serveur applicatif nécessaires

## Publication GitHub Pages

1. Ouvrir **Settings → Pages** dans ce dépôt.
2. Sous **Build and deployment**, sélectionner **Deploy from a branch**.
3. Choisir la branche **main**, dossier **/(root)**, puis **Save**.
4. Ouvrir https://franckmo.github.io/arcadia-breakout/ lorsque GitHub a terminé sa publication.
5. Sur Android, Chrome → menu ⋮ → **Installer l'application** (ou **Ajouter à l'écran d'accueil** selon le navigateur).

## Mise à jour

Le cache PWA est géré dans `sw.js`. À chaque nouvelle version, changer `CACHE_NAME` afin que la nouvelle version remplace l'ancienne.

## Confidentialité

Le record est enregistré uniquement sur l'appareil dans le stockage local du navigateur. Aucune information personnelle n'est collectée.

## Développement

Jeu autonome en HTML5 Canvas, CSS et JavaScript. Aucun outil de compilation ni service externe.