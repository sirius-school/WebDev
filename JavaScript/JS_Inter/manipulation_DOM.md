<!-- omit in toc -->
# Manipulation du DOM deuxième partie
<!-- omit in toc -->
## Table des matières
- [querySelector \& querySelectorAll](#queryselector--queryselectorall)
  - [La méthode `querySelector`](#la-méthode-queryselector)
  - [La méthode `querySelectorAll`](#la-méthode-queryselectorall)
  - [Utilisation pratique](#utilisation-pratique)
  - [En résumé](#en-résumé)
- [Sélection via un attribut HTML](#sélection-via-un-attribut-html)
  - [La méthode `querySelector` avec attributs](#la-méthode-queryselector-avec-attributs)
  - [La méthode `querySelectorAll` avec attributs](#la-méthode-queryselectorall-avec-attributs)
  - [Considérations importantes](#considérations-importantes)
- [La propriété classList](#la-propriété-classlist)
  - [Accéder à classList](#accéder-à-classlist)
  - [Méthodes de classList](#méthodes-de-classlist)
  - [Utilisation pratique](#utilisation-pratique-1)
- [La propriété `id`](#la-propriété-id)
  - [Accéder à la propriété `id`](#accéder-à-la-propriété-id)
  - [Modifier la propriété `id`](#modifier-la-propriété-id)
  - [Considérations importantes](#considérations-importantes-1)
- [Manipuler votre HTML](#manipuler-votre-html)
  - [Créer de nouveaux éléments](#créer-de-nouveaux-éléments)
  - [Supprimer des éléments](#supprimer-des-éléments)
  - [Modifier le contenu d'éléments](#modifier-le-contenu-déléments)
  - [Modifier les attributs d'éléments](#modifier-les-attributs-déléments)
  - [Cloner des éléments](#cloner-des-éléments)
  - [Manipuler les styles CSS](#manipuler-les-styles-css)
  - [Manipuler les parents et les enfants](#manipuler-les-parents-et-les-enfants)
  - [Naviguer dans le DOM](#naviguer-dans-le-dom)
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

### Utilisation pratique

Les méthodes `querySelector` et `querySelectorAll` sont extrêmement utiles pour manipuler le contenu d'une page web de manière dynamique. Vous pouvez les utiliser pour ajouter des événements aux éléments, modifier leur contenu, leurs styles, ou pour effectuer des opérations sur un groupe spécifique d'éléments.

Par exemple, vous pouvez utiliser `querySelectorAll` pour sélectionner tous les éléments d'une liste et leur ajouter un gestionnaire d'événements de type `click` :

```javascript
const tousLesElementsListe = document.querySelectorAll("ul li"); 
// Sélectionne tous les éléments "li" à l'intérieur des éléments "ul"

tousLesElementsListe.forEach(element => {
    element.addEventListener("click", () => {
        // Faire quelque chose lorsque l'élément est cliqué
    });
});
```
### En résumé

Les méthodes `querySelector` et `querySelectorAll` sont des outils puissants pour accéder aux éléments du DOM en utilisant des sélecteurs CSS familiers. Elles offrent une flexibilité et une simplicité accrues lors de la manipulation et de l'interaction avec le contenu HTML de vos pages web.

[:arrow_up: Revenir au top](#table-des-matières)

## Sélection via un attribut HTML

La sélection d'éléments HTML via des attributs est une technique utile en développement web pour cibler spécifiquement des éléments en fonction de leurs attributs. JavaScript offre des moyens flexibles pour effectuer ces sélections en utilisant différentes méthodes. Dans cette partie, nous allons explorer comment sélectionner des éléments en fonction de leurs attributs HTML.

### La méthode `querySelector` avec attributs

Comme vu dans la partie précédente la méthode `querySelector` permet de sélectionner un élément en fonction d'un sélecteur CSS, y compris les attributs. Voici comment sélectionner un élément avec un attribut spécifique :

```javascript
// Exemple théorique
const element = document.querySelector('[attribut="valeur"]');
// Exemple concret
const element = document.querySelector('[data-id="123"]');
```

Ici, la variable `element` séléctionnera l'élément avec l'attribut `data-id` égal à `123`

### La méthode `querySelectorAll` avec attributs

```javascript
// Exemple théorique
const elements = document.querySelectorAll('[attribut="valeur"]');
// Exemple concret
const elements = document.querySelectorAll('[data-content="title"]');
```
Ici, la variable `elements` séléctionnera les éléments avec l'attribut `data-content` égaux à `title`

### Considérations importantes

- L'utilisation de sélections basées sur des attributs peut simplifier le ciblage d'éléments spécifiques, mais veillez à les utiliser judicieusement pour éviter de complexifier le code.

- Les attributs ne sont pas toujours la meilleure méthode pour identifier les éléments, en particulier si vous avez d'autres options comme les classes, les IDs, ou d'autres attributs.

- Les méthodes comme `querySelector` et `querySelectorAll` offrent une grande flexibilité en combinant des sélecteurs CSS avec des attributs.

En conclusion, la sélection d'éléments via des attributs HTML en JavaScript est une approche puissante pour cibler des éléments spécifiques dans le DOM. Utilisez ces techniques de manière appropriée pour améliorer la manipulation et l'interaction avec les éléments de votre page web.

[:arrow_up: Revenir au top](#table-des-matières)

## La propriété classList

La propriété `classList` en JavaScript est utilisée pour accéder et manipuler les classes CSS d'un élément HTML. Elle fournit des méthodes pratiques pour ajouter, supprimer, vérifier la présence de classes et bien plus encore. Cela offre une manière plus élégante et efficace de gérer les classes CSS par rapport à la manipulation manuelle de la chaîne de caractères de la propriété `class`.

### Accéder à classList

Pour accéder à la propriété `classList` d'un élément HTML, vous pouvez simplement utiliser la syntaxe suivante :

```javascript
const element = document.getElementById("monElement");
const class = element.classList;
```

### Méthodes de classList

1. **`add()`** : Ajoute une ou plusieurs classes à l'élément.

   ```javascript
   element.classList.add("maClasse");
   element.classList.add("classe1", "classe2");
   ```

2. **`remove()`** : Supprime une ou plusieurs classes de l'élément.

   ```javascript
   element.classList.remove("maClasse");
   element.classList.remove("classe1", "classe2");
   ```

3. **`toggle()`** : Ajoute la classe si elle n'est pas présente, la supprime si elle est présente.

   ```javascript
   element.classList.toggle("maClasse");
   ```

4. **`contains()`** : Vérifie si l'élément a une classe spécifique.

   ```javascript
   if (element.classList.contains("maClasse")) {
       console.log(element);
   }
   ```

5. **`replace()`** : Remplace une classe par une autre.

   ```javascript
   element.classList.replace("ancienneClasse", "nouvelleClasse");
   ```

6. **`item(i)`** ou **classList[i]** : Récupère la classe à un index spécifique dans la liste des classes.

   ```javascript
   const classeAtIndex = element.classList.item(0); // Récupère la première classe
   const classeAtIndex = element.classList[0]; // Donne le même résultat qu'avec item()
   ```

7. **`length`** : Récupère le nombre total de classes sur l'élément.

   ```javascript
   const nombreClasses = element.classList.length;
   ```

8. **`toString()`** : Convertit la liste de classes en une chaîne de caractères.

   ```javascript
   const classesEnChaine = element.classList.toString();
   ```

9. **`value`** : Quasiment identique à `toString()`, retourne la liste de classes en tant que chaîne de caractères.

   ```javascript
   const classesEnChaine = element.classList.value;
   ```

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

### Considérations importantes

1. **Unicité de l'ID** : Assurez-vous que chaque ID sur la page est unique. Un ID ne devrait être attribué qu'à un seul élément. Si plusieurs éléments ont le même ID, le comportement du script peut devenir imprévisible.

2. **Syntaxe valide** : Les IDs doivent commencer par une lettre (a-zA-Z) et ne peuvent pas contenir d'espaces ni de caractères spéciaux à l'exception du trait de soulignement (_) et du tiret (-).

3. **Accessibilité** : Évitez de dépendre uniquement des IDs pour des interactions importantes dans le contenu. Utilisez-les judicieusement et assurez-vous que le contenu est toujours accessible aux utilisateurs.

4. **Performance** : L'utilisation excessive de sélecteurs par ID peut ralentir les performances. Lorsque vous travaillez avec un grand nombre d'éléments, considérez d'autres méthodes de sélection, comme les classes ou les attributs.

En conclusion, la propriété `id` est un outil puissant pour accéder et manipuler des éléments HTML spécifiques en JavaScript. Utilisez-la avec soin et de manière réfléchie pour améliorer la fonctionnalité et l'interactivité de vos pages web.

[:arrow_up: Revenir au top](#table-des-matières)

## Manipuler votre HTML

### Créer de nouveaux éléments

Pour créer de nouveaux éléments HTML en JavaScript, vous pouvez utiliser la méthode `createElement()` :

```javascript
const nouveauParagraphe = document.createElement("p");
nouveauParagraphe.textContent = "Ceci est un nouveau paragraphe.";
```

Ensuite, pour ajouter cet élément à un autre élément existant (par exemple, le `<body>`), utilisez `appendChild()` :

```javascript
document.body.appendChild(nouveauParagraphe);
```

### Supprimer des éléments

Pour supprimer des éléments HTML, vous pouvez utiliser la méthode `remove()` :

```javascript
const elementASupprimer = document.getElementById("monElement");
elementASupprimer.remove();
```

### Modifier le contenu d'éléments

Pour modifier le contenu HTML d'un élément, vous pouvez utiliser la propriété `innerHTML` ou `textContent` :

```javascript
const monDiv = document.getElementById("monDiv");
monDiv.innerHTML = "<p>Nouveau contenu</p>";
// ou
monDiv.textContent = "Nouveau contenu";
```

### Modifier les attributs d'éléments

Pour modifier les attributs d'un élément, comme `src` pour une image ou `href` pour un lien, utilisez la méthode `setAttribute()` :

```javascript
const monImage = document.getElementById("monImage");
monImage.setAttribute("src", "nouveau-chemin-image.jpg");
```

### Cloner des éléments

La méthode `cloneNode()` permet de cloner un élément existant, soit en dupliquant seulement la structure (sans les événements), soit en dupliquant également les événements :

```javascript
const original = document.getElementById("original");
const clone = original.cloneNode(true); // true pour cloner les enfants (récursivement)
```

### Manipuler les styles CSS

La propriété `style` permet de manipuler les styles CSS d'un élément. Vous pouvez accéder à des propriétés spécifiques ou ajouter de nouvelles propriétés en utilisant JavaScript :

```javascript
const monElement = document.getElementById("monElement");
monElement.style.color = "red";
monElement.style.fontSize = "16px";
```

### Manipuler les parents et les enfants

Les méthodes `appendChild()`, `removeChild()` et `replaceChild()` permettent de manipuler les relations parent-enfant entre les éléments :

```javascript
const parent = document.getElementById("parent");
const nouvelEnfant = document.createElement("div");
parent.appendChild(nouvelEnfant);

const enfantASupprimer = document.getElementById("enfant");
parent.removeChild(enfantASupprimer);
```

### Naviguer dans le DOM

Les propriétés `parentNode`, `previousSibling`, `nextSibling`, `firstChild` et `lastChild` permettent de naviguer dans le DOM et accéder aux éléments voisins et enfants.

### Autres méthodes

D'autres méthodes comme `insertBefore()`, `replaceWith()`, `insertAdjacentHTML()`, `insertAdjacentElement()` sont également utiles pour des opérations spécifiques de manipulation de l'HTML.

En résumé, JavaScript offre une variété de méthodes pour créer, supprimer et manipuler les éléments HTML sur une page web. La maîtrise de ces méthodes est essentielle pour un développement web interactif et dynamique.

> Made by [Lucas Ielli](https://github.com/LucasIelli)
