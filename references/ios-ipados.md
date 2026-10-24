# iPhone et iPad

## Structure d'écran

- **iPhone** : une seule colonne. Barre de navigation en haut (titre large qui se réduit au défilement), contenu au centre, barre d'onglets en bas (3 à 5 onglets).
- **iPad** : exploiter la largeur. Barre latérale (sidebar) à la place de la barre d'onglets quand il y a beaucoup de sections, vues en colonnes (liste + détail), fenêtres redimensionnables et Split View.
- Respecter les **safe areas** : Dynamic Island / encoche en haut, barre d'accueil en bas. Le fond peut déborder, le contenu interactif non.
- Marges latérales d'environ 16 pt sur iPhone, plus larges sur iPad.

## Typographie (styles de texte, taille par défaut)

| Style | Taille approximative |
|---|---|
| Large Title | 34 pt |
| Title 1 / 2 / 3 | 28 / 22 / 20 pt |
| Headline | 17 pt (semi-gras) |
| Body | 17 pt |
| Callout | 16 pt |
| Subheadline | 15 pt |
| Footnote | 13 pt |
| Caption 1 / 2 | 12 / 11 pt |

Toujours passer par les styles de texte (pas des tailles fixes) pour que Dynamic Type fonctionne. Éviter de descendre sous 11 pt.

## Composants et bons usages

- **Listes** : style insetGrouped pour les réglages et formulaires, style plain pour les longs flux. Lignes d'au moins 44 pt de haut.
- **Boutons** : un seul bouton principal rempli par écran. Les actions secondaires en style discret (texte ou teinté). Actions destructives en rouge, jamais en bouton principal sans confirmation.
- **Feuilles (sheets)** : pour une tâche courte et autonome, avec un bouton de fermeture clair. Hauteurs moyenne et grande possibles.
- **Alertes** : rares, pour une information critique, avec 1 à 2 boutons aux libellés explicites (pas « OK / Annuler » quand « Supprimer / Garder » est plus clair).
- **Recherche** : champ de recherche du système, intégré à la navigation.
- **Menus contextuels** et menus déroulants pour les actions secondaires plutôt que de multiplier les boutons.
- **Champs de saisie** : bon type de clavier (e-mail, numérique, téléphone), remplissage automatique, étiquette visible.
- **Gestes** : glisser pour retourner en arrière depuis le bord gauche, tirer pour actualiser, balayer dans les listes. Ne jamais détourner les gestes système, et toujours offrir une alternative visible aux gestes cachés.

## Mise en page

- Aligner sur une grille de multiples de 4 ou 8 pt.
- Coins arrondis « continus » (squircle) et **concentriques** : le rayon d'un élément imbriqué = rayon du parent moins la marge.
- Espacer généreusement, regrouper par proximité plutôt que par traits de séparation.
- Une seule action principale visible par écran.

## Orientation et adaptation

- Penser aux tailles de classe (compact / régulier). Une mise en page doit se réorganiser, pas seulement s'étirer.
- Tester avec le plus grand réglage de Dynamic Type : le texte doit passer à la ligne ou la mise en page se réorganiser.

## À éviter

- Menu hamburger, onglets de plus de 5 éléments, barre d'onglets qui change selon l'écran.
- Fausses barres système dessinées à la main dans une vraie app.
- Texte blanc sur fond clair, ou gris très pâle sur blanc.
- Animations longues ou qui bloquent l'utilisateur.
