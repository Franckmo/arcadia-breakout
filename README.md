# ARCADIA BREAKOUT 🕹️

Casse-briques rétro original, conçu pour téléphone en portrait, indépendant des autres projets Arcadia.

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