<!-- omit in toc -->
# Manipulation du DOM deuxième partie
<!-- omit in toc -->
## Table des matières
- [querySelector \& querySelectorAll](#queryselector--queryselectorall)
  - [La méthode `querySelector`](#la-méthode-queryselector)
  - [La méthode `querySelectorAll`](#la-méthode-queryselectorall)
- [Sélection via un attribut HTML](#sélection-via-un-attribut-html)
- [La propriété `classList`](#la-propriété-classlist)
  - [Accéder à classList](#accéder-à-classlist)
  - [Méthodes de classList](#méthodes-de-classlist)
    - [`add()` : ajouter une classe](#add--ajouter-une-classe)
    - [`remove()` : supprimer une classe](#remove--supprimer-une-classe)
    - [`toggle()` : ajouter/supprimer une classe](#toggle--ajoutersupprimer-une-classe)
    - [`contains()` : vérifier si il y a une classe](#contains--vérifier-si-il-y-a-une-classe)
    - [`replace()` : remplacer une classe](#replace--remplacer-une-classe)
    - [`item(i)` ou `classList[i]` : récupèrer une classe à un index](#itemi-ou-classlisti--récupèrer-une-classe-à-un-index)
    - [`length` : récupèrer le nombre total de classes](#length--récupèrer-le-nombre-total-de-classes)
    - [`value` : retourner une classe en chaîne de caractères](#value--retourner-une-classe-en-chaîne-de-caractères)
  - [Utilisation pratique](#utilisation-pratique)
- [La propriété `id`](#la-propriété-id)
  - [Accéder à la propriété `id`](#accéder-à-la-propriété-id)
  - [Modifier la propriété `id`](#modifier-la-propriété-id)
  - [Considérations importantes](#considérations-importantes)
- [Manipuler votre HTML](#manipuler-votre-html)
  - [`createElement()` : créer de nouveaux éléments](#createelement--créer-de-nouveaux-éléments)
  - [`remove()` : supprimer des éléments](#remove--supprimer-des-éléments)
  - [`innerHTML` \& `textContent` : rappel modifier le contenu](#innerhtml--textcontent--rappel-modifier-le-contenu)
  - [`setAttribute()` : modifier les attributs d'éléments](#setattribute--modifier-les-attributs-déléments)
  - [`cloneNode` : cloner des éléments](#clonenode--cloner-des-éléments)
  - [`style.*` : manipuler les styles CSS](#style--manipuler-les-styles-css)
  - [Manipuler les parents et les enfants](#manipuler-les-parents-et-les-enfants)
    - [`appendChild()` : ajouter un enfant](#appendchild--ajouter-un-enfant)
    - [`removeChild()` : supprimer un enfant](#removechild--supprimer-un-enfant)
    - [`replaceChild()` : remplacer un enfant](#replacechild--remplacer-un-enfant)
    - [`parentNode` : accèder au parent](#parentnode--accèder-au-parent)
    - [`previousSibling` et `nextSibling` : accèder à un élément de même niveau](#previoussibling-et-nextsibling--accèder-à-un-élément-de-même-niveau)
    - [`firstChild` et `lastChild` : accèder aux enfants](#firstchild-et-lastchild--accèder-aux-enfants)
    - [`firstElementChild` et `lastElementChild` : accèder aux balises enfants](#firstelementchild-et-lastelementchild--accèder-aux-balises-enfants)
  - [Autres méthodes](#autres-méthodes)

## querySelector & querySelectorAll

En JavaScript, les méthodes `querySelector` et `querySelectorAll` sont des fonctions très utiles pour sélectionner des éléments dans le DOM (Document Object Model), votre page, en utilisant des sélecteurs comme vous le feriez en CSS. Ces méthodes permettent de cibler spécifiquement les éléments que vous souhaitez manipuler ou interagir avec.

### La méthode `querySelector`

La méthode `querySelector` est utilisée pour sélectionner le premier élément correspondant à un sélecteur CSS, à une balise HTML donné-e. Voici comment vous pouvez l'utiliser :

```javascript
const element = document.querySelector(".maClasse");
```

Dans cet exemple, `element` sera le **premier élément** de la page avec la **classe** CSS `maClasse`.

Vous pouvez également utiliser des sélecteurs plus complexes pour cibler des éléments spécifiques. Par exemple :

```javascript
const formulaireTag = document.querySelector("form");
const formulaireId = document.querySelector("#monFormulaire");
const formulaire = document.querySelector("form#monFormulaire");
const headerClass = document.querySelector(".title");
const titleClass = document.querySelector("h1.title");
```
`formulaireTag` sélectionne la première **balise** correspondante à `<form>`
`formulaireId` sélectionne la balise correspondante à l'**ID** `monFormulaire`
`formulaire` sélectionne le premier élément `<form>` avec l'**ID** `monFormulaire`
`titleClass` sélectionne le premier élément avec la **classe** `title`
`titleClass` sélectionne le premier élément `<h1>` avec la **classe** `title`

[:arrow_up: Revenir au top](#table-des-matières)

### La méthode `querySelectorAll`

La méthode `querySelectorAll` est utilisée pour sélectionner tous les éléments correspondant à un sélecteur CSS donné. Elle renvoie une NodeList, un **tableau** d'éléments qui correspondent au sélecteur. Voici comment vous pouvez l'utiliser :

```javascript
const tousLesLiens = document.querySelectorAll("a");
```

Dans cet exemple, `tousLesLiens` serait une NodeList, un tableau de tous les éléments `<a>` de la page.

Tout comme avec `querySelector`, vous pouvez utiliser des sélecteurs plus spécifiques pour cibler des éléments particuliers :

```javascript
const paragraphes = document.querySelectorAll("article p");
```

Ici, la variable `paragraphes` serait une liste de tous les éléments `<p>` à l'intérieur des éléments `<article>`.

[:arrow_up: Revenir au top](#table-des-matières)

## Sélection via un attribut HTML

La sélection d'éléments HTML via des attributs est une technique utile en développement web pour cibler spécifiquement des éléments en fonction de leurs attributs. JavaScript offre des moyens flexibles pour effectuer ces sélections en utilisant différentes méthodes. Les méthodes de sélection (`getElementById, getElementsByClassName, getElementsByTagName`, `querySelector` et `querySelectorAll`) permettent de sélectionner un élément HTML, y compris ses attributs. Voici comment sélectionner un élément avec un attribut spécifique :

```javascript
// Exemple théorique
const element = document.querySelector('[attribut="valeur"]');
// Exemple concret
const element = document.querySelector('[data-id="123"]');
```

Ici, la variable `element` séléctionnera l'élément avec l'attribut `data-id` égal à `123`

```javascript
// Exemple théorique
const elements = document.querySelectorAll('[attribut="valeur"]');
// Exemple concret
const elements = document.querySelectorAll('[data-content="title"]');
```
Ici, la variable `elements` séléctionnera tous les éléments avec l'attribut `data-content` égaux à `title`

[:arrow_up: Revenir au top](#table-des-matières)

## La propriété `classList`

La propriété `classList` en JavaScript est utilisée pour accéder et manipuler les classes CSS d'un élément HTML. Elle fournit des méthodes pratiques pour ajouter, supprimer, vérifier la présence de classes et bien plus encore. Cela offre une manière plus élégante et efficace de gérer les classes CSS par rapport à la manipulation manuelle de la chaîne de caractères de la propriété `class`.

### Accéder à classList

Pour accéder à la propriété `classList` d'un élément HTML, vous pouvez simplement utiliser la syntaxe suivante :

```javascript
const element = document.getElementById("monElement");
const class = element.classList;
```

[:arrow_up: Revenir au top](#table-des-matières)

### Méthodes de classList

#### `add()` : ajouter une classe

   ```javascript
   element.classList.add("maClasse");
   element.classList.add("classe1", "classe2");
   ```

[:arrow_up: Revenir au top](#table-des-matières)

#### `remove()` : supprimer une classe

Supprimer une classe ou plusieurs si vous spécifiez plusieurs arguments.

   ```javascript
   element.classList.remove("maClasse");
   element.classList.remove("classe1", "classe2");
   ```

[:arrow_up: Revenir au top](#table-des-matières)

#### `toggle()` : ajouter/supprimer une classe

Ajouter une classe si elle n'est pas présente, la supprimer si elle est présente.

   ```javascript
   element.classList.toggle("maClasse");
   ```

[:arrow_up: Revenir au top](#table-des-matières)

#### `contains()` : vérifier si il y a une classe

   ```javascript
   if (element.classList.contains("maClasse")) {
       console.log(element);
   }
   ```

[:arrow_up: Revenir au top](#table-des-matières)

#### `replace()` : remplacer une classe

Cette méthode utilise deux arguments : le premier est l'ancienne classe, le deuxième est la nouvelle.

   ```javascript
   element.classList.replace("ancienneClasse", "nouvelleClasse");
   ```

[:arrow_up: Revenir au top](#table-des-matières)

#### `item(i)` ou `classList[i]` : récupèrer une classe à un index

   ```javascript
   const classeAtIndex = element.classList.item(0); // Récupère la première classe
   const classeAtIndex = element.classList[0]; // Donne le même résultat qu'avec item()
   ```

[:arrow_up: Revenir au top](#table-des-matières)

#### `length` : récupèrer le nombre total de classes

   ```javascript
   const monTitre = document.getElementById('monTitre');
   const nombreClasses = monTitre.classList.length;
   ```

[:arrow_up: Revenir au top](#table-des-matières)

#### `value` : retourner une classe en chaîne de caractères

   ```javascript
   const classesEnChaine = element.classList.value;
   ```

[:arrow_up: Revenir au top](#table-des-matières)

### Utilisation pratique

La propriété `classList` peut être utilisée en conjonction avec les événements et la logique de votre application pour créer des interactions plus dynamiques en modifiant les classes CSS en temps réel. Comme vous l'avez fait sur l'exercice de la Todo Liste.

Par exemple, vous pouvez créer des animations CSS en ajoutant ou en supprimant des classes lorsque certains événements se produisent (clics, survols, etc). De plus, cela peut être utilisé pour activer ou désactiver des styles spécifiques en fonction de l'état de votre application.

En conclusion, la propriété `classList` en JavaScript est un outil puissant pour gérer les classes CSS des éléments HTML de manière propre et efficace, en offrant une meilleure organisation et une manipulation plus simple des styles de votre page web.

[:arrow_up: Revenir au top](#table-des-matières)

## La propriété `id`

La propriété `id` est un attribut spécial d'un élément HTML qui permet de lui attribuer un identifiant unique au sein de la page web. En JavaScript, vous pouvez accéder et manipuler cette propriété pour obtenir ou définir l'ID d'un élément.

### Accéder à la propriété `id`

Pour accéder à la propriété `id` d'un élément en JavaScript, vous pouvez simplement utiliser la syntaxe suivante :

```javascript
const element = document.getElementById("monElement");
const id = element.id;
```

Dans cet exemple, la variable `id` contiendra la valeur de l'attribut `id` de l'élément avec l'ID `monElement`.

[:arrow_up: Revenir au top](#table-des-matières)

### Modifier la propriété `id`

Vous pouvez également modifier la propriété `id` d'un élément en assignant une nouvelle valeur à cette propriété :

```javascript
const element = document.getElementById("monElement");
element.id = "nouvelID";
```

Dans cet exemple, l'ID de l'élément sera modifié de `monElement` à `nouvelID`.

La propriété `id` peut également être utilisée pour créer des liens internes sur une page en utilisant des ancres :

```html
<a href="#monElement">Aller à l'élément</a>
<div id="monElement">Contenu de l'élément</div>
```

En cliquant sur le lien, la page fera défiler jusqu'à l'élément avec l'ID `monElement`.

[:arrow_up: Revenir au top](#table-des-matières)

### Considérations importantes

1. **Unicité de l'ID** : Assurez-vous que chaque ID sur la page est unique. Un ID ne devrait être attribué qu'à un seul élément. Si plusieurs éléments ont le même ID, le comportement du script peut devenir imprévisible.

2. **Syntaxe valide** : Les IDs doivent commencer par une lettre (a-zA-Z) et ne peuvent pas contenir d'espaces ni de caractères spéciaux à l'exception du trait de soulignement (_) et du tiret (-).

3. **Accessibilité** : Évitez de dépendre uniquement des IDs pour des interactions importantes dans le contenu. Utilisez-les judicieusement et assurez-vous que le contenu est toujours accessible aux utilisateurs.

4. **Performance** : L'utilisation excessive de sélecteurs par ID peut ralentir les performances. Lorsque vous travaillez avec un grand nombre d'éléments, considérez d'autres méthodes de sélection, comme les classes ou les attributs.

En conclusion, la propriété `id` est un outil puissant pour accéder et manipuler des éléments HTML spécifiques en JavaScript. Utilisez-la avec soin et de manière réfléchie pour améliorer la fonctionnalité et l'interactivité de vos pages web.

[:arrow_up: Revenir au top](#table-des-matières)

## Manipuler votre HTML

### `createElement()` : créer de nouveaux éléments

Pour créer de nouveaux éléments HTML en JavaScript, vous pouvez utiliser la méthode `createElement()` :

```javascript
const nouveauParagraphe = document.createElement("p");
nouveauParagraphe.textContent = "Ceci est un nouveau paragraphe.";
```

Ensuite, pour ajouter cet élément à un autre élément existant (par exemple, le `<body>`), utilisez `appendChild()` :

```javascript
document.body.appendChild(nouveauParagraphe);
```
L'HTML sera composera donc comme suit : `<body><p>Ceci est un nouveau paragraphe.</p></body>`

[:arrow_up: Revenir au top](#table-des-matières)

### `remove()` : supprimer des éléments

Pour supprimer des éléments HTML, vous pouvez utiliser la méthode `remove()` :

```javascript
const elementASupprimer = document.getElementById("monElement");
elementASupprimer.remove();
```

[:arrow_up: Revenir au top](#table-des-matières)

### `innerHTML` & `textContent` : rappel modifier le contenu

Comme vous l'avez déjà vu dans la première partie voici un rappel pour modifier le contenu HTML d'un élément, grâce à `innerHTML` ou `textContent` :

```javascript
const monDiv = document.getElementById("monDiv");
monDiv.innerHTML = "<p>Nouveau contenu</p>";
// ou
monDiv.textContent = "Nouveau contenu";
```

[:arrow_up: Revenir au top](#table-des-matières)

### `setAttribute()` : modifier les attributs d'éléments

Pour modifier les attributs d'un élément, comme `src` pour une image ou `href` pour un lien, utilisez la méthode `setAttribute()` :

```javascript
const monImage = document.getElementById("monImage");
const monLien = document.getElementById("monLien");
monImage.setAttribute("src", "nouveau-chemin-image.jpg");
monLien.setAttribute("href", "https://www.example.be");
// Plus simplement
monImage.src = "nouveau-chemin-image.jpg";
monLien.href = "https://www.example.be";
```

[:arrow_up: Revenir au top](#table-des-matières)

### `cloneNode` : cloner des éléments

La méthode `cloneNode()` permet de cloner un élément existant, soit en dupliquant seulement la structure (sans les événements), soit en dupliquant également les événements :

```javascript
const original = document.getElementById("original");
const clone = original.cloneNode(true); // true pour cloner les enfants
const clone = original.cloneNode(false); // flase pour cloner uniquement l'élément
```

[:arrow_up: Revenir au top](#table-des-matières)

### `style.*` : manipuler les styles CSS

La propriété `style` permet de manipuler les styles CSS d'un élément. Vous pouvez accéder à des propriétés spécifiques ou ajouter de nouvelles propriétés en utilisant JavaScript :

```javascript
const monElement = document.getElementById("monElement");
monElement.style.color = "red";
monElement.style.fontSize = "16px";
monElement.style.backgroundColor = "green";
```

[:arrow_up: Revenir au top](#table-des-matières)

### Manipuler les parents et les enfants

Dans cette partie, nous allons explorer plusieurs propriétés importantes en JavaScript qui sont utilisées pour naviguer et manipuler la structure d'un document HTML. Ces propriétés fournissent des moyens simples d'accéder aux éléments parents, frères et sœurs, ainsi qu'aux enfants d'un élément donné dans le DOM (Document Object Model).

#### `appendChild()` : ajouter un enfant

La méthode `appendChild()` permet d'ajouter un nouvel enfant à un élément existant. Cet enfant peut être un nœud texte, un élément HTML, ou même un fragment de document. Lorsque cette méthode est appelée sur un élément parent, l'enfant spécifié est **ajouté à la fin** de la liste des enfants de cet élément. Voici comment utiliser `appendChild()` :

```javascript
const parentElement = document.getElementById('parentId');
const newChildElement = document.createElement('div');

parentElement.appendChild(newChildElement);
```

Dans cet exemple, `newChildElement` est ajouté en tant qu'enfant à la fin de `parentElement`.

[:arrow_up: Revenir au top](#table-des-matières)

#### `removeChild()` : supprimer un enfant

La méthode `removeChild()` permet de supprimer un enfant spécifique d'un élément parent. L'enfant à supprimer doit être passé en argument à la méthode. Voici comment utiliser `removeChild()` :

```javascript
const parentElement = document.getElementById('parentId');
const childToRemove = document.getElementById('childId');

parentElement.removeChild(childToRemove);
```

Dans cet exemple, `childToRemove` est retiré de la liste des enfants de `parentElement`.

[:arrow_up: Revenir au top](#table-des-matières)

#### `replaceChild()` : remplacer un enfant

La méthode `replaceChild()` permet de remplacer un enfant existant par un nouvel enfant. Elle prend **deux arguments** : le nouvel enfant à ajouter et l'enfant existant à remplacer. Voici comment utiliser `replaceChild()` :

```javascript
const parentElement = document.getElementById('parentId');
const newChildElement = document.createElement('div');
const childToReplace = document.getElementById('childId');

parentElement.replaceChild(newChildElement, childToReplace);
```
[:arrow_up: Revenir au top](#table-des-matières)

Dans cet exemple, `childToReplace` est remplacé par `newChildElement` au sein de la liste des enfants de `parentElement`.

> Les méthodes `appendChild()`, `removeChild()` et `replaceChild()` sont essentielles pour manipuler les relations parent-enfant entre les éléments dans le DOM. Elles offrent des moyens puissants de modifier la structure du document. Assure-toi de manipuler ces méthodes avec précaution, car elles peuvent avoir un impact significatif sur la structure et le comportement de la page web.

[:arrow_up: Revenir au top](#table-des-matières)

#### `parentNode` : accèder au parent

La propriété `parentNode` permet d'accéder à l'élément parent d'un nœud DOM donné. Elle renvoie l'élément parent sous forme d'objet. Voici un exemple d'utilisation :

```javascript
const childElement = document.getElementById('childId');
const parentElement = childElement.parentNode;
```

[:arrow_up: Revenir au top](#table-des-matières)

#### `previousSibling` et `nextSibling` : accèder à un élément de même niveau

Les propriétés `previousSibling` et `nextSibling` permettent d'accéder respectivement à l'élément précédent et à l'élément suivant dans le même niveau de l'arborescence DOM. Cependant, il convient de noter que les nœuds "frères et sœurs" inclusent également les nœuds texte vides et d'autres nœuds **non élémentaires**. Voici comment les utiliser :

```javascript
const someElement = document.getElementById('someId');
const previousSibling = someElement.previousSibling;
const nextSibling = someElement.nextSibling;
```

[:arrow_up: Revenir au top](#table-des-matières)

#### `firstChild` et `lastChild` : accèder aux enfants

Les propriétés `firstChild` et `lastChild` permettent d'accéder respectivement au premier et au dernier enfant d'un nœud DOM donné. Cependant, tout comme pour les propriétés précédentes, elles peuvent également pointer vers des nœuds **non élémentaires** tels que des nœuds texte. Voici comment les utiliser :

```javascript
const parentElement = document.getElementById('parentId');
const firstChild = parentElement.firstChild;
const lastChild = parentElement.lastChild;
```

[:arrow_up: Revenir au top](#table-des-matières)

#### `firstElementChild` et `lastElementChild` : accèder aux balises enfants

Pour éviter de pointer vers des nœuds texte et accéder uniquement aux éléments enfants, on peut utiliser les propriétés `firstElementChild` et `lastElementChild`. Ces propriétés renvoient respectivement le premier et le dernier élément enfant d'un nœud DOM, **en ignorant les nœuds non élémentaires**. Voici comment les utiliser :

```javascript
const parentElement = document.getElementById('parentId');
const firstElementChild = parentElement.firstElementChild;
const lastElementChild = parentElement.lastElementChild;
```

> En utilisant les propriétés `parentNode`, `previousSibling`, `nextSibling`, `firstChild`, `firstElementChild`, `lastChild` et `lastElementChild`, vous pouvez **naviguer** efficacement dans la structure d'un document HTML en JavaScript. Il est important de noter que ces propriétés peuvent renvoyer des valeurs `null` lorsque les éléments recherchés n'existent pas. Assurez-vous donc de vérifier les valeurs renvoyées avant d'effectuer des opérations sur elles.

[:arrow_up: Revenir au top](#table-des-matières)

### Autres méthodes

D'autres méthodes comme `insertBefore()`, `replaceWith()`, `insertAdjacentHTML()`, `insertAdjacentElement()` sont également utiles pour des opérations spécifiques de manipulation de l'HTML.

En résumé, JavaScript offre une variété de méthodes pour créer, supprimer et manipuler les éléments HTML sur une page web. La maîtrise de ces méthodes est essentielle pour un développement web interactif et dynamique.

[:arrow_up: Revenir au top](#table-des-matières)

[:rewind: Retour au sommaire du cours](../../README.md)

> Made by [Lucas Ielli](https://github.com/LucasIelli)
