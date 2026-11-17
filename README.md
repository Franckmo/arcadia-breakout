# ARCADIA BREAKOUT 🕹️

Casse-briques rétro original, conçu pour téléphone en portrait, indépendant des autres projets Arcadia.

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