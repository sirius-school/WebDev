<!-- omit in toc -->
# Window & document
<!-- omit in toc -->
## Table des matières
- [L'objet Window \& Document](#lobjet-window--document)
- [Prompt](#prompt)
- [Alert](#alert)
- [Confirm](#confirm)
- [Manipuler le DOM](#manipuler-le-dom)
  - [textContent](#textcontent)
  - [innerHTML](#innerhtml)
  - [EventListener](#eventlistener)
  - [Math.Random() et Math.Floor()](#mathrandom-et-mathfloor)
    - [Math.floor()](#mathfloor)
    - [Math.random()](#mathrandom)
    - [Utilisation de Math.floor et de Math.Random](#utilisation-de-mathfloor-et-de-mathrandom)
  - [ParseInt \& ParseFloat](#parseint--parsefloat)
    - [parseInt()](#parseint)
    - [parseFloat()](#parsefloat)
  - [Les fonctions CallBack](#les-fonctions-callback)
  - [La méthode setTimeOut](#la-méthode-settimeout)

## L'objet Window & Document

L'objet Window permet de pointer vers le ``DOM``, qu'est ce que le dom? Lorsque votre navigateur charge votre page web, il commence par lire les métadonnées de votre fichier HTML. Vous l'avez déjà peut être remarqué mais dans la construction des métadonnées, il existe une balise insérée en premier dans votre page :
```html
<!DOCTYPE Html>
```

``DocType`` tenant pour Document Type, en l'occurence il s'agit d'un document de type HTML. Le DOM correspond à l'ensemble de l'arborescence du document HTML. En ``JavaScript`` grâce au mot-clé désignant l'objet document nous pouvons pointer vers un élément particulier du ``DOM`` et lui apporter des modifications. Par exemple : afficher ou cacher au click un menu déroulant. Pour pointer vers l'ensemble de ces éléments et performer une action sur la page HTML nous utilisons l'objet ``Window`` (fenêtre). Pour pointer vers un élément particulier il existe plusieurs méthodes utilisant l'objet ``document`` :

Pointer un élément du document en utilisant son id :
```js
document.getElementById("id");
```
Pointer un élément du document en utilisant son nom de classe :
```js
document.getElementsByClassName("className");
```
Pointer **tous** les éléments d'une balise HTML :
```js
document.getElementByTagName("tag");
```
Pointer l'élément dont l'attribut de la balise HTML name correspond au paramètre entré (par exemple dans le cadre d'un formulaire auquel nous aurions passé l'attribut name) :
```js
document.getElementByName("elementName");
```
Il est possible de récupérer les valeurs de ces éléments via l'objet value, nous aborderons ce concept dans divers exercices.

## Prompt

La méthode prompt est une méthode qui permet d'ouvrir une boite d'invite.
Elle s'exécute avant le chargement du site, en priorité sur toute autre opération. Elle attend d'être résolue pour charger la page. De ce fait, si on l'utilise pour une vérification ou une fonction, la valeur du prompt sera toujours récupérée prioritairement sur le reste de l'exécution du code. Nous verrons dans le module avancé à quoi correspondent les cycles de vie.
Cette boîte contient un champ permettant à l'utilisateur de rentrer une valeur (un texte, des chiffres, un nom). Cette valeur peut alors être récupérée via le sélecteur du prompt et réutilisée pour les passer par exemple en paramètres de fonction. Prenons un exemple d'utilisation et de syntaxe :

```js
let yourName = prompt("Comment t'appelles tu ?"); // Ex de réponse de l'utilisateur : Lucas
console.log(yourName);
```


Décortiquons l'exemple ci-dessus. On voit que j'ai assigné la méthode ``prompt`` en tant que valeur à ma variable ``yourName``. Il est en effet tout à fait possible de passer des méthodes ou des fonctions en tant que valeur de variable. La variable est alors de type objet, car une fonction ou une méthode sont des objets.
```js
prompt(message, défaut);
```
Dans le constructeur de ma méthode ``prompt`` il est possible de passer deux paramètres : le message que l'on veut afficher à l'utilisateur, et une valeur par défaut insérée dans l'input (le champs de saisie). Ce ne sont toutefois pas des paramètres obligatoires, vous pouvez lancer un prompt sans texte ni valeur par défaut via la commande suivante :
```js
window.prompt();
```
Les valeurs retournées : la valeur est directement enregistrée dans la variable contenant le prompt. Si je ``console.log`` cette variable j'aurais directement la valeur rentrée par l'utilisateur affichée dans la console. Les valeurs retournées sont automatiquement des ``chaînes de caractères``. Si vous devez récupérer des nombres, il faudra les convertir avant de pouvoir les utiliser ! Nous verrons dans le chapitre ``ParseInt`` et ``ParseFloat`` comment réaliser ces opérations.
 
## Alert

Il s'agit de nouveau d'une méthode pré-établie par ``JavaScript``. Dans ce cadre ci elle peut s'exécuter à n'importe quel moment du cycle de vie de la page web (provoquée par un click par exemple, ou une redirection de page, ou en retour d'une fonction). Elle est cependant limitée, la box ``alert()`` ne peut contenir qu'un message, elle ne possède pas d'invite. Par contre elle empêche l'utilisateur d'accéder à d'autres contenus tant qu'elle n'a pas été lue et fermée. Elle se comporte comme un modal, nous verrons plus loins dans le cours à quoi correspondent les *modals*, retenez simplement ce terme pour l'instant. Elle se compose donc d'un message et d'un bouton de confirmation. Elle a donc un but parfaitement **informatif**. Elle peut servir pour renvoyer le résultat d'une fonction sans avoir à passer par le ``console.log`` par exemple :

```js
window.alert("résultat de ma fonction");
```

## Confirm

La méthode ``confirm()`` est un peu plus élaborée. Elle se comporte également comme un modal et peut également être exécutée à n'importe quel moment du cycle de vie de la page, déclenchée par une action (au click sur un bouton par exemple). Elle ouvre une boite de dialogue contenant un message, un bouton *confirmer* et un bouton *annuler*. Le bouton confirmer renverra ``true``, alors que le bouton annuler renverra ``false``. Cela vous permet de faire ou non une action en fonction de la réponse de l'utilisateur.<br>
Exemple de la [MDN](https://developer.mozilla.org/fr/docs/Web/API/Window/confirm) :

```js
if(window.confirm("Une nouvelle fenêtre va s'ouvrir")){
    window.open("contact.html", "Vous êtes redirigé vers la page de contact");
}
```

Dans ce cas, la condition vérifie que la valeur renvoyée par la méthode ``confirm()`` soit true, si c'est le cas elle exécute la redirection.

## Manipuler le DOM

### textContent

``textContent`` est une propriété des éléments HTML permettant de modifier le texte contenu au sein de cet élément.
Pour ce faire il faut d'abord pointer l'élément, puis choisir sa propriété textContent et enfin la réattribuer à sa nouvelle valeur de type chaîne de caractère.

```js
document.getElementById("text").textContent = "Salut";
```

### innerHTML

Comme son nom l'indique, la propriété innerHTML permet de passer des balises HTML en plus du texte.

```js
document.getElementById("text").innerHTML = "<span>Salut</span>";
```

### EventListener
Permet d'ajouter une "écoute" des évènements sur un élément HTML.

```js
document.getElementById("btn").addEventListener("click", function maFonction(){
    console.log("La réaction au click fonctionne.");
})
document.getElementById("btn").addEventListener("click", () => {
  console.log("La réaction au click fonctionne.");
});
```


L'exemple ci-dessus montre que la méthode ``addEventListener`` a été ajoutée sur l'élément dont l'ID est ``#btn`` (bouton). On demande à la méthode d'écouter tout les clicks sur cet élément et pour chaque click de lancer la fonction ``maFonction()`` qui elle même lance un ``console.log()``.
Dans d'autres termes, l'``EventListener`` va observer/écouter/attendre les évènements tels que le click, le survol de la souris, et réaliser une fonction que vous aurez programmé lorsque l'utilisateur va clicker ou survoler (par exemple) l'élément HTML avec sa souris.
Ce que l'on appelle **"gestionnaire d'évenement"** ou **"handleEvent"** est simplement le bloc de code appellé lors de la détection de cet évenement. Dans l'exemple ci-dessus il s'agit d'un simple console.log. On peut donc traduire le handleEvent par "que faire si l'utilisateur click sur le bouton".
Par exemple il peut s'agir de l'ouverture d'une boite de dialogues ou bien des évènements peuvent se déclencher au chargement de la page, au click, au double click, au survol de la souris, lors du chargement de nouvelles données, à la redimension d'une page, ou à sa fermeture, lorsque l'utilisateur appuie sur une touche de son clavier.

### Math.Random() et Math.Floor()

L'objet Math permet de recevoir plusieurs méthodes. Pour un aperçu des méthodes possibles voici un lien vers la [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Math)

Celles qui nous intéressent sont les méthodes ``floor()`` et ``random()``.

#### Math.floor()

Renvoit un entier qui est plus petit ou égal au nombre passé en paramètre de la méthode ``floor()``. Par exemple:
```js
let floorNumber = Math.floor(14.32);
//valeur de floorNumber: 14
```

#### Math.random()

Renvoit un nombre "flottant", c'est à dire qu'il est très probable d'obtenir un chiffre avec une décimale, compris entre 0 et le chiffre donné en paramètre de la méthode ``random()``. Par exemple :

```js
let randomNumber = Math.random() * 18;
console.log(randomNumber);
```
Output console, exemple : ``7.74``

#### Utilisation de Math.floor et de Math.Random

Comme nous l'avons vu précédemment un simple ``Math.random()`` peut poser problème si on désire obtenir un chiffre aléatoire qui soit un entier.
Pour obtenir un chiffre aléatoire entier il suffit de passer le ``Math.random()`` en paramètre d'un ``Math.floor()``. Par exemple :

```js
function getRandomInt(param) {
  return Math.floor(Math.random() * param);
}
```
Petit exemple que vous utiliserez :

```js
let randomNumber = Math.floor(Math.random() * 256);
```
Output console, exemple : ``189``

Dans l'exemple ci-dessus la valeur de notre variable ``randomNumber`` sera un entier compris entre 0 et 256 (256 exclu ⚠️), par exemple 133, n'hésitez pas à essayer par vous même en faisant un ``console.log(randomNumber)`` et en modifiant le paramètre pré-établi.

- Tout petite mise en pratique :

*Utiliser un chiffre aléatoire compris entre 0 et 255 pour générer un ``background-color`` aléatoire en remplaçant les valeurs ``RGB`` par la valeur d'un ``random``. Pour effectuer le changement de couleur, créer un bouton qui sera l'interaction avec l'utilisateur.*
<br>

On peut également l'utiliser pour pointer aléatoirement un index dans un tableau.<br>
Par exemple:
```js
console.log(myArray.length);
```
On commence par trouver la longueur du tableau sur lequel on désir pointer un index aléatoire. Dans ce cas ci imaginons un tableau de 12 éléments donc avec des index de 0 à 11.

```js
let randomNumber = Math.floor(Math.random() * 12);
```
On défini la limite du random à 12 car Math.random() exclu le 1 qui est multiplié ensuite par 12. Donc si un tableau est long de 12 éléments il possède 11 index étant donné que le premier index est initialisé à 0.

```js
console.log(myArray[randomNumber]);
```
On affiche ensuite l'élément du tableau qui correspond à la valeur du random contenu dans la variable randomNumber.

```js
let randomNumber = Math.floor(Math.random() * myArray.length);
console.log(myArray[randomNumber]);
```
Cette façon d'écrire nous donnera un résultat peu importe la longueur du tableau.

### ParseInt & ParseFloat

Ces méthodes permettent de convertir un chiffre de type ``string`` en type ``number`` et de les rendre disponible aux opérations mathématiques :
```js
parseInt();
parseInt("valeur à convertir", base);
```
#### parseInt()

Permet de convertir un chiffre **entier** de type ``string`` en un chiffre **entier** de type ``number``. Cette méthode requiert deux paramètres. La valeur à convertir, et la base. La base est un chiffre compris entre 2 et 36, elle peut par exemple convertir une image en chiffre afin de les stocker dans une base de données. Retenez que la base à utiliser est la base ``décimale`` correspondant au chiffre **10**. Votre code se présentera donc sous cette forme :

```js
console.log(parseInt("14", 10));
```

Pour aller plus loin : la doc' [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/parseInt)

#### parseFloat()

Permet de convertir un chiffre à virgule (décimale) de type ``string``, en un chiffre à virgule de type ``number`` :
```js
console.log(parseFloat("3.14", 10));
```
Cette méthode possède également deux paramètres, la valeur à convertir, et la base (toujours 10 dans notre cas).

Pour aller plus loin : la doc [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/parseFloat)


### Les fonctions CallBack

Vous avez déjà eu l'occasion de les manipuler à plusieurs reprises et vous les avez déjà vues sur MDN. Les fonctions ``callback`` sont des fonctions de rappel appelées au sein d'autres fonctions dans leurs paramètres. Par exemple dans un ``foreach``, ou un ``addEventListener``.

```js
let siriusTeamArray = ["Jeremy", "Ganaëlle", "Lucas"];
siriusTeamArray.forEach((element) => {
    console.log(element);
})
```
Dans l'exemple ci-dessus la fonction callback est déclarée à l'aide de la synthaxe EcmaSript6, elle reçoit un paramètre ``(el)`` et est déclarée à l'aide d'une ``arrow function``.

Exemple concret :
```js
document.getElementById("button").addEventListener("click", () => {
    console.log("Hello World");
}) // Arrow Function
document.getElementById("button").addEventListener("click", function(){
    console.log("Hello World");
}) // La même fonction mais en utilisant le mot-clé function
```

### La méthode setTimeOut

Permet d'exécuter une fonction ``callback`` après un temps donné, un ``délai``.
```js
setTimeout(() => {
  console.log("Hello World !");
}, 2000);
```
Dans l'exemple ci-dessus, ``2000`` représente 2000 millisecondes, autrement dit 2 secondes. La fonction callback renvoit un ``console.log()`` différé de 2 secondes.

Bon ! On arrive tout doucement au bout de la théorie et vous n'aurez non pas un mais deux exercices à la fin de celle-ci. **Let's go !**

![](https://media.giphy.com/media/BUKgXhu9o5kqI/giphy.gif)

[:arrow_right: Suite du cours : *Boucles*](./boucles.md)

[:rewind: Retour au sommaire du cours](../../README.md)

> Created by Julie Vanderbyse
> 
> Edited by [Jeremy Scala](https://github.com/scalajeremy) & [Lucas Ielli](https://github.com/LucasIelli)

 


