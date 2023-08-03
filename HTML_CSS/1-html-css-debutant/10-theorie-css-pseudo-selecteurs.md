<!-- omit in toc -->
# Les pseudo sélecteurs

Vous avez peut-être déjà vu certains mot-clé derrière des sélecteurs en CSS (hover, link, visited, active, first-child,...). Ce sont les pseudo sélecteurs, on en distingue de deux types: les **pseudo-elements** et les **pseudo-class**.

- [Pseudo-class](#pseudo-class)
  - [Hover](#hover)
  - [Les liens](#les-liens)
  - [Focus](#focus)
  - [Pseudo-class et CSS Class](#pseudo-class-et-css-class)
  - [First-child](#first-child)
  - [Last-child](#last-child)
  - [Only-child](#only-child)
  - [First-of-type](#first-of-type)
  - [Last-of-type](#last-of-type)
  - [Only-of-type](#only-of-type)
  - [Nth-child](#nth-child)
  - [Nth-last-child](#nth-last-child)
  - [Empty](#empty)
  - [Not(X)](#notx)
  - [Attribut](#attribut)
  - [Attribut valeur](#attribut-valeur)
  - [Toutes les pseudo-class](#toutes-les-pseudo-class)
- [Pseudo-Element](#pseudo-element)
  - [After \& Before](#after--before)
  - [First-letter \& First-line](#first-letter--first-line)
  - [Selection](#selection)
  - [Tous les pseudo-element](#tous-les-pseudo-element)
- [On combine tout!](#on-combine-tout)

## Pseudo-class

Les pseudo-classes permettent d'appliquer un style à un élément non seulement en fonction de son contenu dans le document mais aussi en fonction de facteurs externes (l'historique de navigation par exemple avec :visited ; le statut du contenu avec :checked ; la position de la souris :hover).

Il se note à la suite d'un sélecteur avec `:pseudo-class`

### Hover 

Permet de préciser le style d'un élément lorsque l'utilisateur passe sa souris par dessus l'élément sélectionné.

```html
<div class="bubulle"></div>
```

```css
.bubulle{
  width:250px;
  aspect-ratio: 1;
  border-radius: 50%;
  background-color: yellow;
}

.bubulle:hover{
  background-color: red;
}
```

### Les liens

```css
/* css */
/* lien non-visité */
a:link {color: #FF0000;}

/* lien visité */
a:visited {color: #00FF00;}

/* survol avec le souris */
a:hover {color: #FF00FF;}

/* lien sélectionné cliqué */
a:active {color: #0000FF;} 
```

Ces propriétés CSS vont permettre de modifier le comportement par défaut des styles des liens sur votre page.

- **link**: permet de gérer le style des liens tant qu'il n'ont pas été cliqué. Mettre une couleur différente de votre couleur de texte est récommandé pour attirer le visiteur à cliquer sur le lien.
- **visisted**: permet de gérer le style des liens quand le visiteur à déjà cliqué dessus.
- **hover**: permet de gérer le style des liens lorsqu'on survole ce dernier avec le curseur de la souris.
- **active**: permet de gérer le style des liens quand ils sont cliqués.

> :bulb: Afin que la mise en forme s'applique au mieux, la règle :link doit être placée avant les autres : :link — :visited — :hover — :active. La pseudo-classe :focus est habituellement placée juste avant ou juste après :hover, en fonction de l'effet désiré.

### Focus

La pseudo-class `:focus` permet de définir le comportement d'un élément sélectionné par l'utilisateur généralement dans un formulaire.

```css
/* css */
input:focus {
  background-color: yellow;
}
```

### Pseudo-class et CSS Class

Il est tout à fait possible de combiner les classes CSS et les pseudo-classes.

```css
/* css */
a.important:hover{
  color:red;
}
```

### First-child

La pseudo-class `:first-child` permet de sélectionner spécifiquement le premier élément à l'intérieur de son parent à condition que ce soit le premier.

```css
/* css */
p:first-child{
  color:red;
}
```

```html
<!-- html -->
<div>
  <p>Je serai en rouge</p>
  <p>Je n'aurai pas de couleur spécifique</p>
  <p>Je n'aurai pas de couleur spécifique</p>
</div>
```

> :exclamation: Si l'élément n'est pas le premier de son parent, il ne sera pas sélectionner. Voir exemple suivant.

```css
/* css */
p:first-child{
  color:red;
}
```

```html
<!-- html -->
<div>
  <a href="#">Coucou</a>
  <p>Je ne suis pas le premier enfant de mon parent body, du coup je ne serai pas sélectionné</p>
  <p>Et moi non plus</p>
  <div>
    <p>Par contre, moi je suis bien le premier enfant de mon parent 'div' du coup je serai bien sélectionné</p>
    <p>Et moi toujours pas</p>
  </div>
</div>
```

<!-- omit in toc -->
#### Exemple: Sélectionner la première balise `<em>` dans toutes les `<p>`

```css
/* css */
  p em:first-child{
    color:red;
  }
```

```html
<!-- html -->
<p>Je suis une phrase, <em>moi je serai en rouge</em> et <em>moi, comme je suis le deuxième élément en italique, je ne le serai pas</em></p>
```
<!-- omit in toc -->
#### Exemple: Sélectionner toutes les balises `<em>` dans le "first-child" `<p>`

```css
/* css */
  p:first-child em{
    color: red;
  }
```

```html
<!-- html -->
<p>Salut <em>je serai en rouge</em> et <em>moi aussi</em></p>
<p>Salut <em>je serai PAS en rouge</em> et <em>moi NON PLUS</em></p>
```

### Last-child

Fonctionne comme pour `:first-child` mais au lieu de sélectionner le premier enfant de l'élément, il sélectionnera le dernier.

### Only-child

Sélectionne l'enfant d'un parent si il est le seul élément de ce parent.

```html
<div class="parent">
  <p>Je suis unique</p>
</div>
<div class="parent">
  <p>Je ne suis pas unique</p>
  <p>Je ne suis pas unique</p>
</div>
```

```css
.parent p:only-child{
  color:red;
}
```

### First-of-type

La pseudo-class `:first-of-type` va sélectionner tous les éléments dont c'est leur première apparition.

```css
/* css */
  article :first-of-type{
    background-color: red;
  }
```

```html
<!-- html -->
<article>
  <div>Je suis la première div</div>
  <div>Je suis le premier <span>span</span></div>
  <p>Je suis le premier paragraphe</p>
  <div>Et moi je suis la dernière div</div>
</article>
```

### Last-of-type

Fonctionne comme `:first-of-type` mais sélectionnera le dernier élément qui apparaît.

### Only-of-type

Sélectionne un élément dans son parent si c'est le seul de ce type là présent.

```html
<div class="parent">
  <img src="...">
</div>
<div class="parent">
  <img src="...">
  <img src="...">
</div>
```

```css
.parent img:only-of-type{
  border: 2px solid red;
}
```

### Nth-child

Permet de sélectionner un élément par rapport à sa position dans un groupe d'élément semblable.

```css
/* css */
a:nth-child(2){
  color:orange;
}
```

> Dans cet exemple on va sélectionner le deuxième lien (a) disponible

Ce sélecteur prend un paramètre supplémentaire entre parenthèse. Il peut s'agir des mots-clés: `odd` (impair) ou `even` (pair) ou d'un chiffre. Il est également possible d'y introduire des formules.

```css
/* css */
a:nth-child(2n+1){
  color:orange
}
```

Voilà comment est interprété la formule:

> (2 x 0) + 1 = 1 = 1st Element
> 
> (2 x 1) + 1 = 3 = 3rd Element
> 
> (2 x 2) + 1 = 5 = 5th Element

Cela revient pareil à indiquer `odd`, mais il est possible d'utiliser des formules différentes pour d'autres sélections, par exemple:

```css
/* css */
a:nth-child(3n+3){
  color: green;
}
```

> (3 x 0) + 3 = 3rd Element
>
> (3 x 1) + 3 = 6th Element
>
> (3 x 2) + 3 = 9th Element

> :bulb: Il est possible de raccourcir cette formule par `3n` pour sélectionner, du coup, tous les 3 éléments.

> ✅ Le + dans la formule permet de démarrer le compte en commençant par le chiffre qui suit. Par exemple: 3n+5 va sélectionner tous les 3 éléments en commençant par le cinquième.

[En apprendre plus sur les formules](https://css-tricks.com/how-nth-child-works/)

C'est un peu compliqué ces formules, c'est bien de savoir que ça existe pour quand on les rencontres dans du code ou pour réaliser des styles bien spécifique.

### Nth-last-child

Fonctionne comme `:nth-child` mais compte en commençant par la fin.

### Empty

Sélectionne un élément si il n'a pas d'enfant

```html
<section>
  <div>Plop</div>
</section>
<section>
</section>
```

```css
section:empty{
  width:100px;
  height:100px;
  background-color: red;
}
```

### Not(X)

Sélectionne tous les éléments qui **ne** sont **pas** le sélecteur **X**.

```html
<div>
  <p class="important">...</p>
  <p class="info">...</p>
  <p class="important">...</p>
  <p>...</p>
</div>  
```

```css
p:not(.important){
  color:red;
}
```

### Attribut

Il est possible d'ajouter des attributs spécifiques à nos éléments HTML en plus de ceux qu'on connaît déjà (src, href,...). Cela peut avoir un intérêt en JavaScript pour exécuter du code sur certain élément spécifique. Comme par exemple définir la couleur d'un élément en fonction de l'attribut "color". Alors c'est vraiment spécifique, on verra sans doute ça bien plus tard, mais voici déjà comment sélectionner un élément par son attribut.

```html
<div color="red">...</div>
```

```css
div[color]{
  border: 2px blue solid;
}
```

> :bulb: Ici on sélectionnera toutes les `div` qui on un attribut `color`, peu importe la valeur

### Attribut valeur

Il est également possible de sélectionner un élément qui a un attribut avec une valeur spécifique.

```html
<div color="red">...</div>
```

```css
div[color="red"]{
  border: 2px blue solid;
}
```

> :bulb: Ici on sélectionnera toutes les `div` qui on un attribut `color` **ET** la valeur `red.

On peut également sélectionné un élément dont la valeur de l'attribut commence par notre sélecteur, pratique si on a plusieurs valeurs qui commencent par la même lettre ou combinaison de lettre.

```html
<div color="red">...</div>
<div color="blue">...</div>
<div color="royalblue">...</div>
```

```css
div[color^="r"]{
  border: 2px blue solid;
}
```

Et on peut faire la même chose mais pour l'attribut dont la valeur se termine par notre sélecteur.

```html
<div color="red">...</div>
<div color="blue">...</div>
<div color="royalblue">...</div>
```

```css
div[color$="ue"]{
  border: 2px blue solid;
}
```

Et pour allez encore plus loin, on peut aussi sélectionner un attribut dont la valeur contient notre sélecteur, peu importe sa position.

```html
<div color="red">...</div>
<div color="blue">...</div>
<div color="royalblue">...</div>
```

```css
div[color*="e"]{
  border: 2px blue solid;
}
```

### Toutes les pseudo-class

Il y a évidement énormément d'autres pseudo-class qui ont chacune leurs utilités. Nous venons d'en voir quelques unes qui seront celle que vous utiliserez le plus fréquemment dans vos travaux.

Voici [un lien vers la MDN et toutes les pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)

## Pseudo-Element

Les pseudo-element sont des mots-clés que l'on rajoute à la fin d'un sélecteur pour sélectionner une partie précise de l'élément.

Il se note à la suite d'un sélecteur avec `::pseudo-element`

### After & Before

Permet de sélectionner le début (before) ou la fin (after) d'un élément. Cela sert notamment à ajouter un style à un élément grâce à la propriété `content`.

```css
/* css */
a::before{
  content:"This is a link -> "
}
a::after{
  content:" <- Click on me";
}
```

> :bulb: Le contenu ajouté sera en `inline` dans le bloc

### First-letter & First-line

Permet de sélectionner la première lettre ou ligne d'un élément.

```css
/* css */
p::first-letter {
  font-size: 230%;
}
p::first-line {
  color: red;
}
```

### Selection

Permet de styliser la sélection d'un élément par l'utilisateur.

```css
/* css */
::selection {
  color: red;
  background: yellow;
}
```

>:bulb: Tous les éléments sélectionnés ici seront en rouge et sur fond jaune. 

### Tous les pseudo-element

Il existe encore quelques autres pseudo-element, mais rien de bien utile dans le cadre de ce cours, voici tout de même [un lien vers la doc.](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)

## On combine tout!

Il est tout à fait possible de combiner plusieurs pseudo-sélecteur.

```css
/* css */
  p:nth-child(even):hover::first-letter {
    color:red;
  }
```

> :bulb: Ici on sélectionne la première lettre de tous les paragraphe pair et on applique une couleur dessus quand on passe notre souris par dessus cet élément (tout le paragraphe). C'est un peu tiré par les cheveux, mais ça fonctionne.

[:rewind: Retour au sommaire du cours](./README.md#table-des-matières)
