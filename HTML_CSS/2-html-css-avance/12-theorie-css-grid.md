<!-- omit in toc -->
# Grid (débutant)

:exclamation: Work in progress

<!-- omit in toc -->
## Introduction

On a vu flexbox pour nos mises en page, mais pour des interface un peu plus complexe on va devoir utiliser Grid. Il s'agit de découper notre page en une grille et de définir précisément chaque colone et ligne. Grid est un module CSS crée spécialement pour répondre aux besoins des designer qui devait "hacker" float et flexbox pour arriver à leurs fins.

Attention ça va devenir plus complexe, mais le but n'est pas de maîtriser Grid dès le début, mais de voir son potentiel et d'apprendre à l'utiliser au fur et à mesure de tes projets.

<!-- omit in toc -->
## Table des matières

- [Outils de développement](#outils-de-développement)
- [Quelques concepts de base](#quelques-concepts-de-base)
  - [Grid container](#grid-container)
  - [Grid Item](#grid-item)
  - [Grid Line](#grid-line)
  - [Grid Cell](#grid-cell)
  - [Grid Track](#grid-track)
  - [Grid Area](#grid-area)
- [Création d'une grille](#création-dune-grille)
  - [Grid-container](#grid-container-1)
    - [display](#display)
    - [grid-template-columns \& grid-template-rows](#grid-template-columns--grid-template-rows)
      - [La fonction repeat()](#la-fonction-repeat)
      - [L'unité fr en CSS](#lunité-fr-en-css)
    - [grid-template-areas](#grid-template-areas)
    - [grid-template](#grid-template)
    - [grid-gap](#grid-gap)
    - [justify-content](#justify-content)
    - [align-content](#align-content)
  - [Grid-item](#grid-item-1)
    - [grid-column](#grid-column)
    - [grid-row](#grid-row)
    - [grid-area](#grid-area-1)
    - [Utilisation du slash](#utilisation-du-slash)
- [Flexbox vs Grid](#flexbox-vs-grid)
- [Quelques liens utiles](#quelques-liens-utiles)

## Outils de développement

Avant de commencer à créer notre grille, il est important de savoir comment la visualiser.

Pour vérifier que notre grille est bien construite, on peut utiliser les outils de développement de notre navigateur. Pour ce faire, il suffit de faire un clic droit sur notre page et de sélectionner **inspecter**. Ensuite on clique sur l'onglet **Layout**. Là on peut afficher notre grille et voir différentes options d'affichages (comme les noms des lignes, des colonnes, etc...). Tu peux aussi cliquer sur la petite bulle "grid" à côté d'un élément HTML dans ton code.

## Quelques concepts de base

### Grid container

Il s'agit de l’élément qui aura la propriété **display:grid**. C'est le parent des **grid items**

```html
<div class="grid-container">
  <div class="grid-item"></div>
  <div class="grid-item"></div>
</div>
```

### Grid Item

C'est l'enfant direct du **grid container**.

```html
<div class="grid-container">
  <div class="grid-item">
    <p>Je ne suis pas un grid item!</p>
  </div>
  <div class="grid-item"></div>
</div>
```

### Grid Line

C'est la ligne qui divise la structure de notre grille. Elle peut-être horizontale ou verticale.

![grid-line](./img/12/grid/terms-grid-line.svg)

### Grid Cell

C'est l'espace contenu entre 4 grid line.

![grid-cell](./img/12/grid/terms-grid-cell.svg)

### Grid Track

C'est l'espace entre 2 grid line adjacente. On peut voir ça comme une colone ou une rangée. 

![grid-track](./img/12/grid/terms-grid-track.svg)

### Grid Area

L'espace compris entre 4 grid line. Il peut être composé de plusieurs grid cell.

![grid-area](./img/12/grid/terms-grid-area.svg)

## Création d'une grille

Voyons ensemble les propriétés CSS qui nous permettent de créer une grille.

### Grid-container

Tout d'abord les propriétés qui vont s'appliquer à notre grid container.

#### display

On va définir notre élément principale comme grid.

```css
.grid-container{
  display: grid;
}
```

[Voir en pratique](https://www.w3schools.com/css/css_grid.asp)

#### grid-template-columns & grid-template-rows

Ces deux propriétés vont définir la taille et le nom de nos colonnes et rangées. Il suffit de placer plusieurs valeurs à la suite, chaque valeur représentera la largeur/hauteur de nos colones ou rangés. Cette valeur peut-être donnée en **px**, en **%** ou en **fr** .

Par exemple, pour un grid de 3 colonnes de taille égale :

```css
.grid-container {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
}
```

Ou bien encore pour une grid avec 5 colonnes et 3 rangées de tailles variables :

```css
.grid-container {
  display: grid;
  grid-template-columns: 40px 50px auto 50px 40px;
  grid-template-rows: 25% 100px auto;
}
```

![template-example](./img/12/grid/template-columns-rows-01.svg)

> Par défaut ces lines auront une valeur numérique positive et négative qui leurs sont attribués comme noms. Mais il est possible de définir leurs noms. Voyons cela.

Pour donner un nom aux lines il suffit de placer ce nom devant la valeur et entre crochets ([...]).

```css
.grid-container {
  grid-template-columns: [first] 40px [line2] 50px [line3] auto [col4-start] 50px [five] 40px [end];
  grid-template-rows: [row1-start] 25% [row1-end] 100px [third-line] auto [last-line];
}
```

![template-example](./img/12/grid/template-column-rows-02.svg)

##### La fonction repeat()

La fonction repeat() est utilisée avec les propriétés grid-template-columns et grid-template-rows pour répéter plusieurs fois une série de définitions de colonnes ou de rangées.

**Répéter des colonnes ou des rangées de taille identique :** Imaginons que tu veuilles créer 5 colonnes de la même taille. Au lieu d'écrire 1fr 1fr 1fr 1fr 1fr, tu peux simplement utiliser repeat(5, 1fr).

```css
.grid-container {
  grid-template-columns: repeat(5, 1fr);
}
```

> Cela aura pour but de créer 5 colonnes de taille égale.

**Répéter des motifs :** Tu peux également répéter des motifs. Disons que tu veux un motif alterné : une colonne de 2fr suivie d'une colonne de 1fr, et que tu veux répéter ce motif 3 fois. Plutôt que d'écrire `2fr 1fr 2fr 1fr 2fr 1fr`, tu peux simplifier avec `repeat(3, 2fr 1fr)`.

```css
.grid-container {
  grid-template-columns: repeat(3, 2fr 1fr);
}
```

**Combinaison avec d'autres valeurs :** Tu peux combiner la fonction repeat() avec d'autres valeurs. Par exemple, si tu veux une colonne de 100px suivie de 4 colonnes de taille égale. Tu peux écrire `100px repeat(4, 1fr)`.

```css
.grid-container {
  grid-template-columns: 100px repeat(4, 1fr);
}
```

La fonction `repeat()` te permet d'éviter de répéter manuellement des motifs ou des tailles identiques. C'est particulièrement utile pour les grands systèmes de grille où tu as besoin de nombreuses colonnes ou rangées similaires. Cela rend ton code plus propre et plus lisible.

##### L'unité fr en CSS

Lorsqu'on parle de CSS Grid, on entend souvent parler de l'unité `fr`, mais qu'est-ce que c'est exactement ? L'unité `fr` est une unité de mesure fractionnelle spécifique au Grid Layout.

**Fraction du disponible :** Le `fr` représente une fraction de l'espace disponible dans le container. Si tu as un espace total et que tu le divises en plusieurs parties, chaque partie est une fraction (ou `fr`) de cet espace total.

**Répartition de l'espace :** Supposons que tu as un grid container et que tu veux le diviser en 3 colonnes de taille égale. Tu peux utiliser `1fr` `1fr` `1fr` pour chaque colonne. Chaque colonne prendra alors un tiers (1/3) de l'espace total.

```css
.grid-container{
  grid-template-columns: 1fr 1fr 1fr;
}
```

> Ceci aura pour but de prendre 1/3 de l'espace disponible.

**Combinaison avec d'autres unités :** L'avantage du `fr` est qu'il fonctionne bien avec d'autres unités comme `px`, `%`, `em`, etc. Si tu veux une colonne de 200px et que les deux autres se partagent l'espace restant de manière égale, tu peux faire :

```css
.container {
    grid-template-columns: 200px 1fr 1fr;
}
```

L'unité `fr` est super pratique pour créer des mises en page réactives sans avoir à faire de calculs compliqués. Elle s'adapte automatiquement à l'espace disponible, ce qui la rend idéale pour les designs flexibles et adaptatifs.

#### grid-template-areas

Il est également possible de définir notre grid avec le nom que l'on donne à nos grid-area. pour ce faire on écrit le nom de notre grid-area suivi d'un espace et d'une autre grid-area ou d'un point. Si on place un point cela signifie qu'on définit une grid cell vide. 

```css
  .grid-container {
    display: grid;
    grid-template-columns: 1fr 1fr 0.5fr 1fr;
    grid-template-rows: auto;
    grid-template-areas: 
      "header header header header"
      "main main . sidebar"
      "footer footer footer footer";
    gap: 10px;
  }

[class^="item-"]{
  height:50px;
}

.item-a {
  grid-area: header;
  background-color: coral;
}
.item-b {
  grid-area: main;
  background-color: yellowgreen;
}
.item-c {
  grid-area: sidebar;
  background-color: crimson;
}
.item-d {
  grid-area: footer;
  background-color: dodgerblue;
}
```

![grid-template-area](./img/12/grid/dddgrid-template-areas.svg)

#### grid-template

Permet d'écrire **grid-template-rows**, **grid-template-columns** et **grid-template-areas** en une seule ligne. C'est un peu plus complexe à comprendre à première vue, voici un exemple.

```css
.grid-container {
  grid-template:
    [row1-start] "header header header" 25px [row1-end]
    [row2-start] "footer footer footer" 25px [row2-end]
    / auto 50px auto;
}
```

Voici ce qu'on obtient:

- 2 rangées de 25 pixels chacune.
- 3 colonnes dont la colonne du milieu a une largeur fixe de 50 pixels, et les colonnes de gauche et de droite s'adaptent à leur contenu.
- Les trois colonnes de la première rangée sont assignées à la zone "header".
- Les trois colonnes de la deuxième rangée sont assignées à la zone "footer".
- Des lignes nommées sont utilisées pour mieux identifier les rangées.

#### grid-gap

Il est possible de gérer l'intersection entre les colonnes et rangées. C'est ce qu'on appel le **gap**. On peut mettre une valeur en **px**.

```css
.grid-container {
  display: grid;
  grid-gap: 50px;
}
```

> Dans ce cas-ci, tous les espaces entres colonnes et rangées auront un gap de 50px. Mais il est possible de définir les rangée et puis les colonnes en plaçant 2 valeurs à la suite. Il est également possible d'utiliser les propriétés **grid-row-gap** et **grid-columns-gap**.

![gap](./img/12/grid/dddgrid-gap.png)

#### justify-content

Permet d'aligner l'entièreté de la grille à l'intérieur du container. Prends les valeurs: **space-evenly**, **space-around**, **space-between**, **strech**, **center**, **start** et **end**.

[Voir en pratique](https://css-tricks.com/snippets/css/complete-guide-grid/#aa-justify-content)

#### align-content

Permet d'aligner l'entièreté de la grille de façon verticale à l'intérieur du container. Prends les valeurs: **space-evenly**, **space-around**, **space-between**, **strech**, **center**, **start** et **end**.

[Voir en pratique](https://css-tricks.com/snippets/css/complete-guide-grid/#aa-align-content)

### Grid-item

Maintenant que l'on a vu comment définir notre grille, voyons comment placer les éléments dedans.

#### grid-column

Cette propriété permet de définir à partir de quelle colonne commence et à laquelle se termine notre élément. Pour ce faire on indique une valeur de départ et on sépare celle de fin par un slash (/)

```css
.grid-item{
  grid-column: 1 / 5;
}
```

On peut également utiliser "span" pour indiquer combien de colonnes ou de rangées un élément doit occuper. Si tu veux qu'un élément s'étende sur plusieurs colonnes, tu utiliseras span suivi du nombre de colonnes que tu souhaites qu'il couvre.

```css
.item {
    grid-column: span 3;
}
```

Supposons que tu veuilles que ton élément commence à la 2ème colonne et s'étende sur 2 colonnes :

```css
.grid-item2{
  grid-column: 2 / span 2;
}
```

> :bulb: grid-column est une propriété raccourcie pour **grid-column-start** et **grid-column-end**.

#### grid-row

Fonctionne comme *grid-column* mais pour les rangées.

> :bulb: grid-row est une propriété raccourcie pour **grid-row-start** et **grid-row-end**.

#### grid-area

[Comme vu plus haut](#grid-template-areas), avec grid-template-areas, tu peux définir des zones dans ton grid. Par exemple :

```css
.container {
    grid-template-areas:
    "header header header"
    "main main sidebar"
    "footer footer footer";
}
```

Une fois ces zones définies, tu peux assigner un élément à l'une de ces zones avec grid-area :

```css
.header {
    grid-area: header;
}

.main {
    grid-area: main;
}

.sidebar {
    grid-area: sidebar;
}

.footer {
    grid-area: footer;
}
```

`grid-area` peut aussi être utilisé pour définir rapidement où un élément commence et se termine, à la fois en termes de colonnes et de rangées. La syntaxe est la suivante :

```css
grid-area: row-start / column-start / row-end / column-end;
```

```css
.item {
    grid-area: 1 / 2 / 3 / 4;
}
```

Cet élément commence à la première rangée, deuxième colonne et s'étend jusqu'à la troisième rangée, quatrième colonne.

#### Utilisation du slash

L'utilisation du slash / dans les valeurs de la grille CSS est une convention syntaxique qui permet de séparer et de délimiter différentes parties de la déclaration, en particulier lorsqu'on travaille avec des lignes et des colonnes. Voici quelques scénarios où tu peux rencontrer ce slash dans le contexte des grilles CSS :

**Définir le début et la fin d'un placement :** Lorsque tu définis où un élément grid commence et se termine, tu utilises le slash pour séparer les valeurs de début et de fin.

```css
.item {
    grid-column: 2 / 4;  // Commence à la 2ème colonne et se termine à la 4ème.
}
```

**Raccourcis avec grid-area :** La propriété grid-area permet de définir rapidement le placement d'un élément en termes de ligne de départ, colonne de départ, ligne de fin et colonne de fin. Le slash est utilisé pour séparer ces quatre valeurs.

```css
.item {
    grid-area: 1 / 2 / 3 / 4;  // Ligne de départ, colonne de départ, ligne de fin, colonne de fin.
}
```

**Définir les tailles des lignes et des colonnes avec grid-template :** Lorsque tu utilises la propriété grid-template pour définir à la fois les rangées et les colonnes, tu utilises le slash pour séparer les deux ensembles de valeurs.

```css
.container {
    grid-template: 1fr 2fr / 200px 1fr 1fr;  // Rangées / Colonnes
}
```

<!-- omit in toc -->
## On s'arrête là pour le moment

On s'arrête là pour le moment. Cela fait déjà beaucoup de théorie à pratiquer. Les grids ne sont pas faciles à créer de toute pièces, il existe différents outils pour vous aider, mais il est important d'en comprendre l'essence principale pour pouvoir plus facilement les modifier.

## Flexbox vs Grid

<!-- omit in toc -->
### Flexbox (Flexible Box Layout)

- **Objectif principal :** Flexbox est conçu pour gérer la mise en page dans une dimension, soit une colonne, soit une rangée.
- **Utilisation typique :** Idéal pour aligner des éléments dans des barres de navigation, des barres latérales, ou pour des petits composants et des widgets. Flexbox est aussi parfait pour réorganiser des éléments en ligne ou en colonne en fonction de la taille de l'écran.
- **Propriétés clés :** `display: flex`, `flex-direction`, `justify-content`, `align-items`, etc.

<!-- omit in toc -->
### CSS Grid (Grid Layout)

- **Objectif principal :** Grid est conçu pour gérer des mises en page bidimensionnelles, c'est-à-dire à la fois des colonnes et des rangées en même temps.
- **Utilisation typique :** Idéal pour construire des structures majeures de pages web, des maquettes complexes, des designs avec des zones définies (comme les en-têtes, contenus principaux, barres latérales, pieds de page, etc.).
- **Propriétés clés :** `display: grid`, `grid-template-columns`, `grid-template-rows`, `grid-gap`, `grid-area`, etc.

**Quand utiliser l'un plutôt que l'autre ?**

**Flexbox** est ton meilleur ami lorsque tu veux gérer la mise en page linéaire d'éléments. Si tu penses en termes de ligne ou de colonne, Flexbox est probablement le choix idéal.

**Grid**, en revanche, est la solution lorsque tu veux gérer un design bidimensionnel. Si tu as une maquette ou un design complexe à réaliser, Grid est sans doute la meilleure option.

**Peut-on les utiliser ensemble ?**

Absolument ! Flexbox et Grid ne sont pas mutuellement exclusifs. Tu peux très bien avoir un layout global construit avec Grid, et utiliser Flexbox pour gérer des composants ou des sections spécifiques à l'intérieur de ce layout.

En résumé, Flexbox et Grid sont deux outils puissants en CSS qui ont des usages différents mais complémentaires. Le choix dépendra de ton besoin spécifique de mise en page. Dans de nombreux projets modernes, tu te retrouveras à utiliser les deux en harmonie pour réaliser des designs fluides et réactifs.

## Quelques liens utiles

[Layoutit!](https://grid.layoutit.com/) Permet de créer ses grilles en ligne.

[Complete guide to Grid](https://css-tricks.com/snippets/css/complete-guide-grid)