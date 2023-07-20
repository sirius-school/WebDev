<!-- omit in toc -->
# CSS - Les sélecteurs

<!-- omit in toc -->
## Table des matières

- [Le sélecteur de type](#le-sélecteur-de-type)
- [Le sélecteur de descendance](#le-sélecteur-de-descendance)
- [Sélecteur de groupe](#sélecteur-de-groupe)
- [Sélecteur de classe](#sélecteur-de-classe)
  - [Qu'est-ce qu'une classe](#quest-ce-quune-classe)
- [L'identifiant (id)](#lidentifiant-id)
- [On mélange tout](#on-mélange-tout)
- [Espace](#espace)
- [Le sélecteur universel](#le-sélecteur-universel)
- [Combinateur de voisin direct](#combinateur-de-voisin-direct)
- [Sélecteurs de voisins généraux](#sélecteurs-de-voisins-généraux)
- [Sélecteurs enfant](#sélecteurs-enfant)
- [Convention de nommage](#convention-de-nommage)
- [Pour finir](#pour-finir)

## Le sélecteur de type

Vous pouvez sélectionner n'importe quel élément/balise HTML et lui appliquer un style, tous les éléments de la page seront impacté.

```css
p{
  color: green; /* Tous vos paragraphes seront écrit en vert */
}
```

## Le sélecteur de descendance

```html
<p>Cliquez <a>ici</a> pour accéder au site</p>
```

Pour sélectionner `<a>` descendant de `<p>` nous allons indiquer le chemin en séparant les éléments par un espace:

```css
p a { ... }
```

## Sélecteur de groupe

Pour sélectionner plusieurs éléments qui possèdent les mêmes valeurs, on les sépares par une virgule:

```css
h1, p { ... }
```

## Sélecteur de classe

Si vous avez besoin, par exemple, que tous vos paragraphes soit écris en jaune mais un seul doit être rouge. Il est possible de créer une classe spécifique.

### Qu'est-ce qu'une classe

C'est un attribut que l'on donne à une balise HTML pour pouvoir la cibler plus facilement avec notre CSS. C'est un peu comme une étiquette qu'on colle à notre élément.

On insère dans notre balise HTML un attribut **class** dont la **valeur** peut-être ce que vous voulez, soyez cohérent avec l'effet recherché.

```html
<p>Moi je serai jaune</p>
<p class="important">Mais moi je suis plus important du coup je serai en rouge</p>
```

```css
p{color: yellow;}
.important{color: red;}
```

Il est également possible d'utiliser plusieurs classes, on les sépare par des espaces tout simplement.

```html
<p class="important info">
```

> Ici la balise p prend 2 classes, `important` et `info`, qui sont définie dans la feuille de style.

Une classe peut être utilisé sur plusieurs balises dans la même document.

Il est également possible de cibler une balise HTML avec une classe. Pour ce faire on utilise la manière suivante:

```css
p.maClasse{ ... }
````

Cela ciblera tous les éléments `<p class="maclasse">`

Un autre exemple que vous verrez plus tard:

```html
<button type="button" class="btn btn-default"> ... </button>
```

```css
button.btn.btn-default{ ... } 
```

## L'identifiant (id)

C'est la même chose qu'une classe sauf qu'il doit être unique sur la page, il sera moins utilisé. On ne peut utiliser qu'un id par balise. On le cible avec `#`

```html
<p id="monId">
```

```css
#monId { ... }
```

## On mélange tout

Il est tout à fait possible de mélanger tous ces sélecteurs ensembles. Mais attention à ne pas créer du code CSS trop spécifique.

```css
p#monId.maClasse { ... }
```

> :bulb: Ici on sélectionne tous les paragraphes qui ont la classe `maClasse` et l'id `monId`

## Espace

Si on ne met pas d'espace entre nos sélecteurs, cela signifie que toutes les conditions doivent être vraies pour l'élément.

```css
p.important { ... }
```

```html
<p class="important">Est sélectionné</p>
<p>N'est pas sélectionné</p>
<h1 class="important">N'est pas sélectionné</h1>
```

> Dans l'exemple au dessus on ciblera tous les **paragraphes** qui ont une classe **important**

Si on met un espace, on cible la hiérarchie et du coup c'est le dernier sélecteur qu'on cible.

```css
p .important { ... }
```

```html
<p class="important">N'est sélectionné</p>
<p><span class="important">Est pas sélectionné</span></p>
<p><span>N'est pas sélectionné</span></p>
```

> Dans l'exemple au dessus on ciblera toutes les classes **important** qui ont sont descendants d'un paragraphe

Voyez comme un simple espace peut faire ou défaire votre page. Soyez attentif  et utilisez l'inspecteur de votre navigateur pour cibler plus facilement le problème.

## Le sélecteur universel

Pour sélectionner l'entièreté de notre page on peut utiliser `*`

```css
* {...}
```

:bulb: On peut combiner ce sélecteur avec d'autres pour sélectionner tous les éléments à l'intérieur d'un autre, par exemple:

```css
p * {...}
```

> Sélectionnera tous les éléments à l'intérieur d'un `<p>`

## Combinateur de voisin direct

Le combinateur `+` est un peu plus compliqué, il permet de cibler un voisin direct (qui suit) d'un autre élément.

```css
/* css */
.container + .important{...} 
```

```html
<!-- html -->
<main>
    <div class="container">
      <p class="important">
       Je ne suis pas sélectionné car je suis un enfant/.
      </p>
    </div>
    <p class="important">
     Je suis sélectionné car je suis un voisin direct
    </p>
  </main>
```

> :bulb: Dans cet exemple le `<p class="important">` à l'intérieur de `<div class="container">` ne sera pas sélectionné, car ici on ne cible pas la descendance mais le fait que le lien est "à côté" ou "à la suite" du paragraphe pas englober dans le paragraphe.

## Sélecteurs de voisins généraux

Le combinateur `~` permet de sélectionner tous les voisins direct ou pas direct qui suivent le premier élément sélectionné. C'est comme le sélecteur de voisin direct vu au dessus sauf qu'on peut en sélectionner plusieurs.  

```css
/* css */
p ~ span {color: red;}
```

```html
<!-- html -->
<span>Ici, ce n'est pas rouge.</span>
<p>Voici un paragraphe.</p>
<code>Un peu de code.</code>
<span>Et un autre span.</span>
<code>Encore du code</code>
<span>Ici aussi, c'est rouge</span>
```

## Sélecteurs enfant

Le combinateur `>` sépare deux sélecteurs et cible seulement les éléments correspondant au second sélecteur qui sont des enfants directs des éléments ciblés par le premier sélecteur.


```css
/* css */
span {
  background-color: aqua;
}

div > span {
  background-color: yellow;
}
```

```html
<!-- html -->
<div>
  <span>
    Span #1, in the div.
    <span>Span #2, in the span that's in the div.</span>
  </span>
</div>
<span>Span #3, not in the div at all.</span>
```

## Convention de nommage

- un nom de classe ou d'ID ne doit pas avoir d'accent ou caractères spéciaux.
- On a tendance à éviter le "tout majuscule"
- Un nom de classe ou ID ne prend jamais d'espace, sinon c'est une nouvelle classe

[:arrow_up: Revenir au top](#table-des-matières)

## Pour finir

Pas si compliqué, n'est-ce pas??

> :video_game: Petit jeu sympa pour s'entraîner aux sélecteurs: [http://flukeout.github.io/](http://flukeout.github.io/)

Il reste un ""tout petit"" sujet à abordé pour que tu sois fin prêt à te lancer dans le vaste monde du CSS: [les propriétés](09-theorie-css-prorietes.md)

[:arrow_up: Revenir au top](#table-des-matières)

[:rewind: Retour au sommaire du cours](./README.md#table-des-matières)
