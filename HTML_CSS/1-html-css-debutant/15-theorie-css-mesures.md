<!-- omit in toc -->
# Les unités et valeurs en CSS

Toutes les propriétés utilisées en CSS possède un ensembles de valeurs autorisées. Voyons ensemble certaines de ces valeurs.

<!-- omit in toc -->
## Table des matières

- [Nombres, longueurs et pourcentages](#nombres-longueurs-et-pourcentages)
  - [Longueurs](#longueurs)
    - [Unité de longueur absolue](#unité-de-longueur-absolue)
    - [Unités de longueur relative](#unités-de-longueur-relative)

## Nombres, longueurs et pourcentages

Il peut y avoir différents types de valeur numérique que l'on peut utiliser en CSS comme par exemple un nombre entier (1024 ou -55), un nombre décimal (0.5, -1.2), une dimension (45deg, 10px, 5s) ou un pourcentage (50%).

### Longueurs

Le type numérique le plus courant est la largeur. Que ce soit 10px ou 30em, vous allez croiser cette propriété constamment. Il y a cependant 2 valeurs à connaître: les relatives et les absolues.

#### Unité de longueur absolue

La liste qui suit contient uniquement des unités de longueur absolue. Ces quantités ne sont pas relatives à quoi que ce soit d'autre et leur taille sera considérée comme constante.

| Unité | Nom | Équivalent à |
|---|---|---|
| cm | Centimètres | 1cm = 38px = 25/64in |
| mm | Millimètre | 1mm = 1/10th of 1cm |
| Q | Quarts de millimètre | 1Q = 1/40th of 1cm |
| in | Pouces (inches) | 1in = 2.54cm = 96px |
| pc | Picas | 1pc = 1/6e de 1in |
| pt | Points | 1pt = 1/72e de 1in |
| px | Pixels | 1px = 1/96th de 1in |

La plupart de ces unités sont destinés à l'impression, on n'utilise pas les cm pour mesurer une image sur nos sites web. Par contre, vous retrouvez les pixels (px) qui est utilisés constamment dans le web notamment pour tout ce qui a besoin d'avoir une taille fixe (bordure, image, box-shadow, padding, margin).

#### Unités de longueur relative

Les unités de longueur relative permettent d'exprimer des quantités relatives à quelque chose d'autre comme la taille de la police de l'élément parent ou la taille du viewport. Le gros avantage des longueurs relative est qu'avec un peu d'organisation on peut faire que un élément s'ajuste par rapport à un autre.

| Unité | Équivalent à |
|---|---|
| em | Relative à la taille de la police de l'élément parent pour les typos. Pour la `width`, relative à la taille de la police de l'élément |
| rem | La taille de la police pour l'élément racine. |
| vw | 1% de la largeur du viewport (la zone d'affichage). |
| vh | 1% de la hauteur du viewport (la zone d'affichage). |
| vmin | 1% de la plus petite dimension du viewport (la zone d'affichage). |
| vmax | 1% de la plus grande dimension du viewport (la zone d'affichage). |

Voyons un exemple

```html
<!-- html -->
<div class="wrapper">
  <div class="box px">I am 200px wide</div>
  <div class="box vw">I am 10vw wide</div>
  <div class="box em">I am 10em wide</div>
</div>
```

```css
/* css */
.box{border: red 5px solid}
.wrapper {font-size: 1em;}
.px {width: 200px;}
.vw {width: 10vw;}
.em {width: 10em;}
```


[:arrow_up: Revenir au top](#table-des-matières)

[:rewind: Retour au sommaire du cours](./README.md#table-des-matières)
