# ARCADIA BREAKOUT 🕹️

Casse-briques rétro original, conçu pour téléphone en portrait, indépendant des autres projets Arcadia.

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