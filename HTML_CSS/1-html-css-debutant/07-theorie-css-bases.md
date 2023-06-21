<!-- omit in toc -->
# Les bases du CSS pour débuter

Qu'est-ce que le CSS? Cela veut dire Cascading Style Sheet ou "feuille de style en cascade". Elle permet de générer la présentation de votre page HTML. Ainsi, au lieu de mettre votre code dédié au style dans la balise `<head>` ou directement dans chaque balise que vous souhaitez styliser, vous pouvez mettre toutes vos règles dans une ou plusieurs feuilles de style.

Le plus grand avantage, c'est la centralisation de vos styles et leurs maintient. Imaginez un instant, pour les liens sur votre page vous voulez que leurs couleur soit rouge, cela voudrait dire que sur chacun de vos fichier HTML contenant des liens il vous faut insérer le bout de code qui défini cette couleur. Des jours plus tard, tout votre site est fini et vous vous rendez compte que finalement la couleur de vos liens seraient mieux en orange. Vous allez devoir ouvrir vos 30 pages HTML et changer le code dans chacune de vos pages. C'est long et fastidieux et ce n'est que pour un "petit" changement. Si vous avez fait une feuille de style, il vous suffit de changer la couleur une fois et tous vos documents se mettront à jour!

Le CSS permet aussi la gestion des différents médias possibles pour votre page. Pour que votre site apparaisse correctement sur d'autres types d'écrans (tablette, smartphone,...) il faut lui dire comment se comporter, c'est encore là que le CSS brille!

> :bulb: Regardez ce site [http://csszengarden.com/], il propose le même contenu mais vous pouvez changer de style. C'est un exemple parfait de la puissance du CSS.

Prêt à découvrir le CSS alors?

<!-- omit in toc -->
## Table des matières

- [Quelques infos pratiques](#quelques-infos-pratiques)
- [CSS interne vs CSS externe](#css-interne-vs-css-externe)
  - [Interne à la page](#interne-à-la-page)
  - [Externe aux pages](#externe-aux-pages)
- [La syntaxe](#la-syntaxe)
  - [Les commentaires en CSS](#les-commentaires-en-css)
- [Les outils de développement](#les-outils-de-développement)

## Quelques infos pratiques

- Le CSS sert donc à préciser au navigateur vos couleurs de textes, de liens, la tailles de vos images, le style de vos polices, où sont situés vos différents bloc et encore tellement d'autres choses.
- C'est le navigateur qui va interpréter le css, il est donc possible d'avoir des rendus différents de l'un à l'autre.
- Certain navigateurs n'ont pas encore accès à toutes les fonctionnalités.
  - [https://caniuse.com/]
  - [https://browserstack.com/]
- Le pixel perfect n'existe pas.
- Inspecter l'élement (click droit sur une page) est votre meilleur ami.

[:arrow_up: Revenir au top](#table-des-matières)

## CSS interne vs CSS externe

### Interne à la page

On place une balise `<style>` dans la balise `<head>`

```html
<head>
  <style type="text/css">

    h1{
      color: red;
    }

  </style>
</head>
```

L'avantage c'est que l'ont peut appliquer une règle sur tous les  éléments identique du document.

L'inconvénient c'est que ça ne s'applique qu'au document et non pas au site entier. Il faudra donc modifier le CSS de chaque page en cas de changement.

Vous retrouverez le style CSS interne pour une page de newsletter par exemple. Là on est certain qu'on a pas besoin d'autres page.

[:arrow_up: Revenir au top](#table-des-matières)

### Externe aux pages

On insère un `lien` vers un fichier `.css` un peu de la même façon qu'on insère une image ou un lien. Ceci ce fait dans la balise `<head>` à l'aide de la balise `<link>`.

```html
<head>
<link rel="stylesheet" href="styles.css">
</head>
```

- `rel`: attribut requis pour déterminer la relation entre la page et le document qu'on lie. Dans notre cas il s'agit d'une feuille de style (stylesheet)
- `href`: comme pour un lien, il faut indiquer où se trouve notre fichier CSS.

[:arrow_up: Revenir au top](#table-des-matières)

## La syntaxe

```css
h1{
  color: blue;
  font-size: 12px;
}
```

![syntax-css](https://www.w3schools.com/css/img_selector.gif)

- Le `sélecteur` (*h1*) est l'élément sur lequel on applique les propriétés.
- La `propriété` (*color*, *font-size*) est l'effet que l'on va donner comme la couleur, la position,...
- La `valeur` (*blue*, *12px*) de la propriété CSS.
- La `déclaration CSS` est l'ensemble de propriété et de valeur. On peut en avoir plusieurs par sélecteur, on les sépare par un **;**

[:arrow_up: Revenir au top](#table-des-matières)

### Les commentaires en CSS

Comme pour l'HTML, on peut insérer des commentaires pour soi-même ou pour toutes autres personnes qui lira votre code. Pour ce faire on utilise un slash et un astérisque.

```css
h1{
  color: red; /* C'est rouge, parce que j'aime le rouge */
}
```

[:arrow_up: Revenir au top](#table-des-matières)

## Les outils de développement

Il est important de savoir utilisé les outils de développement de votre navigateur, souvent accessible en faisant un clic droit sur notre page et en cliquant sur "Inspecter". Cela ouvre un panneau qui nous seras bien utile pour essayer des propriétés CSS sans devoir revenir dans notre code à chaque modifications.

[:rewind: Retour au sommaire du cours](./README.md#table-des-matières)
