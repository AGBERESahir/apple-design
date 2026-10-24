# Apple Watch, Apple TV et Vision Pro

## Apple Watch (watchOS)

Interactions brèves : quelques secondes, un coup d'œil, un geste.

- **Une tâche par écran**, contenu minimal, texte court. Si l'info tient en une phrase, ne pas en faire un écran de paramètres.
- **Navigation** : pile verticale, onglets en pages défilantes, ou liste. Le contenu défile verticalement avec la **Digital Crown**.
- **Police** : SF Compact (système). Tailles par styles de texte. Éviter de petits textes secondaires.
- **Fond noir** : l'écran est OLED, le noir se fond avec le bord du boîtier. Mettre le contenu sur fond sombre, avec des couleurs vives mais peu nombreuses.
- **Cibles tactiles** généreuses (au moins la taille d'un doigt, boutons larges pleine largeur pour l'action principale).
- **Retours** : haptiques légères, animations courtes. Pas de longues attentes sans indicateur.
- **Complications et widgets** : montrer une information utile d'un regard, sans interaction nécessaire.
- **Éviter** : saisie de texte longue, formulaires, contenu dense, dépendance à un iPhone sans le signaler.

## Apple TV (tvOS)

Interface vue à 3 mètres, pilotée à la télécommande, sans pointeur.

- **Moteur de focus** : un seul élément est en focus à la fois, agrandi et surélevé avec un effet de parallaxe. Chaque élément interactif doit avoir un état focus évident.
- **Navigation directionnelle** (haut, bas, gauche, droite) prévisible, sans élément inatteignable.
- **Marges de zone sûre** : garder le contenu à l'écart des bords (environ 60 pt sur les côtés et 90 pt en haut et en bas sur une grille 1920 × 1080).
- **Texte** grand et à fort contraste : corps d'au moins environ 29 pt, titres bien plus grands. Pas de texte fin.
- **Visuels** riches : images plein cadre, affiches, arrière-plans de qualité, avec un voile pour garder le texte lisible.
- **Saisie** minimale : préférer sélection, dictée, ou connexion via un autre appareil.
- **Éviter** : petits boutons, menus profonds, textes denses, lecture exigeant de se rapprocher.

## Vision Pro (visionOS)

Interface spatiale pilotée par les yeux (regard), les mains (pincer) et la voix.

- **Fenêtres** flottantes dans l'espace, avec le matériau verre : elles laissent voir l'environnement. Éviter les fonds opaques pleins qui coupent l'utilisateur de la pièce.
- **Cibles** généreuses : environ **60 pt** minimum, espacées, avec un état de survol au regard (effet de surbrillance).
- **Ornements** : barres d'outils et contrôles attachés au bord de la fenêtre plutôt qu'à l'intérieur.
- **Profondeur** : superposer des plans avec parcimonie, éviter les mouvements brusques ou forts à la périphérie, éviter de forcer la tête à tourner.
- **Texte** légèrement plus gros que sur iPhone, graisse suffisante, contraste soigné sur du verre.
- **Confort** : éviter les animations qui bougent tout le champ de vision, laisser l'utilisateur contrôler l'immersion.
- **Éviter** : les éléments collés aux bords du champ de vision, les cibles minuscules, les fonds sombres plein écran sans raison.

## Points communs

- Utiliser les composants système de la plateforme, qui gèrent focus, regard, Crown et accessibilité.
- Adapter le contenu à la plateforme au lieu de copier l'interface iPhone.
- Garder l'accessibilité : VoiceOver, taille de texte, contrastes, réduction du mouvement.
