# SwiftUI et Liquid Glass

Liquid Glass est le matériau introduit en 2025 avec les systèmes « 26 » (iOS 26, iPadOS 26, macOS Tahoe 26, watchOS 26, tvOS 26) et repris sur visionOS. Les versions suivantes l'affinent : vérifier la page « Materials » du HIG et la documentation SwiftUI avant de s'appuyer sur un détail d'API.

## Principes d'usage

- **Navigation et contrôles, pas contenu** : le verre sert à la couche qui flotte au-dessus du contenu (barres, boutons flottants, onglets). Ne pas en faire le fond des cartes de contenu ni des listes.
- **Composants système d'abord** : en recompilant avec le SDK récent, barres de navigation, barres d'onglets, barres d'outils, feuilles, menus et champs de recherche adoptent le verre automatiquement. Ne pas les redessiner ni ajouter un fond personnalisé par-dessus.
- **Pas de verre sur du verre** : éviter d'empiler des couches de verre, et grouper les éléments de verre voisins dans un conteneur.
- **Teinte avec parcimonie** : réserver la couleur à l'action principale, pas à tous les boutons.
- **Lisibilité d'abord** : le texte sur du verre doit garder un bon contraste, avec le contenu qui défile derrière. Tester sur fonds clairs, sombres et chargés.
- **Accessibilité** : le système adapte le verre quand l'utilisateur active Réduire la transparence ou Contraste accru. Ne pas contourner ces réglages.

## Code de base (iOS 26 et suivants)

```swift
import SwiftUI

struct ExempleView: View {
    var body: some View {
        NavigationStack {
            List(1..<20) { i in
                Text("Élément \(i)")
            }
            .navigationTitle("Accueil")      // barre système : verre automatique
            .toolbar {
                ToolbarItem(placement: .primaryAction) {
                    Button("Ajouter", systemImage: "plus") { }
                }
            }
        }
    }
}
```

Boutons et effets personnalisés :

```swift
// Style de bouton verre fourni par le système
Button("Continuer") { }
    .buttonStyle(.glass)

// Action principale mise en avant
Button("Valider") { }
    .buttonStyle(.glassProminent)

// Effet verre sur une vue personnalisée
Label("Lecture", systemImage: "play.fill")
    .padding()
    .glassEffect(.regular.interactive(), in: .capsule)

// Plusieurs éléments de verre proches : les grouper
GlassEffectContainer(spacing: 16) {
    HStack(spacing: 16) {
        Button("Photo", systemImage: "camera") { }.glassEffect()
        Button("Vidéo", systemImage: "video") { }.glassEffect()
    }
}
```

Variantes de verre : `.regular` (usage courant) et `.clear` (plus transparent, sur contenu riche en médias avec un voile sombre), ainsi qu'une teinte possible avec `.tint(_:)`.

## Repli pour les versions antérieures

```swift
extension View {
    @ViewBuilder
    func carteFlottante() -> some View {
        if #available(iOS 26, *) {
            self.padding().glassEffect(in: .rect(cornerRadius: 20))
        } else {
            self.padding()
                .background(.regularMaterial,
                            in: RoundedRectangle(cornerRadius: 20, style: .continuous))
        }
    }
}
```

Matériaux classiques : `.ultraThinMaterial`, `.thinMaterial`, `.regularMaterial`, `.thickMaterial`, `.ultraThickMaterial`.

## Bonnes pratiques SwiftUI (toutes versions)

- **Typographie** : `.font(.body)`, `.title`, `.headline`… pour profiter de Dynamic Type. Éviter `.font(.system(size: 17))` fixe.
- **Couleurs** : `Color.primary`, `Color.secondary`, `Color(.systemBackground)`, `.accentColor` / `.tint`. Définir les couleurs personnalisées dans le catalogue d'assets avec variantes clair et sombre.
- **Icônes** : `Image(systemName:)` avec `.symbolRenderingMode(.hierarchical)` ou `.palette` selon le besoin, et `Label` pour associer texte et icône.
- **Mise en page** : `NavigationStack` / `NavigationSplitView`, `TabView`, `List`, `Form`, `Grid`. Éviter les tailles fixes ; préférer `frame(maxWidth: .infinity)`, `ViewThatFits`, classes de taille (`horizontalSizeClass`).
- **Zones sûres** : laisser SwiftUI les gérer, n'utiliser `.ignoresSafeArea()` que pour les fonds.
- **Cibles** : `.frame(minWidth: 44, minHeight: 44)` ou `.contentShape(Rectangle())` pour les zones tactiles petites.
- **Accessibilité** : `.accessibilityLabel`, `.accessibilityHint`, `@Environment(\.accessibilityReduceMotion)`, `@Environment(\.dynamicTypeSize)`.
- **Animation** : `withAnimation(.snappy)` ou `.spring` courts, avec le respect de Réduire les animations.
- **Aperçus** : toujours fournir `#Preview` en clair et en sombre, avec un grand réglage de Dynamic Type.

## Multi-plateforme

- Écrire le code une fois avec des composants adaptatifs, puis ajouter `#if os(macOS)` / `#if os(iOS)` seulement pour ce qui diffère (raccourcis clavier, menus, survol).
- Sur Mac : `.keyboardShortcut`, `Commands`, `.onHover`, `Settings { }`.
- Sur Watch : `TabView` avec style page, `.digitalCrownRotation`.
- Sur Vision Pro : `.ornament`, fenêtres avec verre, cibles 60 pt.
