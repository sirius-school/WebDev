<!-- omit in toc -->
# Manipulation de tableaux première partie

Avant de vous lancer dans les exercices nous allons apprendre comment manipuler vos données contenues dans un tableau.
<!-- omit in toc -->
## Tables des matières
- [Opérations de tableaux (arrays operations)](#opérations-de-tableaux-arrays-operations)
  - ["Boucler" dans un tableau](#boucler-dans-un-tableau)
  - [Ajouter une donnée](#ajouter-une-donnée)
  - [Supprimer la dernière donnée](#supprimer-la-dernière-donnée)
  - [Supprimer la première donnée](#supprimer-la-première-donnée)
  - [Ajouter une donnée à l'indice 0](#ajouter-une-donnée-à-lindice-0)
  - [Supprimer une donnée grâce à son indice\[\]](#supprimer-une-donnée-grâce-à-son-indice)
  - [Copier un tableau](#copier-un-tableau)
- [Méthodes](#méthodes)
  - [findIndex](#findindex)
  - [Filter](#filter)
  - [Reduce](#reduce)
  - [Map](#map)
  - [Includes](#includes)
  - [Sort](#sort)
- [Petite précision !](#petite-précision-)

## Opérations de tableaux (arrays operations)

### "Boucler" dans un tableau

Votre première loop, la boucle ``.forEach()`` est *la* boucle que vous devez utiliser dès que vous entendez le mot ``Array``. En effet elle vous permettra d'afficher tous les éléments d'un tableau et ce un par un :

```js
let fruits = ["Pomme", "Orange", "Fraise"];

fruits.forEach((fruit) => {
  console.log(fruit);
});
```
Output console : ``Pomme`` ``Orange`` ``Fraise``

### Ajouter une donnée

Tu souhaites ajouter des données dans ton tableau ``(.push)`` :

```js
let fruits = ["Pomme", "Orange", "Fraise"];

fruits.push("Kiwi");

console.log(fruits);
```
Output console : ``["Pomme", "Orange", "Fraise", "Kiwi"]``

### Supprimer la dernière donnée

Avec ``.pop()`` tu pourras supprimer le dernier élément de ton tableau :

```js
let fruits = ["Pomme", "Orange", "Fraise", "Kiwi"];

fruits.pop();

console.log(fruits);
```
Output console : ``["Pomme", "Orange", "Fraise"]``

### Supprimer la première donnée

``.shift()`` fonctionne comme .pop() mais supprimera le premier élément du tableau :

```js
let fruits = ["Pomme", "Orange", "Fraise", "Kiwi"];

fruits.shift();

console.log(fruits);
```
Output console : ``["Orange", "Fraise", "Kiwi"]``

### Ajouter une donnée à l'indice 0

```js
let fruits = ["Pomme", "Orange", "Fraise"];

fruits.unshift("Kiwi");

console.log(fruits);
```
Output console : ``["Kiwi", "Pomme", "Orange", "Fraise"]``

### Supprimer une donnée grâce à son indice[]

Si vous souhaitez supprimer un élément et que vous connaissez son indice, utilisez ``.splice()`` dans les parenthèses indiquez l'indice de l'élément que vous voulez supprimer et le nombre d'éléments que vous souhaitez supprimer :

```js
let fruits = ["Pomme", "Orange", "Fraise"];

fruit.splice(1, 1);

console.log(fruits); 
```
Output console : ``["Pomme", "Fraise"]``

### Copier un tableau

``.slice()`` le mot ressemble beaucoup à celui du dessus alors attention 😉 :

```js
let fruits = ["Pomme", "Orange", "Fraise"];

let copyFruits = fruit.slice();

console.log(copyFruits);
```
Output console : ``["Pomme", "Orange", "Fraise"]``

## Méthodes

### findIndex

La méthode findIndex permet de trouver une correspondance entre un élément et son index dans le tableau. Elle renvoie l'index du premier élément répondant à la condition. Si il ne trouve aucune correspondance la valeur renvoyée sera de -1 (false). Continuons avec la variable ``fruits`` :
```js
const index = fruits.findIndex(element => element === "Pomme");
console.log(index);
console.log(fruits[index]);
```

### Filter
Comme son nom l'indique, la méthode ``filter()`` permet d'appliquer un filtre personnalisé, et ensuite de renvoyer le résultat de ce filtre dans un nouveau tableau. Exemple d'utilisation :

```js
let fruits = ["Pomme", "Orange", "Fraise"];
let newArrayFruits = fruits.filter(element => element === "Pomme");
console.log(newArrayFruits);
```
Output console : ``["Pomme"]``

Dans l'exemple ci-dessus le filtre demande de retourner les éléments du tableau correspondant **strictement** à la chaîne de caractère ``"Pomme"``. On stock la valeur du filtre à l'intérieur d'une nouvelle variable qui contiendra après application le nouveau tableau d'éléments retourné par filter.

### Reduce

Permet d'accumuler les valeurs d'un tableau et de les réduire à une valeur **unique**. Par exemple, imaginons un tableau d'objet dans lequel une clé contient de nouveau un tableau. Je souhaite créer un nouveau tableau contenant toutes les valeurs de cette clé pour chaque objet. Dans ce cas la console affichera les valeurs pour chaque objet rassemblés au sein d'un nouveau tableau :

```js
const arrayNum = [1, 2, 3, 4];
const sum = arrayNum.reduce(
  (previousValue, currentValue) => previousValue + currentValue
);
console.log(sum);
```

Output console : ``10``

### Map
La fonction ``map()`` performe une fonction sur chaque élément du tableau et renvoit un nouveau tableau contenant les éléments transformés :
```js
let numberArray = [1, 2, 3, 4];
let byTwoArray = numberArray.map(element => element * 2);
console.log(byTwoArray);
```

Output console : ``[2, 4, 6, 8]``

### Includes
``includes()`` va chercher une occurence dans le tableau et renvoit une valeur booléenne ``true`` ou ``false`` en fonction de si il a trouvé un élément équivalent ou non :

```js
let fruits = ["Pomme", "Orange", "Fraise"];
console.log(fruits.includes('Fraise'));
```

Output console : ``true``


### Sort
La méthode ``sort()`` trie les éléments d'un tableau, **dans ce même tableau**, et renvoie le tableau. Par défaut, le tri s'effectue sur les éléments du tableau convertis en *chaînes de caractères* et triées selon les valeurs des unités de code UTF-16 des caractères.
```js
let sortArray = [10, 1, 3];
console.log(sortArray.sort());
```

Output console : ``[1, 10, 3]``


Si on veut trier un tableau de **nombre**, il convient d’utiliser la méthode suivante :

```js
let sortArray = [1, 10, 3];
console.log(sortArray.sort((a, b) => a - b));
```

Output console : ``[1, 3, 10]``

## Petite précision !

Dans votre code vous avez encodé vous-même votre tableau **mais** quand vous serez développeur, vous utiliserez des tableaux qui ne seront peut-être pas dans votre code source et dont vous ne serez pas le "propriétaire". Donc si vous faites une suppression, ce sera **irréversible**... C'est à ce moment qu'on se dit heureusement il y a ``.slice()`` attention quand même de ne pas copier un tableau avec des milliers de données 😋

[:arrow_right: Suite du cours : *les fonctions et conditions*](./fonctions_conditions.md)

[:rewind: Retour au sommaire du cours](../../README.md)

> Created by [Lucas Ielli](https://github.com/LucasIelli)

