<!-- omit in toc -->
# Les fonctions et les conditions
<!-- omit in toc -->
## Table des matières
- [Les fonctions (functions)](#les-fonctions-functions)
- [Les conditions](#les-conditions)
  - [If...else](#ifelse)
  - [Switch Case](#switch-case)
- [Conclusion](#conclusion)

## Les fonctions (functions)

Une fonction est un ensemble d'instructions menant à la réalisation d'une tâche. Par exemple je souhaite afficher mon prénom dans la console avec un petit message de bienvenue adapté lors de ma connexion. On peut imaginer une fonction telle que celle-ci :

```js
function helloWhenConnected(name) { 
    let name = name;
    console.log(`Salut ${name}`); // Concaténation avec des backticks
    console.log("Salut " + name); // Concaténation avec le symbole +
}; 
 
helloWhenConnected("Lucas");
``` 
 
Résultat dans la console : ``Salut Lucas``

Une fonction contient un constructeur ``()`` qui peut recevoir un ou plusieurs paramètres comme dans l'exemple ci-dessus ``(name)`` et les instructions à executer englobées via ``{}``, grâce à ces éléments on devine donc que la fonction est en fait de ``type objet``. On la définit sous plusieurs formes, elle est déclarée à l'aide du mot-clé ``function``. Nous verrons plus tard qu'il est également possible de la déclarer sous forme d'une constante à l'aide ce que l'on appelle ``arrow function`` qui est un standard **ECMAscript6**. 

Une fonction peut retourner une valeur, on peut par exemple l'utiliser pour réaliser des opérations : 

```js
function multiply(a, b){ 
    return a * b; 
}; 
console.log(multiply(2, 4));

``` 
Output console : ``8``

Dans ce bout de code on appelle la fonction à l'aide de son nom suivit de son constructeur comprenant les deux paramètres que j'ai décidé de lui attribuer ``(2, 4)``. Vous le comprendrez, les paramètres défini lors de la construction de la fonction sont en réalité une valeur abstraite destinée à être remplacée par une donnée. Cette donnée est intégré lors de l'appel à la fonction. Pour lancer une fonction il faut en effet faire appel à elle, pour ce faire vous l'avez constaté il suffit d'indiquer le nom de la fonction désirée suivie de son constructeur () et du point virgule. 

Exemple d'appel de fonction:

```js
multiplication(2,4);
``` 

Observez de nouveau la fonction ``helloWhenConnected()`` et la fonction ``multiplication()``, n'y-a-t-il pas une différence dans la syntaxe ? Le mot-clé ``return`` apparaît dans la seconde fonction. Sans lui le résultat de l'opération ne serait tout simplement pas retourné à l'écran.

## Les conditions

L'explication est dans le titre. Parfois, vous serez amenés à performer une fonction, une série d'instructions, uniquement si une condition est remplie (ou non). Les conditions utilisent les opérateurs de comparaison pour s'aider à prendre une décision en fonction des paramètres qui leur sont fournis. 

Par exemple : J'hésite à manger une barre de chocolat plutôt qu'une pomme. Mon médecin traitant m'a fait la remarque de diminuer sur le sucre, je me renseigne sur les taux de sucres de ma barre chocolatée et de ma pomme. Celui de ma pomme est inférieur à celui de ma barre chocolatée :arrow_right: je décide de manger la pomme (dans le meilleur des cas, l'erreur est humaine, pas mathématique). 

Nous allons voir deux types de conditions : ``if...else``, et ``switch Case``. 

### If...else

if...else est littéralement traduite par "si...sinon...". Si ma condition est remplie, je performe mon opération. Sinon je ne fais rien ou je prévois une autre opération à réaliser dans ce cadre. 

Par exemple: 

```js
if(isConnected === true){ 
    helloWhenConnected("Lucas"); 
} else { 
    redirectTo("/login") 
};
```
Si ma variable ``isConnected`` est vérifiée à true, je lance ma fonction ``helloWhenConnected("Lucas")`` sinon, je redirige mon utilisateur vers la page de login. Plutôt simple non? Il suffit de dire explicitement ce que vous désirez à votre ordinateur et il s'en occupe !

Quelques conditions particulières, qu'on appelle "truthy" et "falsy":

- ``0`` est le seul nombre qui retourne toujours ``false``.
- N'importe quel autre nombre (même les nombres négatifs) retourne ``true``.
- ``""`` une chaîne de caratères vide retourne `false`.
- N'importe quelle autre chaîne de caractères non-vide retourne ``true``.
- `{}` et ``[]`` les objets et tableaux vides ou non retournent toujours ``true``.
- `null`, ``undefined``, ``NaN`` retournent toujours ``false``.

### Switch Case

Pour ce qui est du ``switch Case``, la syntaxe et le mode de fonctionnement est assez différent. Il permet en réalité d'évaluer un plus grand nombre de conditions que dans le cadre du ``if...else``

```js
let siriusTeamArray = ["Jeremy", "Ganaëlle", "Lucas", "Kevin", "Laetitia"]; 
 
switch (siriusTeamArray[0]) { 
  case "Jeremy": 
    console.log("Salut Jeremy") 
    break;
 
  case "Ganaëlle": 
    console.log("Salut Ganaëlle") 
    break; 
 
  // incorporez autant de case que vous le souhaitez 
 
 default: 
    redirectTo("/login"); 
    break; 
}
```
Switch, passe de cas en cas jusqu'à trouver une égalité avec le paramètre entré dans son constructeur. ``SI`` l'indice 0 de mon tableau ``siriusTeamArray`` est égal au cas ``(case)`` "Jeremy" alors la console affichera ``console.log("Jeremy")`` et la vérification des cas suivant s'arrête à l'aide du mot-clé ``"break;"`` (**indispensable** sinon le code entre dans une **boucle infinie**, c'est à dire le meilleur moyen pour faire planter votre navigateur). Sinon il passe au cas suivant.

## Conclusion 

Vous voici avec une première introduction complète au langage et à sa syntaxe. Nous allons maintenant pouvoir passer à la pratique. Pour réaliser votre projet, aidez-vous des ressources que vous pouvez trouver sur le net et gardez la théorie à portée de main.

Bon travail !

![](https://media.giphy.com/media/13GIgrGdslD9oQ/giphy.gif)

[:arrow_right: Suite du cours : *Window & document*](./window_document.md)

[:rewind: Retour au sommaire du cours](../../README.md)

> Created by Julie Vanderbyse
> 
> Edited by [Jeremy Scala](https://github.com/scalajeremy) & [Lucas Ielli](https://github.com/LucasIelli)