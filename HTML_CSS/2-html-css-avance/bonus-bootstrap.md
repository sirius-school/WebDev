<!-- omit in toc -->
# Bootstrap

![bootstrap](https://getbootstrap.com/docs/5.2/assets/brand/bootstrap-logo-shadow.png)

:warning::warning::warning::warning:

Ce cours à été rédigé sur une ancienne version de Bootstrap et est donc à consulter à titre informatif.

La nouvelle verison étant la 5.2 et sa documentation est disponnible [ici](https://getbootstrap.com/docs/5.2/getting-started/introduction/)

:warning::warning::warning::warning:

- [Introduction](#introduction)
- [Installation](#installation)
  - [Méthode rapide (CDN)](#méthode-rapide-cdn)
  - [Méthode complète (fichiers compilés)](#méthode-complète-fichiers-compilés)
    - [Fichier sources](#fichier-sources)
  - [Package manager](#package-manager)
- [Starter Template](#starter-template)
- [Utilisation](#utilisation)
  - [Container](#container)
    - [Fluid container](#fluid-container)
    - [Responsive container](#responsive-container)
  - [Grid](#grid)
    - [Largeur égale](#largeur-égale)
    - [Alignement](#alignement)
      - [Vertical](#vertical)
      - [Horizontal](#horizontal)
    - [More](#more)
  - [Utilities](#utilities)
    - [Colors](#colors)
      - [Text color](#text-color)
      - [Background color](#background-color)
    - [Borders](#borders)
    - [Spacing](#spacing)
    - [Sizing](#sizing)
    - [Text Alignement](#text-alignement)
  - [Components](#components)
  - [Icons](#icons)
  - [Themes](#themes)
  - [Snippets](#snippets)

## Introduction

Bootstrap est un framework permettant d'aider à la création de site web responsive et mobile first.

Il comprend un large éventail de classes CSS déjà toute faites, lorsqu'on apprend à les utiliser on peut très rapidement construire une page web ou un prototype.

Un des gros intérêt de Bootstrap c'est la possibilité de définir le comportement de nos éléments via différentes classes. On peut par exemple définir aussi bien la couleur, la couleur de fond et l'alignement d'un texte avec 3 classes à appliqués à une seule `div`.

## Installation

### Méthode rapide (CDN)

Copiez-collez le lien vers le CSS dans votre balise `<head>`.

```html
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" crossorigin="anonymous">
```

Voilà, vous avez accès aux classes de Bootstrap!

Il faut encore ajouter les scripts Jquerry (bientôt obsolète dans la future version 5), Popper.js et ceux de Bootstrap pour que tous leurs composants fonctionnent correctement. Ceux-ci sont optionnels, vous pouvez retrouver la liste des composants qui nécessitent du JS pour fonctionner dans [la documentation](https://getbootstrap.com/docs/4.5/getting-started/introduction/#js).

Ajoutez les lignes suivantes à la fin de votre page, juste avant la fermeture de la balise \<body> pour incorporer le JS.

```html
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js" integrity="sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN" crossorigin="anonymous"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js" integrity="sha384-B4gt1jrGC7Jh4AgTPSdUtOBvfO8shuf57BaghqFfPlYxofvL8/KUEfYiJOMMV+rV" crossorigin="anonymous"></script>
```

Pour pouvoir utiliser le petit hack de répétition de header vu en [semaine 5 pour landing page](https://github.com/sirius-school/Semaine-05/tree/master/Exercices/landing-page#petit-hack-pour-r%C3%A9p%C3%A9ter-son-headerfooter-sur-plusieurs-pages) il nous faut la version full de JQuerry. Si vous regarder le starter Bootstrap, il utilise la version `slim`. Du coup il suffit d'intégrer le lien vers JQuerry full à la place. Attention à l'ordre dans lequel vous placez vos scripts. On a d'abord besoin de JQuerry avant d'exécuter notre script à nous, sinon ça plante!

```html
<script src="https://code.jquery.com/jquery-3.5.1.js" integrity="sha256-QWo7LDvxbWT2tbbQ97B53yJnYU3WhH/C8ycbRAkjPDc=" crossorigin="anonymous"></script>
<script src="script.js"></script> <!-- Notre script qui permet d'afficher le header/footer -->
<!-- le reste des scripts Bootstrap (i.e. Popper, bootstrap js) -->
```

### Méthode complète (fichiers compilés)

Il est également possible de télécharger Bootstrap et d'accéder aux fichiers dont vous avez besoin.

Pour ce faire rendez-vous sur la [page de Download :floppy_disk:](https://getbootstrap.com/docs/4.5/getting-started/download/#compiled-css-and-js)

Il vous suffit ensuite de placer ces fichiers directement dans votre projet et de créer les liens vous même. Cette méthode peut alourdir inutilement votre site.

#### Fichier sources

Il est également possible de retrouver les fichiers pré-compilation si vous voulez jeter un oeil et éffectuer des modifications importantes.

### Package manager

Si vous travaillez avec un package manager (npm), il est tout à fait possible d'installer Bootstrap. [Référez-vous à la documentation :book:](https://getbootstrap.com/docs/4.5/getting-started/download/#package-managers) pour la commande exacte en fonction de votre projet.

[:arrow_up:Revenir au top](#bootstrap)

## Starter Template

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript -->
    <!-- jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js" integrity="sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js" integrity="sha384-B4gt1jrGC7Jh4AgTPSdUtOBvfO8shuf57BaghqFfPlYxofvL8/KUEfYiJOMMV+rV" crossorigin="anonymous"></script>
  </body>
</html>
```

[:arrow_up:Revenir au top](#bootstrap)


## Utilisation

Vous êtes normalement capable d'utiliser des classes CSS, et bien Bootstrap ce n'est que ça au final. Une grosse bibliothèque de classes pensées pour le responsive et la conception facile de template HTML.

Il n'y a pas de solution miracle pour apprendre Bootstrap, il faut l'utiliser, allez lire la documentation et tester un maximum. Je vous propose une petite sélection et quelques explications des classes les plus utiles pour démarrer, après ça sera à vous d'explorer [:book: la documentation!](https://getbootstrap.com/docs/4.5/getting-started/introduction/)

### Container

Bootstrap propose une classe `container`qui permet d'avoir un contenant flexible facilement. Le container est nécessaires pour pouvoir utiliser leurs système de grid personnalisé (voir point suivant).

Un container de base à un max-width défini pour chaque breakpoint.

```html
<div class="container">...</div>
```

#### Fluid container

Il existe aussi une classe pour avoir un container fluide, qui prends toute la largeur disponible.

```html
<div class="container-fluid">...</div>
```

#### Responsive container

Il existe aussi des classes pour gérer les différents breakpoint de vos containers.

```html
<div class="container-sm">100% wide until small breakpoint</div>
<div class="container-md">100% wide until medium breakpoint</div>
<div class="container-lg">100% wide until large breakpoint</div>
<div class="container-xl">100% wide until extra large breakpoint</div>
```

[:book: Voir la documentation](https://getbootstrap.com/docs/4.5/layout/overview/#containers)

[:arrow_up:Revenir au top](#bootstrap)


### Grid

Bootstrap utilise **Flexbox** pour créer un système de grille personnalisé qui facilite la mise en page de vos éléments.

Le principe est simple, votre container est divisée en 12 colonnes, vous n'avez qu'a utilisé la classe `col-x` pour afficher une ligne de `x` colone.

Pour ce faire vous devez utilisez une `<div>` avec la classe `row` pour déterminer une rangée. Ensuite à l'intérieur de cette rangée, vous pouvez placer les colonnes que vous voulez. :exclamation: Le total de vos colonnes par rangé ne peut pas être supérieur à 12!

  [:book: Plus d'info dans la documentation](https://getbootstrap.com/docs/4.5/layout/grid/#how-it-works)

```html
<div class="container">
  <div class="row">
    <div class="col-4">
    <div class="col-4">
    <div class="col-4">
  </div>
  <div class="row">
    <div class="col-2">
    <div class="col-6">
    <div class="col-4">
  </div>
</div>
```

#### Largeur égale

Si vous n'indiquez pas de valeur après la classe `col` celle-ci seront immédiatement responsive et Bootstrap leurs appliqueras une largeur égale.

```html
<div class="container">
  <div class="row">
    <div class="col">
    <div class="col">
    <div class="col">
  </div>
</div>
```

> Ceci ferra bien 3 colonnes de largeur égale.

#### Alignement

Vous vous souvenez des propriétés `justify-content` et `align-items` de Flexbox? Et bien c'est utilisable ici aussi, suffit d'ajouter une des classes suivantes à votre rangée ou colone.

[:book: Plus d'info dans la documentation](https://getbootstrap.com/docs/4.5/layout/grid/#alignment)

##### Vertical

```html
  <div class="row align-items-start">
  <div class="row align-items-center">
  <div class="row align-items-end">
```

##### Horizontal

```html
  <div class="row justify-content-start">
  <div class="row justify-content-center">
  <div class="row justify-content-end">
  <div class="row justify-content-around">
  <div class="row justify-content-between">
```

#### More

Il y a encore pas mal d'options pour utiliser les grids de Bootstrap, mais il suffit d'un simple coup d'oeil dans [:book:la documentation](https://getbootstrap.com/docs/4.5/layout/grid/) pour trouver votre bonheur!

[:arrow_up:Revenir au top](#bootstrap)

### Utilities

Les utilities sont des petites classes qui s'ajoutent à vos éléments pour vous aider à les styliser. Il en existe pas mal, on va en voir quelques exemples, mais comme d'habitude, ça sera à vous d'allez dans [:book: la documentation des utilities](https://getbootstrap.com/docs/4.5/utilities/borders/)

```
Borders
Clearfix
Close icon
Colors
Display
Embed
Flex
Float
Image replacement
Interactions
Overflow
Position
Screen readers
Shadows
Sizing
Spacing
Stretched link
Text
Vertical align
Visibility
```

#### Colors

Bootstrap utilise Sass pour gérer son CSS et notamment ses variables et functions de couleurs. Il ensuite très facile d'utiliser ces couleurs une fois qu'on connaît le nom de ces variables. Il existe par exemple deux couleurs: Primary et Secondary. Celle-ci peuvent s'associer à n'importe quelle classe qui peut être mise en couleur. Il y a également une couleur de Success, Danger, Warning et Info.

[Voir les couleurs par défaut](https://getbootstrap.com/docs/4.5/utilities/colors/)

##### Text color

```html
<p class="text-primary">.text-primary</p>
<p class="text-secondary">.text-secondary</p>
<p class="text-success">.text-success</p>
<p class="text-danger">.text-danger</p>
<p class="text-warning">.text-warning</p>
<p class="text-info">.text-info</p>
<p class="text-light bg-dark">.text-light</p>
<p class="text-dark">.text-dark</p>
<p class="text-body">.text-body</p>
<p class="text-muted">.text-muted</p>
<p class="text-white bg-dark">.text-white</p>
<p class="text-black-50">.text-black-50</p>
<p class="text-white-50 bg-dark">.text-white-50</p>
```

##### Background color

```html
<div class="p-3 mb-2 bg-primary text-white">.bg-primary</div>
<div class="p-3 mb-2 bg-secondary text-white">.bg-secondary</div>
<div class="p-3 mb-2 bg-success text-white">.bg-success</div>
<div class="p-3 mb-2 bg-danger text-white">.bg-danger</div>
<div class="p-3 mb-2 bg-warning text-dark">.bg-warning</div>
<div class="p-3 mb-2 bg-info text-white">.bg-info</div>
<div class="p-3 mb-2 bg-light text-dark">.bg-light</div>
<div class="p-3 mb-2 bg-dark text-white">.bg-dark</div>
<div class="p-3 mb-2 bg-white text-dark">.bg-white</div>
<div class="p-3 mb-2 bg-transparent text-dark">.bg-transparent</div>
```

[:arrow_up:Revenir au top](#bootstrap)

#### Borders

Voici comment ajouter rapidement des bordures à vos éléments.

```html
<span class="border"></span>
<span class="border-top"></span>
<span class="border-right"></span>
<span class="border-bottom"></span>
<span class="border-left"></span>
```

Il est également facile de mettre tout ça en couleur avec les couleurs vues plus haut.

```html
<span class="border border-primary"></span>
<span class="border border-secondary"></span>
<span class="border border-success"></span>
<span class="border border-danger"></span>
<span class="border border-warning"></span>
<span class="border border-info"></span>
<span class="border border-light"></span>
<span class="border border-dark"></span>
<span class="border border-white"></span>
```

Et on peut encore ajouter un border-radius.

```html
<img src="..." alt="..." class="rounded">
<img src="..." alt="..." class="rounded-top">
<img src="..." alt="..." class="rounded-right">
<img src="..." alt="..." class="rounded-bottom">
<img src="..." alt="..." class="rounded-left">
<img src="..." alt="..." class="rounded-circle">
<img src="..." alt="..." class="rounded-pill">
<img src="..." alt="..." class="rounded-0">
```

[:book: Documentation sur les border](https://getbootstrap.com/docs/4.5/utilities/borders/)

[:arrow_up:Revenir au top](#bootstrap)

#### Spacing

Il est très facile d'ajouter des margins ou des padding à une div. Il suffit d'ajouter une classe en suivant la structure suivante

`{property}{sides}-{size}`

```text
-- Property --
m - pour une classe de marge
p - pour une classe de padding
```

```text
-- Sides --
t - pour une classe qui définit margin-top ou padding-top
b - pour une classe qui définit margin-bottom ou padding-bottom
l - pour une classe qui définit margin-left ou padding-left
r - pour une classe qui définit margin-right ou padding-right
x - pour une classe qui définit *-left and *-right
y - pour une classe qui définit *-top and *-bottom
blank - pour une classe qui définit un margin ou padding sur les 4 côtés de l'élément.
```

```text
-- Size --
0 - pour les classes qui éliminent les margin ou padding en utilisant la valeur 0.
1 - pour une classe qui utilise des margin ou padding à $spacer * .25
2 - pour une classe qui utilise des margin ou padding à $spacer * .5
3 - pour une classe qui utilise des margin ou padding à $spacer
4 - pour une classe qui utilise des margin ou padding à $spacer * 1.5
5 - pour une classe qui utilise des margin ou padding à $spacer * 3
auto - pour une classe qui utilise des margin auto
```

`$spacer` est une variable Sass définie par défaut à `1rem`.

[:book: Documentation sur le spacing](https://getbootstrap.com/docs/4.5/utilities/spacing/)

[:arrow_up:Revenir au top](#bootstrap)

#### Sizing

Il est possible d'utiliser les classes Bootstrap pour définir rapidement la taille d'un élément.

```html
<div class="w-25">Width 25%</div>
<div class="w-50">Width 50%</div>
<div class="w-75">Width 75%</div>
<div class="w-100">Width 100%</div>
<div class="w-auto">Width auto</div>
```

[:book: Documentation](https://getbootstrap.com/docs/4.5/utilities/sizing/)

#### Text Alignement

C'est également très facile d'aligner un texte avec la bonne classe.

```html
<p class="text-left">Left aligned text on all viewport sizes.</p>
<p class="text-center">Center aligned text on all viewport sizes.</p>
<p class="text-right">Right aligned text on all viewport sizes.</p>
```

[:book: Documentation](https://getbootstrap.com/docs/4.5/utilities/text/)

### Components

Un autre avantage de Bootstrap c'est l'immense bibliothèque de composants déjà tout près. En voici certains, mais de nouveau il faudra allez voir par vous même ce dont vous avez besoin car il n'y aucun intérêt à recopier ici du code tout fait.

Voici cependant le lien vers [:book: la documentation](https://getbootstrap.com/docs/4.5/components/alerts/)


Tous les composants disponibles:

```
Alerts
Badge
Breadcrumb
Buttons
Button group
Card
Carousel
Collapse
Dropdowns
Forms
Input group
Jumbotron
List group
Media object
Modal
Navs
Navbar
Pagination
Popovers
Progress
Scrollspy
Spinners
Toasts
Tooltips
```

Il vous suffit d'allez jeter un oeil au code et à la documentation pour reproduire les composants qui vous intéressent

[:arrow_up:Revenir au top](#bootstrap)

### Icons

Bootstrap propose depuis peu une bibliothèque d'icônes. Pour les installer exécutez la commande suivante:

```
npm install bootstrap-icons
```

Ensuite il suffit de copier le code HTML que vous trouverez sur [la page des icônes](https://icons.getbootstrap.com/#icons)

[:arrow_up:Revenir au top](#bootstrap)

### Themes

[Bootswatch](https://bootswatch.com/) propose des thèmes gratuits pour Bootstrap, il suffit de les télécharger et d'ensuite remplacer la feuille de style CSS par la nouvelle. Ainsi pas besoin de chipoter aux fichiers d'origine, vous aurez vos nouvelles couleurs et toutes les fonctionnalités de Bootstrap.

Il existe ainsi pléthore de thèmes payants qui propose souvent plus qu'une feuille de style, mais aussi des mises en page spécifique ou des nouveaux components.

[:arrow_up:Revenir au top](#bootstrap)

### Snippets

Les snippets ou fragments en français, sont des bouts de code que l'on peut retrouver sur internet. Il y a également une multitude de snippet qu'on peut retrouver sur internet pour utiliser Bootstrap et ses compposants de différentes façons.

Il existe des sites qui répertories ces bouts de code, comme par exemple [bootsnip](https://bootsnipp.com/) ou encore [mdbootstrap](https://mdbootstrap.com/snippets/).

:exclamation: Attention toute fois, ces bouts de codes sont souvent "complexe" pour pas grand chose ou sont "expirés". Soyez conscient de ce que vous copiez/collez dans vos projets et ne le faite pas sans comprendre un minimum. Au mieux inspirez-vous du code trouvé et essayer de le reproduire vous-même.

:exclamation: Attention également aux versions de Bootstrap utilisez. si vous copiez du "vieux" code il est possible que le nom de certaines classes aient changés depuis la création du snippet. Alors si ça fonctionne pas, regardez quelle version de Bootstrap est utilisée et voyez si vous pouvez l'adapter à la dernière version (4.5). Evitez d'utilisez la version 5, encore en alpha, pour un vrai projet. Faites en un sur le côté si vous voulez tester les nouvelles fonctionnalitées de Bootstrap!

[:arrow_up:Revenir au top](#bootstrap)
