---
name: apple-design
description: Concevoir, coder et critiquer des interfaces selon le design Apple (Human Interface Guidelines, Liquid Glass) pour iPhone, iPad, Mac, Apple Watch, Apple TV et Vision Pro. Produit des maquettes HTML, du code SwiftUI ou des revues de design. À utiliser dès que l'utilisateur parle d'iOS, iPhone, iPad, macOS, watchOS, tvOS, visionOS, SwiftUI, SF Symbols, HIG, Liquid Glass, d'une app "native", "style Apple" ou "comme sur iPhone", même s'il ne cite pas Apple explicitement. Use for any Apple-platform UI/UX design, mockup, SwiftUI or design-review request.
---

# Design Apple (HIG)

Ce skill aide à créer des interfaces qui paraissent natives sur les plateformes Apple. Il couvre trois types de livrables : maquettes HTML, code SwiftUI, conseils et critiques de design.

## Démarche

1. **Cadrer** : identifier la ou les plateformes (iPhone, iPad, Mac, Watch, TV, Vision Pro) et le livrable (maquette, code, critique). Si la plateforme n'est pas claire, la demander, car les règles changent beaucoup d'une plateforme à l'autre.
2. **Lire la référence adaptée** (une seule suffit souvent) :
   - iPhone / iPad → `references/ios-ipados.md`
   - Mac → `references/macos.md`
   - Watch / TV / Vision Pro → `references/watch-tv-vision.md`
   - Code SwiftUI ou effets Liquid Glass → `references/swiftui-liquid-glass.md`
   - Maquette HTML → `references/html-mockups.md`
   - Mesures et couleurs réelles des composants iOS 27 (boutons verre, interrupteur, stepper, listes…) → `references/ios27-components.md`, avec la feuille de style `assets/ios27-components.css` à reprendre dans les maquettes HTML iPhone
   - Les curseurs macOS (SVG) sont dans `assets/macos-pointers/`, leur usage est décrit dans `references/macos.md`.
3. **Vérifier les valeurs récentes si la précision compte** : le HIG évolue à chaque version d'OS. Pour une dimension exacte, un composant récent ou une nouveauté, consulter la page officielle correspondante sur https://developer.apple.com/design/human-interface-guidelines (avec web_fetch ou web_search) plutôt que de se fier uniquement à ces notes.
4. **Produire** le livrable.
5. **Se relire** avec la checklist ci-dessous avant de répondre.

## Principes de fond

- **Hiérarchie** : le contenu passe d'abord, les contrôles le servent. L'œil doit savoir en un coup d'œil ce qui est important.
- **Harmonie** : l'interface s'accorde avec le matériel, les formes arrondies et le système.
- **Cohérence** : composants et comportements familiers, pour que l'utilisateur transfère ce qu'il sait déjà.
- Moins de décoration, plus de clarté. Les contrôles flottent au-dessus du contenu sans le masquer.

## Règles universelles

- **Composants système d'abord** : barres de navigation, onglets, listes, feuilles (sheets), menus. Ils apportent gratuitement accessibilité, adaptation aux tailles et style de la version d'OS.
- **Cibles tactiles d'au moins 44 × 44 pt** sur iPhone et iPad (60 pt sur Vision Pro).
- **Typographie système** (SF Pro, ou SF Compact sur Watch) avec des styles de texte hiérarchisés et le support de Dynamic Type. Pas de police décorative pour l'interface.
- **Couleurs sémantiques** (accent iOS 27 : `#0088FF`) (label, fond, séparateur, couleur d'accent) qui s'adaptent au mode sombre. Ne jamais coder le noir et le blanc en dur dans une vraie app. Contraste de texte d'au moins 4,5:1.
- **Icônes SF Symbols**, alignées sur le texte, avec un style cohérent (poids, rendu).
- **Marges et zones sûres** : respecter les safe areas, ne jamais coller le contenu aux bords ou sous la Dynamic Island, la barre d'accueil ou la barre de titre.
- **Navigation prévisible** : onglets pour les grandes sections (3 à 5 sur iPhone), pile de navigation pour la profondeur, feuilles pour les tâches courtes. Pas de menu hamburger sur iOS, la barre d'onglets le remplace.
- **Retour d'information** : chaque action a un état visible (pressé, chargement, succès, erreur). Haptiques légères et sobres sur iPhone et Watch.
- **Accessibilité** : VoiceOver (libellés), Dynamic Type, Réduire les animations, Réduire la transparence, Contraste accru. Ne jamais transmettre une information par la couleur seule.
- **Langue et localisation** : prévoir des textes plus longs (le français est souvent 20 à 30 % plus long que l'anglais) et la lecture droite-gauche.

## Checklist de relecture

- [ ] La plateforme est respectée (pas d'interface iPhone copiée telle quelle sur Mac ou Watch).
- [ ] Les composants système sont utilisés quand ils existent.
- [ ] Cibles tactiles ≥ 44 pt, textes lisibles, contraste suffisant.
- [ ] Mode clair ET mode sombre fonctionnent.
- [ ] Hiérarchie visuelle claire : un élément principal par écran.
- [ ] Pas de verre empilé sur du verre, pas de teinte Liquid Glass partout.
- [ ] États vides, chargement et erreur prévus.
- [ ] Accessibilité (libellés, Dynamic Type, animations réduites).

## Format des réponses

- **Maquette** : fournir un fichier HTML ouvrable, avec le cadre d'appareil adapté et les deux modes si pertinent.
- **Code** : SwiftUI propre, commenté brièvement, avec une solution de repli (`#available`) si une API récente est utilisée.
- **Critique** : lister les problèmes par ordre d'importance, chacun avec la règle HIG concernée et une correction concrète.
- Citer les principes avec ses propres mots et renvoyer vers la page officielle du HIG plutôt que de recopier son texte.

## Préférences personnelles de l'utilisateur

<!-- Section à compléter avec les règles et goûts propres à l'utilisateur. -->
- (à compléter : couleurs d'accent favorites, style de coins, densité, langue des textes, etc.)
