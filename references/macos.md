# Mac (macOS)

Le Mac se pilote au pointeur et au clavier, avec des fenêtres redimensionnables et des écrans larges. Ne pas y transposer une interface iPhone telle quelle.

## Structure

- **Fenêtres** redimensionnables, avec une taille minimale raisonnable. Plusieurs fenêtres possibles.
- **Barre latérale** (sidebar) à gauche pour la navigation principale, souvent translucide. Contenu au centre, panneau d'inspecteur optionnel à droite.
- **Barre d'outils** (toolbar) en haut de la fenêtre : actions fréquentes, recherche, titre. Boutons groupés par fonction.
- **Barre de menus** : toutes les commandes de l'app y figurent (Fichier, Édition, Présentation, Fenêtre, Aide). Une action disponible ailleurs doit aussi l'être dans les menus.
- **Raccourcis clavier** standards : ⌘N, ⌘O, ⌘S, ⌘W, ⌘Z, ⇧⌘Z, ⌘C/⌘V/⌘X, ⌘F, ⌘, (réglages). Afficher le raccourci à côté de chaque commande de menu.

## Dimensions et densité

- Les contrôles sont plus petits que sur iPhone (hauteur de bouton d'environ 22 à 28 pt) car le pointeur est précis.
- Texte courant d'environ 13 pt (corps système), titres de section 13 pt en gras ou 11 pt en capitales discrètes pour les légendes.
- Espacements plus serrés que sur iOS, mais respirer entre les groupes.
- Coins de fenêtre très arrondis, contrôles avec rayons modérés.

## Interactions propres au Mac

- **Survol** : les éléments interactifs réagissent au survol (surbrillance, infobulle après un court délai).
- **Clic droit / Ctrl-clic** : menus contextuels sur les éléments pertinents.
- **Glisser-déposer** : pour réorganiser, importer, exporter.
- **Sélection multiple** avec ⇧ et ⌘.
- **Focus clavier** : navigation par Tab, anneau de focus visible.
- **Trackpad** : défilement inertiel, pincer pour zoomer, balayer entre pages.
- **Préférences** : fenêtre de réglages séparée (⌘,), organisée en onglets avec icônes.

## Apparence

- Suivre le mode clair / sombre et la couleur d'accent choisie par l'utilisateur dans les réglages du système.
- Matériaux translucides (barre latérale, barre d'outils) avec un contraste suffisant du texte au-dessus.
- Avec Liquid Glass (macOS Tahoe et suivants), les barres et contrôles flottants adoptent le verre automatiquement avec les composants système. Voir `swiftui-liquid-glass.md`.

## Curseurs disponibles dans ce skill

Fichiers SVG 32 × 32 px dans `assets/macos-pointers/`, à utiliser dans les maquettes HTML (par exemple en `cursor: url(...)` ou en image positionnée) pour montrer l'état d'un élément.

| Situation | Fichier |
|---|---|
| Pointeur normal | `default.svg` (variante : `default-alt.svg`) |
| Lien, bouton cliquable | `hand-pointing.svg` |
| Élément saisissable | `hand-open.svg` |
| Élément en cours de déplacement | `hand-grabbing.svg` |
| Champ de texte | `text-cursor.svg` |
| Déplacer | `move.svg` |
| Viseur / sélection précise | `cross.svg` |
| Zoom avant / arrière | `zoom-in.svg` / `zoom-out.svg` |
| Chargement | `beachball.svg` |
| Redimensionner (haut, bas, gauche, droite) | `resize-up.svg`, `resize-down.svg`, `resize-left.svg`, `resize-right.svg` |
| Redimensionner (axes) | `resize-up-down.svg`, `resize-left-right.svg`, `resize-north-south.svg`, `resize-west-east.svg` |
| Redimensionner (coins) | `resize-north-east-south-west.svg`, `resize-north-west-south-east.svg` |

Règle de base : montrer un curseur dans une maquette seulement quand il aide à comprendre l'interaction (survol d'un bouton, bord de fenêtre, champ de texte). Ne pas en parsemer tout l'écran.

## À éviter

- Cibles trop grandes et marges de style tactile, ou au contraire minuscules sans survol ni focus.
- Fenêtre qui ne peut pas être redimensionnée ou qui plante sous une taille minimale.
- Actions uniquement accessibles par un geste ou un bouton, sans commande de menu ni raccourci.
- Barre de menus vide, ou menus qui ne reflètent pas les actions de l'app.
