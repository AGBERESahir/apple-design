# Composants iOS 27 (mesures du kit Figma)

Valeurs lues dans l'export SVG du kit « iOS and iPadOS 27 » fourni par l'utilisateur (mode clair). Les mesures sont en points. La feuille de style `assets/ios27-components.css` en donne une version prête à l'emploi. Le verre y est une approximation CSS : le vrai rendu combine plusieurs couches avec des modes de fusion que le CSS ne reproduit pas.

## Couleurs (mode clair)

| Rôle | Valeur |
|---|---|
| Accent (bleu iOS 27) | `#0088FF` (l'ancien bleu iOS était `#007AFF`) |
| Vert (interrupteur activé) | `#34C759` |
| Texte principal / glyphes | `#1A1A1A` |
| Texte secondaire (détails) | `#727272` |
| Texte d'indication (placeholder) | `#BFBFBF` |
| Étiquettes secondaires, titres de section | `rgba(60,60,67,0.6)` |
| Séparateur, point de page inactif | `rgba(60,60,67,0.3)` |
| Remplissage de contrôle (stepper) | `rgba(118,118,128,0.12)` |
| Fond de champ, ligne sélectionnée | `#EDEDED` |
| Piste de la barre de progression | `rgba(120,120,120,0.2)` |

## Mesures des composants

| Composant | Dimensions | Détails |
|---|---|---|
| Bouton verre rond (retour, icône seule) | 44 × 44, ou 48 × 48 dans une barre | Rayon = moitié. Glyphe `#1A1A1A`. |
| Bouton verre capsule texte (« Edit ») | 60 × 44 | Rayon 22. Texte 17 pt `#1A1A1A`. |
| Barre verre multi-boutons | largeur libre × 44 | Rayon 22. |
| Bouton capsule rempli, petit | 66 × 28 | Fond `#0088FF`, texte et icône blancs (« Play »). |
| Bouton capsule rempli, grand | environ 86 × 50 | Fond `#0088FF`, texte blanc 17 pt. |
| Bouton validation (coche) | environ 51 × 51 | Cercle `#0088FF`, coche blanche. |
| Interrupteur | 64 × 28 | Piste verte `#34C759`, curseur blanc 38 × 24, marge de 2, rayon 12. |
| Stepper (− / +) | 92 × 32 | Deux moitiés de 46, rayon 16, séparateur 1 × 24, glyphes noirs. |
| Points de pagination | pastille 112 × 24, points de 8 | Espacement de 16 entre centres, actif noir, inactif `rgba(60,60,67,.3)`. |
| Barre de progression | 370 × 4 | Rayon 2, remplissage `#0088FF`. |
| Indicateur d'activité | 8 bâtons de 5 × 13 | Rayon 2,5, opacité de 0,15 à 1 en tournant. |
| Champ de recherche (verre) | 200 à 300 × 44 | Rayon 22, loupe à gauche, micro à droite, indication `#BFBFBF` / micro `#727272`. |
| Ligne de liste | hauteur 44 | Icône 20 × 20 à gauche en `#0088FF`, titre 17 pt `#1A1A1A`, détail 17 pt `#727272` à droite. |
| Ligne sélectionnée | capsule 300 × 44 | Fond `#EDEDED`, rayon 22. |
| En-tête de section | texte `rgba(60,60,67,.6)` | Détail à droite avec chevron bas. |
| Sélecteur « Label ⌃⌄ » | texte 17 pt | Texte `#0088FF` avec double chevron. |
| Tuile / carte de verre | 160 × 160 | Rayon 23 à 34 selon l'usage. |

## Le verre

Un bouton verre rond empile quatre couches dans cet ordre :

1. noir à 25 %,
2. blanc à 25 %,
3. gris `#444444` à 60 % en mode « plus-lighter »,
4. `#F8F8F8` à 20 % en mode « luminosité ».

Ombres : un flou vertical très léger (décalage 8, flou 15, opacité 2 %), un fin liseré clair d'environ 0,5 de large (`#E8E8E8`), et deux bords latéraux de 1,25 (`#D0D0D0`). Résultat : un disque translucide et lumineux, sans contour dur.

En CSS, utiliser `backdrop-filter: blur(20px) saturate(180%)` avec un fond blanc semi-transparent, un liseré très léger et une ombre douce (voir `assets/ios27-components.css`).

## Icône de retour (chevron gauche)

Dans un cadre 44 × 44, le chevron fait environ 11 × 19, en `#1A1A1A`, dessiné avec un trait épais aux extrémités arrondies. Équivalent SVG simple :

```html
<svg viewBox="0 0 44 44" width="44" height="44"><path d="M26 13l-9 9 9 9" fill="none" stroke="#1A1A1A" stroke-width="2.6" stroke-linecap="round" stroke-linejoin="round"/></svg>
```

## À retenir pour les maquettes

- Le bleu d'accent iOS 27 est `#0088FF` (plus saturé que l'ancien `#007AFF`).
- Les boutons de barre sont des cercles ou capsules de **verre**, séparés les uns des autres, pas des icônes nues.
- Les cibles tactiles restent à 44 pt minimum, même quand le bouton rempli fait 28 pt de haut (le petit « Play » est un style compact à réserver aux contextes serrés).
- Les valeurs du mode sombre ne figurent pas dans cet export. Les chercher dans le kit avant d'inventer.
