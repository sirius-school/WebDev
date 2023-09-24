<!-- omit in toc -->
# Manipulation de tableaux deuxième partie
<!-- omit in toc -->
## Table des matières
- [Introduction](#introduction)
- [`isArray`](#isarray)
- [`fill`](#fill)
- [`find`](#find)
- [`join`](#join)

## Introduction

Dans cette partie du cours, nous allons explorer d'autres méthodes importantes en JavaScript pour manipuler les tableaux. Nous allons notamment étudier les méthodes `isArray`, `fill`, `find`, et `join`. Ces méthodes sont des outils précieux pour manipuler les tableaux et les chaînes de caractères.

## `isArray`

La méthode `isArray` est utilisée pour vérifier si une variable est de type tableau (Array) ou non. Elle retourne `true` si la variable est un tableau, et `false` si ce n'est pas le cas. Cela peut-être fort utile dans une condition `if()...else`, il est parfois important de bien vérifier le type de données que vous récuperez avant de les manipuler.

Exemple d'utilisation :
```javascript
const myArray = [1, 2, 3];
const isItArray = Array.isArray(myArray); // Retourne true
```

## `fill`

La méthode `fill` permet de remplir tous les éléments d'un tableau avec une valeur donnée. Vous pouvez spécifier les indices de début et de fin pour délimiter la plage de remplissage.

Exemple théorique : 
```javascript
array.fill(valeur, début, fin);
```
- array : Le tableau que vous souhaitez remplir avec la valeur spécifiée.
- valeur : La valeur à insérer dans chaque élément du tableau.
- début (facultatif) : L'indice de départ à partir duquel la modification doit commencer. Par défaut, c'est 0 (le début du tableau).
- fin (facultatif) : L'indice de fin jusqu'auquel la modification doit aller. Par défaut, c'est la longueur du tableau.

Exemple d'utilisation :
```javascript
const myArray = [0, 0, 0, 0, 0];
myArray.fill(5, 1, 4); // Remplit les indices 1, 2 et 3 avec la valeur 5
// Résultat : [0, 5, 5, 5, 0]
```

## `find`

La méthode `find` est utilisée pour rechercher le premier élément dans un tableau qui satisfait une condition donnée. Elle renvoie la première valeur trouvée ou `undefined` si aucune valeur ne correspond à la condition.

Exemple d'utilisation :
```javascript
const numbers = [10, 25, 8, 30, 15];
const found = numbers.find(num => num > 20); // Trouve le premier nombre supérieur à 20
// Résultat : 25
```

## `join`

La méthode `join` est utilisée pour concaténer tous les éléments d'un tableau en une **chaîne de caractères**. Vous pouvez spécifier un séparateur qui sera inséré entre chaque élément.

```javascript
const words = ["Hello", "beautiful", "world", "!"];
const combined = words.join(" "); // Combine les éléments avec un espace entre chaque mot
// Résultat : "Hello beautiful world !"
```

> Created by [Lucas Ielli](https://github.com/LucasIelli)

