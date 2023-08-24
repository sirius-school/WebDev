# Méthode de sélection querySelector

- [Méthode de sélection querySelector](#méthode-de-sélection-queryselector)
  - [Introduction](#introduction)
  - [La méthode `querySelector`](#la-méthode-queryselector)
  - [La méthode `querySelectorAll`](#la-méthode-queryselectorall)
  - [Utilisation pratique](#utilisation-pratique)


## Introduction
En JavaScript, les méthodes `querySelector` et `querySelectorAll` sont des fonctions/méthodes très utiles pour sélectionner des éléments dans le DOM (Document Object Model), votre page, en utilisant des sélecteurs CSS. Ces méthodes permettent de cibler spécifiquement les éléments que vous souhaitez manipuler ou interagir avec.

## La méthode `querySelector`

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
const titleClass = document.querySelector("h1.title");
```
`formulaireTag` sélectionne la première **balise** correspondante à `<form>`
`formulaireId` sélectionne la balise correspondante à l'**ID** `monFormulaire`
`formulaire` sélectionne le premier élément `<form>` avec l'**ID** `monFormulaire`
`titleClass` sélectionne le premer élément `<h1>` avec la **classe** `title`

## La méthode `querySelectorAll`

La méthode `querySelectorAll` est utilisée pour sélectionner tous les éléments correspondant à un sélecteur CSS donné. Elle renvoie une NodeList, un **tableau** d'éléments qui correspondent au sélecteur. Voici comment vous pouvez l'utiliser :

```javascript
const tousLesLiens = document.querySelectorAll("a");
```

Dans cet exemple, `tousLesLiens` serait une NodeList, un tableau de tous les éléments `<a>` de la page.

Tout comme avec `querySelector`, vous pouvez utiliser des sélecteurs plus spécifiques pour cibler des éléments particuliers :

```javascript
const paragraphes = document.querySelectorAll("article p");
```

Ici, `paragraphes` serait une liste de tous les éléments `<p>` à l'intérieur des éléments `<article>`.

## Utilisation pratique

Les méthodes `querySelector` et `querySelectorAll` sont extrêmement utiles pour manipuler le contenu d'une page web de manière dynamique. Vous pouvez les utiliser pour ajouter des événements aux éléments, modifier leur contenu, leurs styles, ou pour effectuer des opérations sur un groupe spécifique d'éléments.

Par exemple, vous pouvez utiliser `querySelectorAll` pour sélectionner tous les éléments d'une liste et leur ajouter un gestionnaire d'événements de clic :

```javascript
const tousLesElementsListe = document.querySelectorAll("ul li");

tousLesElementsListe.forEach(element => {
    element.addEventListener("click", () => {
        // Faire quelque chose lorsque l'élément est cliqué
    });
});
```

En résumé, les méthodes `querySelector` et `querySelectorAll` sont des outils puissants pour accéder aux éléments du DOM en utilisant des sélecteurs CSS familiers. Elles offrent une flexibilité et une simplicité accrues lors de la manipulation et de l'interaction avec le contenu HTML de vos pages web.

> Made by [Lucas Ielli](https://github.com/LucasIelli)
