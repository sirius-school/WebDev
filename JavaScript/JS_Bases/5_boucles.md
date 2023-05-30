<!-- omit in toc -->
# Les boucles
Le super guide sur le concept des boucles grâce à [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Loops_and_iteration)
Il existe plusieurs boucles :
- for (pour, tant que)
- do-while (faire, tant que)
- while (tant que)
- forEach (pour chaque élément || que vous connaisez déjà).
<!-- omit in toc -->
## Table des matières
- [La boucle for](#la-boucle-for)
- [La boucle do...while](#la-boucle-dowhile)
- [La boucle while](#la-boucle-while)
- [Petit rappel de forEach](#petit-rappel-de-foreach)

## La boucle for

Une boucle permet de performer une action tant que son cycle d'itérations n'est pas rempli par sa condition.

```js
function populateArray(number) {
    let array = [];
    for(let i = 0; i <= number; i++) {
        array.push(i);
    }
    console.log(array)
}
populateArray(100);
```
On pourrait traduire cette fonction de cette manière :
"**Pour** la variable ``number`` attribuée à ``100`` dans l'appel de la fonction et **tant que** la valeur de ``i`` est plus petite ou égale à la valeur de ``number``, on ajoute la valeur de ``i`` à notre tableau ``array``.

## La boucle do...while

Celle-ci exécute une action tant que sa condition n'est pas remplie. Elle ne s'auto incrémente pas contrairement à la boucle for qui elle possède une auto-incrémentation en paramètre de fonction. Exemple :

```js
let arrayTest = [];
let numberTest = 0;
do {
  numberTest = numberTest + 1; // ou numberTest++;
  arrayTest.push(numberTest);
} while (numberTest < 10);
console.log(arrayTest);
```
Output console : ``[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]``

Traduit littéralement : "**Fait** un push() de numberTest dans arrayTest **tant que** la valeur de numberTest est plus petit que 10."

Petit test quelqu'un sait me donner la différence entre la boucle ``for`` et la boucle ``do...while`` au niveau du résultat?

## La boucle while

Encore plus minimaliste, la boucle while part du principe que **tant que** sa condition n'est pas remplie elle exécute le bout de code donné. De la même façon que do...while, la boucle ``while`` n'auto incrémente pas sa condition, il faut le spécifier. L'utilité de ces boucles réside dans le fait que l'on peut leur passer comme condition true || false, contrairement à la boucle for qui ne vérifie que des valeurs numériques.

```js
let number = 0;
let array = [];
while (number <= 100) {
  array.push(number);
  number++;
}
console.log(array);
```

## Petit rappel de forEach

Contrairement à ses congénères ci-dessus, la méthode forEach ne peut s'appliquer qu'aux ``tableaux`` ! Il s'agit ici de créer une boucle qui va exécuter une fonction pour chaque éléments du tableau donné. Il n'y a pas de condition à remplir contrairement aux précédentes versions. Elle est destinée uniquement à apporter une modification || opération pour chaque élément du tableau. Par exemple, dans le cas où vous voudriez créer des éléments HTML de manière dynamique, nous pourrions dire que pour tous les éléments titre d'un objet, contenu dans un tableau, je génère un titre h2 dans mon code HTML.

```js
let siriusTeamArray = ["Jeremy", "Ganaëlle", "Lucas"];
siriusTeamArray.forEach((element) => console.log(`Salut ${element}`));
```
Output console : ``Salut Jeremy`` ``Salut Ganaëlle`` ``Salut Lucas``

La théorie pour cette partie du cours est **finie** !!! J'espère que vous êtes prêt pour les exercices 😈

![](https://c.tenor.com/Fthj62gIHrIAAAAM/falling-papers-people-are-awesome.gif)

[:arrow_right: Suite du cours : *Exercices !*](../ExercisesJS/)

[:rewind: Retour au sommaire du cours](../README.md#au-programme)

> Created by Julie Vanderbyse
> 
> Edited by Jeremy Scala & Lucas Ielli
