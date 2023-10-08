<!-- omit in toc -->
# Flexbox

Pour le moment on a vu que les éléments ont une propriété `display:block;`  ou `display:inline;` par défaut. On devait utiliser float pour de la mise en page. On a également vu les tableaux mais ça ne sert pas à mettre un site en page, encore moins un site responsive.Vient alors à la rescousse: Flexbox!

Le modèle de mise en page Flexbox (Flexible Box) en CSS est conçu pour simplifier la création de mises en page complexes et adaptatives. Il s'agit d'un système **unidimensionnel** qui permet de gérer l'alignement, la distribution et l'ordre des éléments dans un conteneur.

![flexible](https://media.giphy.com/media/xTiTnBzmxbZlMPdhlu/giphy.gif)

:arrow_up: Toi quand on te dit que Flexbox rend tes éléments flexible mais que tu maîtrises pas encore bien.

<!-- omit in toc -->
## Table des matières

- [Outils de développement](#outils-de-développement)
- [Comment ça fonctionne](#comment-ça-fonctionne)
  - [Les propriétés du parent](#les-propriétés-du-parent)
    - [Flex-direction](#flex-direction)
    - [Flex-wrap](#flex-wrap)
    - [Flex-flow](#flex-flow)
    - [Gap](#gap)
    - [Justify-content](#justify-content)
    - [Align-items](#align-items)
    - [Align-content](#align-content)
  - [Les propriétés des enfants du container](#les-propriétés-des-enfants-du-container)
    - [Order](#order)
    - [Flex-grow](#flex-grow)
    - [Flex-shrink](#flex-shrink)
    - [Flex-basis](#flex-basis)
      - [Avantages de flex-basis par rapport à width](#avantages-de-flex-basis-par-rapport-à-width)
    - [Flex](#flex)
    - [Align-self](#align-self)
- [Quelques liens utiles](#quelques-liens-utiles)

## Outils de développement

Avant de commencer à créer nos éléments Flex, il est important de savoir comment les visualiser.

Pour vérifier que notre Flexbox fonctionne bien, on peut utiliser les outils de développement de notre navigateur. Pour ce faire, il suffit de faire un clic droit sur notre page et de sélectionner **inspecter**. Ensuite on clique sur l'onglet **Layout**. Là on peut afficher notre Flexbox et voir différentes options d'affichages. Tu peux aussi cliquer sur la petite bulle "flex" à côté d'un élément HTML dans ton code.

## Comment ça fonctionne

C'est très simple, il nous faut un parent à qui on donne la propriété **display:flex;**. Dedans on va placer nos éléments que l'on souhaite distribuer dans l'espace. Tous les enfants directs deviendront du coup des éléments flexibles.

```html
<!-- index.html -->
<div class="parent">
    <div class="child">Enfant 1</div>
    <div class="child">Enfant 2</div>
    <div class="another-parent">
      <div class="child">Enfant 3</div>
      <div class="child">Enfant 4</div>
      <div class="child">Enfant 5</div>
    </div>
  </div>

```

```css
/* style.css */
.parent {
  display: flex; /* Appliquer Flexbox au parent */
  justify-content: space-between;
  border: blue 2px solid;
}

.child {
  border: 1px solid black;
  padding: 10px;
}

.another-parent {
  border: red 2px solid;
  display: flex;
}
```

[Voir en pratique sur W3School](https://www.w3schools.com/css/css3_flexbox.asp)

### Les propriétés du parent

[Suivre sur W3School](https://www.w3schools.com/css/css3_flexbox_container.asp)

#### Flex-direction

Définit la direction des éléments à l'intérieur du conteneur. Les valeurs possibles sont **`row`** (par défaut), `row-reverse`, `column` et `column-reverse`.

```css
.container {
  display: flex;
  flex-direction: row;
}
```

#### Flex-wrap

Contrôle le comportement de l'enroulement des éléments dans le conteneur lorsque l'espace est insuffisant. Les valeurs sont **`nowrap`** (par défaut), `wrap` et `wrap-reverse`.

En d'autres termes, flex-wrap vous permet de décider si les objets flexibles doivent continuer à tenir horizontalement à l'intérieur de la boîte (sans se soucier de leur taille) ou s'ils doivent être autorisés à se déplacer vers le bas (allez à la ligne) pour tenir verticalement lorsque l'espace est insuffisant.

```css
.container{
  display: flex;
  flex-wrap: wrap;
}
```

#### Flex-flow

La propriété flex-flow est en fait une courte façon de définir les deux propriétés flexbox principales : `flex-direction` et `flex-wrap`, en une seule déclaration. Cela simplifie le processus de configuration des directions et de l'enroulement des éléments flexibles dans un conteneur.

```css
.container {
  display: flex;
  flex-flow: row wrap; /* Équivalent à flex-direction: row; flex-wrap: wrap; */
}
```

#### Gap

La propriété gap en Flexbox (et en Grid Layout) est utilisée pour définir l'espace entre les éléments flexibles dans un conteneur. Elle offre un moyen simple et efficace de gérer l'espacement entre les éléments sans avoir besoin d'ajouter de marges ou de rembourrages supplémentaires.

La propriété gap combine à la fois les marges horizontales et verticales entre les éléments, ce qui permet de créer rapidement des mises en page plus aérées et organisées. Si tu souhaite un espace différent entre les lignes et les colonnes, tu peux spécifier deux valeurs.

```css
.container {
  display: flex;
  gap: 20px; /* Remplace les marges entre les éléments */
}
```

#### Justify-content

Contrôle l'alignement horizontal des éléments flexibles dans le conteneur. Les valeurs possibles sont **`flex-start`** (par défaut), `flex-end`, `center`, `space-between` et `space-around`.

```css
.container{
  display: flex;
  justify-content: center;
}
```

![justify-content](img/13/justify-content.svg)

#### Align-items

Contrôle l'alignement vertical des éléments flexibles dans le conteneur. Les valeurs possibles sont `flex-start`, `flex-end`, `center`, `baseline` et **`stretch`** (par défaut).

```css
.flex-container{
  display: flex;
  align-items: center;
}
```

![align-items](img/13/align-items.svg)

#### Align-content

Contrôle l'alignement vertical de l'espace supplémentaire dans le conteneur lorsque les éléments occupent plusieurs lignes. Les valeurs possibles sont similaires à celles de `justify-content`.

```css
.flex-container{
  display: flex;
  flex-wrap: wrap;
  align-content: space-between; /* flex-start, flex-end, stretch, space-between, space-around  */
}
```

![align-content](img/13/align-content.svg)

[:arrow_up: Revenir au top](#table-des-matières)

### Les propriétés des enfants du container

[Suivre sur W3School](https://www.w3schools.com/css/css3_flexbox_items.asp)

#### Order

La propriété `order` en Flexbox vous permet de spécifier l'ordre dans lequel les éléments flexibles sont affichés à l'intérieur de leur conteneur. Par défaut, tous les éléments ont une valeur d'ordre de 0. En utilisant la propriété `order`, vous pouvez changer cet ordre pour organiser les éléments d'une manière qui ne suit pas nécessairement l'ordre dans lequel ils apparaissent dans le code HTML.

```html
<!-- index.html -->
<div class="container">
  <div class="item">Premier</div>
  <div class="item" style="order: 3;">Troisième</div>
  <div class="item" style="order: 1;">Deuxième</div>
</div>
```

```css
/*styles.css */
.container {
  display: flex;
  justify-content: space-between;
}

.item {
  border: 1px solid black;
  padding: 10px;
}
```

#### Flex-grow

La propriété `flex-grow` détermine comment l'espace disponible est réparti entre les éléments flexibles lorsque leur conteneur a de l'espace supplémentaire. Un élément avec une valeur de flex-grow plus élevée prendra davantage d'espace que ceux avec des valeurs plus faibles. La valeur par défaut est `0`.

```css
.container {display: flex;}

.item {
  flex-grow: 1; /* Prendra autant d'espace que possible */
}

.item:nth-child(2) {
  flex-grow: 2; /* Prendra le double de l'espace par rapport aux autres */
}
```

#### Flex-shrink

La propriété `flex-shrink` détermine comment les éléments flexibles rétrécissent lorsque l'espace disponible est insuffisant. Un élément avec une valeur de flex-shrink plus élevée rétrécira davantage par rapport aux autres. La valeur par défaut est `1`.

```css
.container {display: flex; width: 300px;}

.item {
  border: red 2px solid;
  width: 150px;
  flex-shrink: 1; /* Rétrécira autant que possible */
}

.item:nth-child(2) {
  flex-shrink: 0; /* Ne rétrécira pas */
}

```

#### Flex-basis

La propriété `flex-basis` détermine la taille initiale d'un élément flexible avant que l'espace restant ne soit distribué. Cela peut être spécifié en pixels, en pourcentage ou en une valeur spéciale comme auto.

```css
.container {display: flex;}

.item {
  flex-basis: 150px; /* Taille initiale de 150 pixels */
}

.item:nth-child(2) {
  flex-basis: 25%; /* Taille initiale de 25% de l'espace disponible */
}

.item:nth-child(3) {
  flex-basis: auto; /* Taille basée sur le contenu interne */
}
```

##### Avantages de flex-basis par rapport à width

1. **Flexibilité dans les mises en page responsive** : `flex-basis` est plus adaptatif car il peut être exprimé en pourcentage. Cela signifie que l'élément peut s'adapter à différents écrans et tailles de conteneurs.

2. **Distribution équitable de l'espace** : Lorsque tu utilises `flex-basis` avec les propriétés `flex-grow` et `flex-shrink`, les éléments peuvent se répartir équitablement l'espace disponible tout en respectant leur taille initiale.

3. **Optimisation pour des mises en page flexibles** : Lorsque tu travailles avec des dispositions flexibles qui peuvent changer en fonction du contenu ou de l'espace disponible, `flex-basis` offre une plus grande flexibilité.

En résumé, si tu souhaites une largeur fixe et stable pour tes éléments, utilises `width`. Si tu veux une plus grande adaptabilité et une distribution flexible de l'espace, `flex-basis` est généralement préférable lorsque tu travailles avec des dispositions flexibles. On utilisera `flex-basis` quand on abordera le responsive design.

#### Flex

Permet de combiner **flex-grow**, **flex-shrink** et **flex-basis** en une seule règle.

:exclamation: Attention à bien respecter l'ordre des propriétés :exclamation:

```css
#element1{
  flex: 1 0 200px;
}
```

#### Align-self

Contrôle l'alignement vertical d'un élément flexible individuel, annulant l'effet de `align-items` pour cet élément.

```css
.item {
  align-self: center; /* flex-start, flex-end
  }
```

[Voir en pratique (en bas de page)](https://www.w3schools.com/css/css3_flexbox_items.asp)

[:arrow_up: Revenir au top](#table-des-matières)

## Quelques liens utiles

[Build with Flexbox](http://flexbox.buildwithreact.com/)

[Complete guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

[:arrow_up: Revenir au top](#table-des-matières)

[:rewind: Retour au sommaire du cours](./README.md#table-des-matières)
