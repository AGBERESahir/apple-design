# apple-design

Un skill Claude pour concevoir, coder et critiquer des interfaces qui paraissent natives sur les plateformes Apple (iPhone, iPad, Mac, Apple Watch, Apple TV, Vision Pro), en s'appuyant sur les Human Interface Guidelines et le style Liquid Glass.

Le skill produit trois types de livrables :

- **Maquettes HTML** ouvrables dans un navigateur, avec cadre d'appareil et modes clair/sombre
- **Code SwiftUI** propre, avec solution de repli `#available` pour les API récentes
- **Critiques de design** classées par importance, avec la règle HIG concernée et une correction concrète

## Installation

**Claude.ai**

1. Compresser le dossier du repo en `apple-design.zip` (le fichier `SKILL.md` doit être à la racine du ZIP)
2. Aller dans *Settings → Capabilities → Skills*
3. Importer le ZIP et activer le skill

**Claude Code**

```bash
git clone https://github.com/AGBERESahir/apple-design.git ~/.claude/skills/apple-design
```

## Utilisation

Le skill se déclenche automatiquement dès que la demande parle d'iOS, d'iPhone, de SwiftUI, de HIG, de Liquid Glass ou d'une app « style Apple ». Quelques exemples :

- « Fais-moi une maquette HTML d'un écran de réglages pour iPhone »
- « Écris une vue SwiftUI avec une barre d'onglets et une liste »
- « Critique cet écran selon le HIG » (avec une capture jointe)
- « Adapte cette interface pour Mac »

## Structure

```
apple-design/
├── SKILL.md                      # Point d'entrée : démarche, règles, checklist
├── references/
│   ├── ios-ipados.md
│   ├── macos.md
│   ├── watch-tv-vision.md
│   ├── swiftui-liquid-glass.md
│   ├── html-mockups.md
│   └── ios27-components.md       # Mesures et couleurs des composants iOS 27
└── assets/
    ├── ios27-components.css      # Feuille de style pour les maquettes iPhone
    └── macos-pointers/           # Curseurs macOS (SVG)
```

`SKILL.md` sert de routeur : Claude y lit la démarche, puis ouvre uniquement la référence adaptée à la demande.

## Sources et fiabilité

Les valeurs de design évoluent à chaque version d'OS. Les références de ce repo sont des notes de travail, pas la documentation officielle. Pour une dimension exacte ou un composant récent, la source faisant foi est le [HIG officiel](https://developer.apple.com/design/human-interface-guidelines).

- Dernière vérification des mesures : *à compléter (mois/année)*
- Sources des mesures iOS 27 : *à compléter*

## Contribuer

Les corrections sont bienvenues, surtout :

- les mesures ou couleurs erronées (merci d'indiquer la source)
- les cas où le skill produit un résultat peu natif
- les exemples de maquettes ou de code SwiftUI de référence

Ouvrir une issue ou une pull request.


## Avertissement

Ce projet est indépendant et n'est ni affilié ni approuvé par Apple Inc. Apple, iPhone, iPad, Mac, Apple Watch, Apple TV, Vision Pro, SF Symbols et Liquid Glass sont des marques ou noms appartenant à Apple Inc.
