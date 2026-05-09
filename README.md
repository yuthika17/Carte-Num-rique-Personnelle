# Carte-Num-rique-Personnelle
Carte numérique personnelle interactive – Mini-projet de réseautage professionnel
## Introduction

Dans le cadre de ce mini-projet, nous avons conçu une **carte numérique personnelle** destinée au réseautage lors d'événements professionnels. Cette carte constitue une alternative moderne et mémorable au CV classique, permettant de présenter son identité, ses compétences et ses coordonnées de manière visuelle et interactive.
## Explication de la Structure du Code

### Structure HTML

La carte est encapsulée dans un `<article class="card">`, élément sémantique représentant un contenu autonome et réutilisable. Elle se compose de 9 sections dans l'ordre visuel :

|#|Bloc|Balise / Classe|Rôle|
|---|---|---|---|
|①|Bandeau d'en-tête|`.header-band`|Fond dégradé décoratif avec motif de points|
|②|Avatar|`.avatar-wrap > .avatar`|Initiales + point vert de statut online|
|③|Identité|`.identity`|Nom `<h1>` + titre `<p class="role">`|
|④|Tags technos|`.tags > .tag`|Pills de compétences avec effet hover|
|⑤|Statistiques|`.stats > .stat`|Grille CSS 3 colonnes|
|⑥|Bio|`.bio`|Paragraphe de présentation personnelle|
|⑦|Compétences|`.skills`|Barres de progression 100% CSS|
|⑧|Réseaux sociaux|`.socials > .social-btn`|Liens `<a>` avec icônes SVG inline|
|⑨|Bouton CTA|`.cta-wrap > .cta`|Lien `mailto:` stylisé|

---

### Structure CSS

**Variables CSS (`:root`)** Toutes les couleurs, dimensions et rayons sont centralisés en variables personnalisées. Modifier une seule variable suffit pour recolorier toute la carte, ce qui rend le code facilement maintenable.

**Chevauchement de l'avatar — Negative Margin** L'avatar chevauche le bandeau grâce à `margin-top: -42px`, combiné à `position: relative` et `z-index: 2` pour qu'il reste visible au-dessus des autres éléments.

**Pseudo-éléments (`::before` / `::after`)** Utilisés pour créer des éléments décoratifs sans balises HTML supplémentaires : le motif de points sur le bandeau (`::before`), le point de statut online sur l'avatar (`::after`), et les séparateurs verticaux entre les statistiques (`.stat + .stat::before`).

**Barres de progression — CSS pur** Chaque barre est composée d'un `.bar-track` (fond gris) contenant un `.bar-fill` dont la largeur est définie par une classe utilitaire (`.w-95`, `.w-80`…). L'animation `@keyframes grow` fait apparaître la barre de gauche à droite via `transform: scaleX()`, sans aucune ligne de JavaScript.

**Animation d'entrée — Stagger** La carte et ses sections apparaissent en cascade grâce à `@keyframes rise` (fondu + translation + légère mise à l'échelle) avec des `animation-delay` croissants, créant un effet de révélation progressif et élégant.

**CSS Grid** Les statistiques utilisent `display: grid` avec `grid-template-columns: repeat(3, 1fr)` pour une répartition parfaitement équitable en 3 colonnes, sans calculs manuels de largeur.

---

## Conclusion

Ce mini-projet démontre qu'il est possible de créer une interface web moderne, animée et interactive en utilisant uniquement HTML5 et CSS3. Les techniques employées — variables CSS, pseudo-éléments, animations `@keyframes`, CSS Grid, negative margin — illustrent la richesse des standards web actuels sans aucune dépendance externe.

La carte numérique produite constitue un outil de réseautage efficace et mémorable, bien plus vivant qu'un CV traditionnel, tout en restant simple à personnaliser et à maintenir. Ce projet confirme que la maîtrise des fondamentaux reste la base indispensable de tout développement web de qualité.
