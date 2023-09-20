<!-- omit in toc -->
# Les boucles en JavaScript
<!-- omit in toc -->
## Table des matières
- [Introduction](#introduction)
- [1. La Boucle `for`](#1-la-boucle-for)
  - [Exemple d'utilisation de la boucle `for`](#exemple-dutilisation-de-la-boucle-for)
- [2. La Boucle `while`](#2-la-boucle-while)
  - [Exemple d'utilisation de la boucle `while`](#exemple-dutilisation-de-la-boucle-while)
- [3. La Boucle `do...while`](#3-la-boucle-dowhile)
  - [Exemple d'utilisation de la boucle `do...while`](#exemple-dutilisation-de-la-boucle-dowhile)
- [4. La Boucle `for...in`](#4-la-boucle-forin)
  - [Exemple d'utilisation de la boucle `for...in`](#exemple-dutilisation-de-la-boucle-forin)
- [5. La Boucle `for...of`](#5-la-boucle-forof)
  - [Exemple d'utilisation de la boucle `for...of`](#exemple-dutilisation-de-la-boucle-forof)
- [Petit rappel de forEach](#petit-rappel-de-foreach)
  - [Exemple d'utilisation de la boucle `forEach`](#exemple-dutilisation-de-la-boucle-foreach)
- [Conclusion](#conclusion)

## Introduction

Les boucles sont des structures de contrôle essentielles en programmation. Elles permettent d'exécuter un bloc de code de manière répétée tant qu'une condition spécifique est remplie. En JavaScript, il existe plusieurs types de boucles, chacune avec ses caractéristiques et ses cas d'utilisation. Dans ce cours, nous allons explorer les boucles `for`, `while`, `do...while`, `for...in`, et `for...of`.

> Que veux dire le mot itération en programmation ? C'est un procédé de calcul répétitif qui boucle jusqu'à ce qu'une condition particulière soit remplie.

## 1. La Boucle `for`

La boucle `for` est idéale lorsque vous connaissez à l'avance le nombre d'itérations nécessaires. Elle se compose de trois parties principales : l'initialisation, la condition de continuation, et l'expression d'itération.

```javascript
for (initialisation; condition de continuation; expression itération) {
    // Bloc de code à exécuter à chaque itération
}
```

- **Initialisation**: Une instruction qui est exécutée une seule fois avant le début de la boucle. Elle est généralement utilisée pour déclarer et initialiser la variable de contrôle (par exemple, `let i = 0;`).

- **Condition de continuation**: Une expression booléenne qui est évaluée avant chaque itération. Si la condition est vraie, la boucle continue à s'exécuter. Si elle est fausse, la boucle se termine (par exemple, `i < 10;`).

- **Expression d'itération**: Une instruction qui est exécutée à la fin de chaque itération. Elle est généralement utilisée pour mettre à jour la variable de contrôle (par exemple, `i++` pour incrémenter `i` de 1).

### Exemple d'utilisation de la boucle `for`

```javascript
function populateArray(number) {
    let array = [];
    for (let i = 0; i <= number; i++) {
        array.push(i);
    }
    console.log(array);
}
populateArray(100);
```

Dans cet exemple, la boucle `for` remplit un tableau avec les nombres de **0 à 100**.

## 2. La Boucle `while`

La boucle `while` est utilisée lorsque vous ne connaissez pas à l'avance le nombre d'itérations nécessaires. Elle continue à exécuter le bloc de code tant qu'une condition spécifiée est vraie.

```javascript
while (condition) {
    // Bloc de code à exécuter tant que la condition est vraie
}
```

- **Condition**: Une expression booléenne qui est évaluée avant chaque itération. Si la condition est vraie, la boucle continue à s'exécuter. Si elle devient fausse, la boucle s'arrête.

### Exemple d'utilisation de la boucle `while`

```javascript
let number = 0;
let array = [];
while (number <= 100) {
  array.push(number);
  number++;
}
console.log(array);
```

Ce code remplit un tableau avec les nombres de 0 à 100 à l'aide de la boucle `while`.

## 3. La Boucle `do...while`

La boucle `do...while` est similaire à la boucle `while`, mais elle garantit que le bloc de code est exécuté au moins une fois, même si la condition initiale est fausse.

```javascript
do {
    // Bloc de code à exécuter au moins une fois
} while (condition);
```

- **Condition**: Une expression booléenne qui est évaluée après chaque itération. Si la condition est vraie, la boucle continue à s'exécuter. Si elle devient fausse, la boucle s'arrête.

### Exemple d'utilisation de la boucle `do...while`

```javascript
let arrayTest = [];
let numberTest = 0;
do {
  numberTest = numberTest ++;
  arrayTest.push(numberTest);
} while (numberTest < 10);
console.log(arrayTest);
```

Même si la condition est initialement fausse, ce code affiche `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]` dans la console.

## 4. La Boucle `for...in`

La boucle `for...in` est utilisée pour parcourir les propriétés énumérables d'un objet. Elle permet de boucler à travers les clés d'un objet.

```javascript
for (let key in object) {
    // Bloc de code à exécuter pour chaque clé
}
```

- **key**: Une variable qui prend la valeur de chaque clé à chaque itération.

### Exemple d'utilisation de la boucle `for...in`

```javascript
let person = {
    name: "John",
    age: 30,
    job: "developer"
};

for (let key in person) {
    console.log(key + ": " + person[key]); // person[key] signifie que vous utilisez la VALEUR de la variable key comme nom de propriété
}
```

Ce code parcourt les propriétés de l'objet `person` et affiche leurs clés et leurs valeurs.

> Je précise que dans votre boucle for...in, vous devez utiliser `person[key]` pour accéder aux valeurs des propriétés de l'objet `person`, car `key` est une **variable** qui prendra les noms de propriétés de manière dynamique.

## 5. La Boucle `for...of`

La boucle `for...of` est utilisée pour parcourir les éléments d'une structure itérable, telle qu'un tableau.

```javascript
for (let element of iterable) {
    // Bloc de code à exécuter pour chaque élément
}
```

- **element**: Une variable qui prend la valeur de chaque élément à chaque itération.

### Exemple d'utilisation de la boucle `for...of`

```javascript
let colors = ["red", "green", "blue"];

for (let color of colors) {
    console.log(color);
}
```

Ce code parcourt les éléments du tableau `colors` et les affiche.

## Petit rappel de forEach

Contrairement à ses congénères ci-dessus, la méthode `forEach` ne peut s'appliquer qu'aux `tableaux` ! Il s'agit ici de créer une boucle qui va exécuter une fonction pour chaque éléments du tableau donné. Il n'y a pas de condition à remplir contrairement aux précédentes versions. Elle est destinée uniquement à apporter une modification ou une opération pour chaque élément du tableau.

```javascript
array.forEach(element => {
  // Bloc de code à exécuter pour chaque élément
});
```

### Exemple d'utilisation de la boucle `forEach`

```javascript
let fruits = ["Pomme", "Poire", "Banane", "Orange"];
fruits.forEach((fruit) => console.log(`Ceci est une ${fruit}`));
```
Ce code parcourt les éléments du tableau `fruits` et affiche chaque élément.

## Conclusion

Les boucles sont un élément fondamental de la programmation en JavaScript. Elles vous permettent d'automatiser des tâches répétitives, de parcourir des objets et des tableaux, et de manipuler des données de manière efficace. Choisissez la boucle qui convient le mieux à votre problème, et pratiquez leur utilisation pour devenir un programmeur JavaScript plus compétent.

N'hésitez pas à consulter la [documentation JavaScript](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Loops_and_iteration) pour en savoir plus sur les boucles et leurs fonctionnalités avancées.

> Created by [Lucas Ielli](https://github.com/LucasIelli)

