# Maquettes HTML au style Apple

Objectif : un fichier HTML autonome qui ressemble à une vraie app Apple, en clair et en sombre.

## Règles de base

- **Un seul fichier** HTML avec CSS et JS intégrés. Pas d'image distante.
- **Police** : pile système, sans télécharger SF Pro (sa licence interdit de la redistribuer) :
  `font-family: -apple-system, BlinkMacSystemFont, "SF Pro Text", "SF Pro Display", system-ui, "Helvetica Neue", Arial, sans-serif;`
  Sur un appareil non Apple, la police de repli s'affiche : le dire à l'utilisateur si l'aperçu paraît différent.
- **Icônes** : les SF Symbols ne sont pas redistribuables dans une page web. Utiliser des SVG simples dessinés à la main (trait de 1,5 à 2 px, coins arrondis) ou des emojis en dernier recours, et mentionner le nom du symbole prévu (par exemple `house.fill`) dans un commentaire ou une légende.
- **Mode clair et sombre** : définir toutes les couleurs en variables CSS, avec `@media (prefers-color-scheme: dark)`.
- **Unités** : travailler en pixels CSS égaux aux points Apple (1 pt = 1 px CSS dans la maquette).

## Variables de couleur (valeurs système iOS)

```css
:root {
  --blue:   #007AFF;  --green: #34C759;  --red:   #FF3B30;
  --orange: #FF9500;  --yellow:#FFCC00;  --indigo:#5856D6;

  --bg:            #FFFFFF;   /* systemBackground */
  --bg-grouped:    #F2F2F7;   /* systemGroupedBackground */
  --bg-cell:       #FFFFFF;   /* secondarySystemGroupedBackground */
  --label:         #000000;
  --label-2:       rgba(60,60,67,.6);
  --label-3:       rgba(60,60,67,.3);
  --separator:     rgba(60,60,67,.29);
  --fill:          rgba(120,120,128,.12);
}
@media (prefers-color-scheme: dark) {
  :root {
    --blue:   #0A84FF;  --green: #30D158;  --red:   #FF453A;
    --orange: #FF9F0A;  --yellow:#FFD60A;  --indigo:#5E5CE6;

    --bg:            #000000;
    --bg-grouped:    #000000;
    --bg-cell:       #1C1C1E;
    --label:         #FFFFFF;
    --label-2:       rgba(235,235,245,.6);
    --label-3:       rgba(235,235,245,.3);
    --separator:     rgba(84,84,88,.6);
    --fill:          rgba(120,120,128,.24);
  }
}
```

## Cadres d'appareil (en points)

| Appareil | Largeur × hauteur |
|---|---|
| iPhone (Pro, taille courante) | 393 × 852 |
| iPhone grand format | 430 × 932 |
| iPad (11 pouces) | 834 × 1194 |
| Apple Watch (grand cadran) | environ 205 × 251 |
| Mac, fenêtre type | 900 × 600 minimum |

Pour une maquette iPhone : cadre aux coins très arrondis (rayon d'environ 48 à 55 px), îlot dynamique en haut, barre d'accueil en bas, barre d'état avec heure à gauche et indicateurs à droite. Laisser environ 54 px en haut et 34 px en bas de zone non interactive.

## Composants types

- **Barre de navigation** : titre large (34 px, gras) qui se réduit, bouton de retour en bleu d'accent.
- **Barre d'onglets** : 3 à 5 icônes avec libellé de 10 px, l'onglet actif en couleur d'accent. Style verre flottant : fond translucide `backdrop-filter: blur(20px) saturate(180%)` avec une bordure fine.
- **Liste groupée** : cellules de 44 px minimum, séparateurs décalés après l'icône, coins du groupe arrondis à 10 à 12 px.
- **Bouton principal** : pleine largeur, hauteur 50 px, rayon 14 px ou forme capsule, fond d'accent, texte blanc 17 px semi-gras.
- **Interrupteur** : 51 × 31 px, vert quand activé.
- **Feuille** : arrondie en haut (rayon 12 à 20 px), poignée de 36 × 5 px, fond de grouped.

## Effet verre en CSS (approximation)

```css
.glass {
  background: rgba(255,255,255,.55);
  -webkit-backdrop-filter: blur(24px) saturate(180%);
  backdrop-filter: blur(24px) saturate(180%);
  border: .5px solid rgba(255,255,255,.5);
  box-shadow: 0 8px 30px rgba(0,0,0,.12);
}
@media (prefers-color-scheme: dark) {
  .glass { background: rgba(40,40,45,.55); border-color: rgba(255,255,255,.12); }
}
```

C'est une imitation : prévenir que le vrai rendu Liquid Glass (réfraction, reflets réactifs) n'est pas reproductible en CSS pur.

## Mac dans une maquette

- Fenêtre avec les trois boutons en haut à gauche (rouge `#FF5F57`, jaune `#FEBC2E`, vert `#28C840`), barre latérale translucide, barre d'outils.
- Utiliser les curseurs de `assets/macos-pointers/` pour illustrer les états de survol (voir `macos.md`). Les intégrer en SVG en ligne ou via `cursor: url(data:image/svg+xml;...) 4 4, auto` si le fichier doit rester autonome.

## Soigner la maquette

- Contenu réaliste (noms, montants, dates dans la langue de l'utilisateur) plutôt que « Lorem ipsum ».
- Plusieurs états si utile : vide, chargement, erreur, rempli.
- Interactions simples en JS (changement d'onglet, ouverture de feuille) pour donner une impression de vraie app.
- Préciser en fin de réponse ce qui est approximatif (police de repli, icônes, verre).
