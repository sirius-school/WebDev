<!-- omit in toc -->
# Introduction JavaScript

<!-- omit in toc -->
## Table des matières

- [Qu'est-ce que JavaScript](#quest-ce-que-javascript)
- [Questionnaire rapide](#questionnaire-rapide)
  - [Question 1](#question-1)
  - [Question 2](#question-2)
  - [Question 3](#question-3)
  - [Question 4](#question-4)
  - [Question 5](#question-5)
- [La balise `<script>`](#la-balise-script)
- [Votre première fonction](#votre-première-fonction)
  - [`console.log()` un ami pour comprendre votre code](#consolelog-un-ami-pour-comprendre-votre-code)
  - [Où trouver la console](#où-trouver-la-console)
  - [Comment utiliser `console.log()`](#comment-utiliser-consolelog)
  - [À quoi cela sert-il](#à-quoi-cela-sert-il)
  - [Dernière astuce](#dernière-astuce)
- [Les variables](#les-variables)
  - [La syntaxe](#la-syntaxe)
  - [Les types de variables](#les-types-de-variables)
    - [1. Chaine de caractères (string)](#1-chaine-de-caractères-string)
    - [2. Les nombres (numbers)](#2-les-nombres-numbers)
    - [3. Booléens (booleans)](#3-booléens-booleans)
    - [4. Tableaux (arrays)](#4-tableaux-arrays)
    - [5. Objets (objects)](#5-objets-objects)
    - [6. Les constructeurs (constructors)](#6-les-constructeurs-constructors)
- [Les opérateurs (operands)](#les-opérateurs-operands)
- [Résumé](#résumé)
- [Conclusion](#conclusion)


## Qu'est-ce que JavaScript

Le langage **JavaScript** est un langage de programmation très utilisé dans le développement web. Il a été créé à l'origine pour rendre les pages web interactives en permettant aux développeurs d'ajouter des fonctionnalités dynamiques aux sites web. Depuis sa création, JavaScript est devenu l'un des piliers essentiels du développement web moderne.

Voici quelques points clés pour mieux comprendre ce qu'est **JavaScript** :

1. **Langage interprété côté client :** JavaScript est principalement exécuté sur le navigateur web de l'utilisateur (côté client), ce qui signifie que le code est exécuté sur l'ordinateur ou l'appareil de l'utilisateur plutôt que sur le serveur web. Cela permet aux pages web de réagir instantanément aux actions de l'utilisateur, comme cliquer sur un bouton, remplir un formulaire ou faire défiler une page.

2. **Polyvalence :** JavaScript est un langage polyvalent. Il peut être utilisé pour créer des fonctionnalités interactives et dynamiques sur les sites web, mais il est également utilisé pour le développement côté serveur (à l'aide de plateformes telles que Node.js) et dans de plus rares cas dans le développement d'applications mobiles et de jeux.

3. **Syntaxe facile à apprendre :** La syntaxe de JavaScript est relativement simple et similaire à d'autres langages de programmation comme Java et C++. C'est un bon choix pour débuter dans le développement web.

4. **Manipulation du DOM :** JavaScript est utilisé pour interagir avec le DOM (Document Object Model), qui est la représentation de la page web chargée dans le navigateur. Cela signifie que vous pouvez utiliser JavaScript pour modifier dynamiquement le contenu, le style et le comportement des éléments d'une page web sans avoir à recharger toute la page.

5. **Large communauté et bibliothèques :** JavaScript bénéficie d'une vaste communauté de développeurs et dispose d'une multitude de bibliothèques et de frameworks, tels que **React.JS**, **Angular.JS** et **Vue.JS**, qui facilitent le développement web et l'ajout de fonctionnalités plus avancées.

En résumé, JavaScript est un langage de programmation puissant qui permet de créer des **sites web interactifs et dynamiques**. C'est devenu un outil essentiel pour tout développeur web, je tiens à préciser que si vous souhaitez apprendre un framework JS il est indispensable d'apprendre le langage de base, ***JavaScript***.

[:arrow_up: Revenir au top](#table-des-matières)

## Questionnaire rapide

### Question 1
**Qu'est-ce que le DOM en relation avec JavaScript ?**
- A) Un langage de programmation côté client.
- B) Une représentation du code JavaScript côté serveur.
- C) La structure de fichiers utilisée pour stocker du code JavaScript.
- D) La représentation de la page web chargée dans le navigateur, avec laquelle JavaScript interagit.

### Question 2
**Quel est l'avantage principal de JavaScript en tant que langage côté client ?**
- A) Il permet d'exécuter du code sur le serveur pour une meilleure performance.
- B) Il rend les pages web plus esthétiques avec des animations.
- C) Il réagit instantanément aux actions de l'utilisateur sans recharger la page.
- D) Il est facile à apprendre pour les débutants en programmation.

### Question 3
**Quel rôle joue JavaScript côté serveur avec l'utilisation de Node.js ?**
- A) Il permet de créer des sites web complets (Frontend & Backend).
- B) Il crée des animations interactives sur les sites web.
- C) Il gère le style et la présentation des pages web.
- D) Il interagit avec le navigateur pour charger les pages web.

### Question 4
**Qu'est-ce que les bibliothèques et les frameworks JavaScript apportent au développement web ?**
- A) Ils fournissent des outils pour gérer les bases de données.
- B) Ils permettent de développer des jeux en ligne.
- C) Ils facilitent la création de pages web interactives et dynamiques.
- D) Ils sont utilisés pour stocker et gérer les fichiers JavaScript.

### Question 5
**Pourquoi est-il important d'apprendre le langage de base JavaScript avant d'utiliser un framework JavaScript tel que React.JS, Angular.JS ou Vue.JS ?**
- A) Les frameworks JavaScript ne sont pas compatibles avec les navigateurs modernes.
- B) Le langage de base JavaScript est obsolète et doit être utilisé uniquement pour le support de vieux navigateurs.
- C) Les frameworks JavaScript ne sont pas populaires auprès des développeurs web.
- D) Les frameworks JavaScript sont construits sur la base du langage de base JavaScript, donc une bonne compréhension de ce dernier est nécessaire pour les utiliser de manière efficace.

> Généré par ChatGPT en fonction de la théorie.

[:arrow_up: Revenir au top](#table-des-matières)

<!--
Généré par ChatGPT en fonction de la théorie.
Réponse au questionnaire

**Question 1:** Qu'est-ce que le DOM en relation avec JavaScript ?
- Réponse: D) La représentation de la page web chargée dans le navigateur, avec laquelle JavaScript interagit.

**Question 2:** Quel est l'avantage principal de JavaScript en tant que langage côté client ?
- Réponse: C) Il réagit instantanément aux actions de l'utilisateur sans recharger la page.

**Question 3:** Quel rôle joue JavaScript côté serveur avec l'utilisation de Node.js ?
- Réponse: A) Il permet de créer des applications web complètes.

**Question 4:** Qu'est-ce que les bibliothèques et les frameworks JavaScript apportent au développement web ?
- Réponse: C) Ils facilitent la création de pages web interactives et dynamiques.

**Question 5:** Pourquoi est-il important d'apprendre le langage de base JavaScript avant d'utiliser un framework JavaScript tel que React.js, Angular.js ou Vue.js ?
- Réponse: D) Les frameworks JavaScript sont construits sur la base du langage de base JavaScript, donc une bonne compréhension de ce dernier est nécessaire pour les utiliser de manière efficace.
-->

## La balise `<script>`

La balise `<script>` permet d'injecter du contenu JavaScript dans votre page HTML ou de simplement lier un fichier script à votre page. Elle est **essentielle** pour rendre vos pages web interactives et dynamiques. Durant la formation nous lierons un fichier JavaScript externe plutôt que d'insérer directement du code JavaScript dans cette balise, cela fait partie des **bonnes pratiques** à mettre en place dès le départ de votre apprentissage.

Pour utiliser un fichier JavaScript externe, nous devons insérer la balise `<script>` à l'intérieur de notre fichier HTML. Mais attention ! Il est important de la placer à un emplacement spécifique pour assurer le bon fonctionnement de notre code.

Ainsi, nous devons insérer la balise `<script>` non pas dans la section `<head>` de notre document (les méta-données), mais après la fermeture de la balise `<body>` dans notre fichier `index.html`, de cette manière :

```html
<!DOCTYPE html>
<html>
<head>
    <!-- Les méta-données, les styles et autres éléments -->
</head>
<body>
    <!-- Le contenu de la page -->
    <h1>Titre de la page</h1>
    <p>Contenu de la page...</p>

    <!-- La balise script pour lier notre fichier JavaScript externe -->
    <script src="script.js"></script>
</body>
    <!-- OU -->
    <script src="script.js"></script>
</html>
```

Pourquoi placer le script à cet endroit ? Eh bien, en plaçant la balise `<script>` à la fin du corps (`<body>`) de notre document, nous assurons que le navigateur a d'abord chargé l'ensemble des balises HTML, y compris les éléments avec lesquels nous souhaitons interagir dans notre fichier JavaScript. Ainsi, lorsque le fichier `script.js` est chargé, il peut accéder à ces éléments sans rencontrer de problèmes.

Si nous placions la balise `<script>` dans la section `<head>`, le fichier JavaScript pourrait être chargé avant que le reste du contenu ne soit totalement disponible, entraînant des erreurs et rendant difficile l'accès aux éléments souhaités. Cela pourrait provoquer des erreurs telles que des éléments "undefined" au lieu de pointer vers l'élément désiré.

En résumé, en plaçant la balise `<script>` à la fin du corps de notre document HTML, nous nous assurons que notre code JavaScript interagit correctement avec notre page web, ce qui est important, surtout lorsque nous commençons à apprendre et à utiliser JavaScript.

[:arrow_up: Revenir au top](#table-des-matières)

## Votre première fonction

### `console.log()` un ami pour comprendre votre code

En JavaScript, `console.log()` est une fonction très utile qui permet d'afficher des informations dans la console du navigateur. C'est un outil précieux pour les développeurs car il permet de vérifier ce qui se passe dans le code et d'obtenir des informations importantes pendant le processus de développement.

### Où trouver la console

Avant même d'écrire dans votre code il faut savoir ou le résultat (**l'output**) sera affiché 😛 Pour accèder à votre console et cela pour la plupart des navigateurs, vous pouvez faire un clic droit sur votre page web, choisir "Inspecter" ou "Inspecter l'élément" ou appuyer sur la touche "F12" de votre clavier, puis accéder à l'onglet "Console".

### Comment utiliser `console.log()`

Pour utiliser `console.log()`, vous devez simplement écrire `console.log()` dans un `fichier.js` et avoir bien mis la balise `<script>` dans votre HTML. Entre les parenthèses de `log()`, vous pouvez mettre ce que vous voulez afficher dans la console. Par exemple :

```javascript
console.log("Je vais enfin apprendre JavaScript chez Sirius School ! 🥰");
```

### À quoi cela sert-il

`console.log()` sert à plusieurs choses :

1. **Débogage (Debugging) :** Lorsque vous développez une application, il est courant d'ajouter des `console.log()` à différents endroits de votre code pour vérifier si certaines valeurs sont correctes ou pour voir si certaines parties du code sont exécutées.

2. **Afficher des informations :** Vous pouvez utiliser `console.log()` pour afficher des messages, des variables, des tableaux, des objets ou tout autre type de données que vous souhaitez examiner.

3. **Suivi de l'exécution :** Cela peut vous aider à suivre l'exécution de votre code et à comprendre dans quel ordre les instructions sont exécutées.

4. **Vérification des erreurs :** Si vous rencontrez des problèmes avec votre code, `console.log()` peut être un moyen rapide de trouver où se situent les erreurs.

### Dernière astuce

Lorsque vous débutez en JavaScript, `console.log()` est votre meilleur atout ! N'hésitez pas à l'utiliser autant que nécessaire pour comprendre comment votre code fonctionne et pour repérer d'éventuelles erreurs. Une fois que vous avez terminé de déboguer votre code, vous pouvez simplement commenter ou supprimer les `console.log()` pour rendre votre code plus propre.

> Faites confiance à `console.log()` et laissez-le vous aider à maîtriser la magie de JavaScript ! ✨

[:arrow_up: Revenir au top](#table-des-matières)

## Les variables

Une variable est un conteneur. Elle contient les informations dont nous avons besoin pour les fonctionnalités de notre application, notre site. Une variable c'est par exemple:
```js
const firstname = "Lucas";
```
``const`` (pour constante) détermine la portée de la variable, en l'occurence elle ne peut être réassignée à une nouvelle valeur car c'est une valeur constante, en effet, mon prénom est Lucas et sauf demande de ma part aux autorités communales, il en restera ainsi toute ma vie. 

``let`` défini une variable dont la valeur est réassignable, par exemple :
```js
let javascriptCoach = "Lucas";
```
Nous ne sommes à l'abri de rien, un évenement m'empêchant de donner cours pourrait avoir lieu, un remplaçant serait donc désigné, cette variable doit donc pouvoir être réassignable si besoin.

``var`` = Portée globale, fortement dépréciée.

``let`` = Portée limitée à celle du bloc courant. 

``const`` = Portée limitée à celle du bloc comme ``let`` mais n'est pas réassignable.

[:arrow_up: Revenir au top](#table-des-matières)

### La syntaxe

Nous savons du coup que ``let`` ou ``const`` désignent la portée de la variable.<br>
``firstname`` est le nom donné à ma variable.<br>
Un nom de variable est toujours unique.<br>
Un bon nom de variable est défini par la clareté de son utilité (il n'y a pas de doute possible quant à l'utilité de ma variable firstname, elle se réfère à un prénom).<br>
Un nom de variable débute toujours par une lettre minuscule, cependant si elle comporte plusieurs mots (tel que dans l'exemple "javascriptTeacher") la première lettre du second mot sera toujours écrite en majuscule. On appelle cette pratique le [*camelCase*](https://en.wikipedia.org/wiki/Camel_case) il s'agit ici d'un cas de bonne pratique, une sorte de convention en matière de rédaction de code Javascript.<br>
Le signe ``=`` en JavaScript ne signifie **pas** égal mais **assigne** une valeur à la variable.
``" "`` définit le type de la variable sur "string" qui signifie chaîne de caractère en français.<br>
Nous verrons dans le chapitre suivant les différents types de variables, il peut s'agir d'un nombre, d'un texte, d'un booléen (vrai ou faux), d'un tableau, etc... 
<br>
``;`` Le point virgule désigne la fin de la ligne, le navigateur comprend qu'il doit passer à la ligne suivante et continue la lecture du code. Si vous vous abstenez d'ajouter le point virgule il peut arriver des erreurs de lecture de votre navigateur. Il est donc indispensable de toujours l'ajouter quand vous passez à la ligne après avoir terminé une ligne de code.

[:arrow_up: Revenir au top](#table-des-matières)

### Les types de variables

Javascript est langage dit "typé", la bonne pratique veut que pour chaque nouvelle variable, nous "déclarions" son type. Par type on entend : est-ce-que ma variable est un nombre? Est-ce une chaîne de caractère? Est-ce un booléen (vrai ou faux)? Est-ce-que ma variable est un tableau? Ou un objet? Pour ce dernier, nous y reviendrons plus tard mais l'ensemble du langage est basé sur les objets, on dit de lui qu'il est orienté objet. Il s'agit d'une notion plus avancée que nous aborderons plus tard mais il est toujours utile de le mentionner. 

#### 1. Chaine de caractères (string)
Une chaîne de caractère représente un texte, elle peut contenir l'ensemble des caractères reconnu de votre clavier DONT des chiffres. Les chiffres seront ici interprêtés sous forme de caractère et ne pourront pas être utilisé comme une variable typée nombre, vous ne pourrez donc pas l'utiliser pour effectuer une opération. Pour définir une variable en tant que chaîne de caractère nous utilisons les guillements ``" "``. Retenez que ``"1"`` est une chaîne de caractère si j'additione la chaîne de caractère ``"2"``, je n'obtiendrai **pas** 3 mais bien ``"12"``. Cela n'est même pas une addition mais une **concaténation**, vous verrez souvent ce terme qui est important à connaitre.

Dans l'exemple ci-dessous nous déclarons la variable ``firstname`` et l'attribuons à ``new String()``. ``new`` représente une instruction (nouveau) qui créera une **nouvelle instance** totalement vide, et ``String`` l'objet que nous voulons créer. Il s'agit ici d'un objet global de type ``String`` (chaîne de caractère). Les **parenthèses** qui suivent ``String`` contiendront une donnée et celle-ci devra être entourée de **guillements** :

```js
const firstname = new String("Lucas");
```
Attention le résultat dans votre console sera ``String {'Lucas'}`` détaillé avec un index sur chacune des lettres de votre chaîne de caractère avec une valeur primitive ``"Lucas"``.

Vous pouvez préciser le type de variable que vous souhaitez :
```js
const firstname = String("Lucas");
```
Evidemment ceci ``const firstname = Number("Lucas");`` ne fonctionnera pas et le résultat sera **NaN** (not a number).

Plusieurs exemples de chaînes de caractère déclarés de façons plus "simples" mais moins détaillées :
```js
const firstname = "Lucas";
let age = '29 ans';
let job = `Web Coach en Sirius !`;
```
Comme nous l'avons vu précédement ma variable est préfixée ``let`` ou ``const`` en fonction de sa portée, le choix du nom est le plus explicite possible (firstname), elle est assignée grâce au signe ``=`` déclarée de type chaîne de caractère grâce aux guillemets ``" "``, et pour terminé, comme à chaque fin de déclaration le ``;`` qui indique au navigateur de passer à la ligne suivante. 

Imaginons que je souhaite afficher les valeurs de ces variables dans ma console:
```js
console.log(firstname + ", " + age + ", " + job);
```
Le résultat affiché dans la console sera :
``Lucas, 29 ans, Web Coach en Sirius !``

Cette opération est une concaténation. Le ``+`` est l'opérateur qui permet aux chaînes de caractères de se suivrent. Si vous êtes attentifs vous aurez remarqué que j'ai ajouté des virgules et des espaces entourées de guillements ``", "`` sans ça le résultat serait "Lucas29 ansWeb Coach en Sirius !"

Plutôt que de concaténer, il est possible d'utiliser la syntaxe des "backticks" ``" ` "`` et d'insérer la/les variable(s) directement dans la phrase. Comme ceci :

```js
console.log(`Je m'appelle ${firstname}, j'ai ${age} et je suis ${job}`);
```
Nous obtiendrons dans notre console :
``Je m'appelle Lucas, j'ai 29 ans et je suis Web Coach en Sirius !``

[:arrow_up: Revenir au top](#table-des-matières)

#### 2. Les nombres (numbers)

Grâce aux nombres vous pourrez réaliser un tas d'opérations utiles à votre application, paginations, boucles de rendu, calculs... Pas de panique, il ne faut pas être bon en math pour réaliser ces opérations, Javascript le fait pour vous, du moment où vous utilisez la bonne syntaxe afin de lui indiquer le travail qu'il a à effectuer.

Il est possible de déclarer une variable typée ``Number`` comme ceci :

```js
let firstNumber = new Number(1);
let secondNumber = Number(2);
```

Autre exemple simplifié de variable typée number :
```js
let firstNumber= 1; 
let secondNumber = 2;
```
Imaginons que je souhaite afficher le résultat de l'addition de ces deux nombres :
```js
console.log(firstNumber + secondNumber);
```
Le résultat (output) de cette opération sera ``3``.

Observez bien la différence entre les deux types de variables, pour réaliser l'opération (une addition en l'occurence) j'ai du indiquer à ma variable qu'il s'agissait d'un chiffre, pour ce faire il suffit tout simplement d'écrire vos nombres dépourvu de guillemets. 

Lorsque ma variable est typée "number" je peux réaliser des opérations mathématiques et obtenir un résultat cohérent. Si ma variable chaîne de caractères contenant des nombres je ne pourrais pas réaliser d'opérations en dehors de la concaténation. Gardez cela à l'esprit quand vous créez une nouvelle variable.

Dernière chose que vous devez savoir, il existe deux types de valeurs pour une variable ``Number`` :

```js
let firstNumber = 10; // Integer value
let secondNumber = 1.25; // Float value
```

#### 3. Booléens (booleans)

L'objet Booléen en javascript est déclaré de cette façon :
```js
let isConnected = new Boolean(false *or* true);
```
Décortiquons ce bout de code : 

``new`` représente l'instruction, ``Boolean`` l'objet devant être créé, on constate la présence du constructeur () il indique que l'objet devant être créé doit recevoir un paramètre pour être construit en l'occurence il peut recevoir ``true`` (vrai) ou ``false`` (faux) qui sont des valeurs booléennes, il est possible d'y insérer d'autres valeurs, ces dernières seront alors converties en valeurs booléennes. Par exemple: *null, undefined, 0, -0, ou une chaîne de caractère vide " "*, sera convertie en ``false``. Si la valeur insérée est valide, par exemple une chaîne de caractère telle que "Salut" elle sera convertie en ``true``.

Ma variable ``isConnected`` a pour but de vérifier si mon utilisateur est connecté ou non. Si il est connecté, la valeur attritubée sera ``true``, si pas elle sera ``false``. Un booléen ne reçoit que ces deux valeurs "vrai" ou "faux". Elle permet de performer des actions spécifique en vérifiant si l'état de cette variable est définie sur true ou false.

Par exemple, si mon utilisateur est connecté, je peux afficher son profil sur le client, si non, le client renvoit vers la page de connexion ou d'enregistrement. Les booléens sont particulièrement utiles lorsque vous utiliserez les méthodes de conditions telles que ``if/else`` ou ``switch case`` (que nous aborderons plus loin dans le cours).

Une autre manière de déclarer le type de votre variable booléenne :

```js
let isConnected = Boolean();
```
Attention si vous ne précisez pas de valeur dans les parenthèses, la valeur par défaut sera **false**.

Une façon simplifiée de déclarer un booléen :

```js
let isConnected = true;
let isConnected = false;
```

[:arrow_up: Revenir au top](#table-des-matières)

#### 4. Tableaux (arrays)

Les tableaux (ou Arrays) sont des conteneurs plus structurés que de simples variables. Une variable ne peut contenir qu'une information à la fois, un tableau peut en contenir plusieurs. De ce fait pour chaque information contenue dans un tableau, il lui est attribué un indice. Afin de pouvoir facilement récupérer l'information spécifique dont nous avons besoin dans ce tableau. Le premier élément d'un tableau est attribué à l'**indice 0**, le second à l'indice 1, le troisième à l'indice 2, etc...

**Veillez toujours à garder à l'esprit que le premier élément d'un tableau débute à 0.**

Le tableau est un élément essentiel du langage, il permet de récupérer, stocker et manipuler facilement les données. Pour définir le type tableau il faut indiquer à JavaScript que vous souhaitez créer un nouveau tableau, il existe plusieurs façon de le faire :

```js
let studentArray = new Array();
``` 
Dans cet exemple nous déclarons la variable studentArray et l'attribuons à ``new Array();``. ``new`` représente une instruction (nouveau), et ``Array`` l'objet que nous voulons créer. Il s'agit ici d'un objet global de type Array (tableau). Les **parenthèses** qui suivent ``Array`` contiendront les données que tu dois séparer d'une **virgule** sans oublier d'utiliser la bonne syntaxe selon le type de variable que tu veux stocker dans ce tableau.
<br>
Vous pouvez ici aussi préciser le type de variable :

```js
let secondArray = Array();
```
Plus simplement la variable peut être déclarée directement avec des crochets qui correspondent à la syntaxe décrivant un tableau vide :
```js
let studentArray = [];
```
Exemple concret :
```js
let siriusTeamArray = ["Jeremy","Ganaëlle","Kevin","Laetitia","Lucas"];
``` 
Pouvez-vous me dire quel est l'indice de Laetitia dans ce tableau ❓
<br>
Dans ce dernier cas le tableau est directement déclaré avec des données. Si vous possédez déjà les données nécessaires vous pouvez pré-remplir votre tableau comme ci-dessus avec la variable ``siriusTeamArray``, sinon vous pouvez créer un tableau vide comme les deux exemples précédents, et utiliser une fonction spécifique de javascript (que nous verrons prochainement lors de la série d'exercice sur la manipulation des tableaux) pour le remplir une fois les informations acquises.

Nous utiliserons les tableaux à maintes et maintes reprises durant notre formation et vous continuerez à les utiliser chaque jour dans votre prochain boulot de Web Dev en herbe. Il est donc primordial que cette notion soit intégrée.

Pour accéder à l'information contenue dans mon tableau je peux soit : 

- Faire un rendu complet de mon tableau -> exemple :
```js
console.log(siriusTeamArray);
```
Qui imprimera dans votre console :  

``["Jeremy","Ganaëlle","Kevin","Laetitia","Lucas"]`` 

- Choisir l'élément spécifique que je souhaite afficher, si je connais son index -> exemple :
```js
console.log(siriusTeamArray[3]);
```
La console imprimera alors ``"Laetitia"``

Propriétés et méthodes : 

Les tableaux possèdent de nombreuses méthodes et propriétés, comme la propriété ``length`` qui permet de calculer le nombre d'éléments présents dans le tableau. Grâce à cette propriété nous pourrons utiliser des boucles (il s'agit ici d'une méthode) permettant de créer des opérations sur chacun des éléments du tableau, ceci nous est permis grâce aux boucles ``for`` qui utilisent l'indice courant du tableau ainsi que sa longueur pour réaliser des opérations sur chacun des éléments du tableau jusqu'à sa fin grâce à la propriété ``length``. Nous verrons à quoi correspondent les boucles et leur intérêt plus tard.

**Retenez que les tableaux sont des éléments essentiels à la création de sites et d'applications dynamiques.**

[:arrow_up: Revenir au top](#table-des-matières)

#### 5. Objets (objects)

Retenez que Javascript est un langage **orienté objet**. Tout est construit à partir d'un objet (variables, méthodes, fonctions...). Les objets possèdent des propriétés, on peut les comparer aux objets de la vrai vie. Par exemple je peux créer un objet Chien qui possédera comme propriété une race, une taille, un poids, une couleur de pelage, un âge, un nom. À ces propriétés viennent se joindre les valeurs correspondante au chien. Prenons comme exemple: 

```js
const chat = { 
        nom: "Lucky", 
        age: 4, 
        poids: "6 kgs", 
        couleur: "Tigré Gris"
};
```

Les objets possèdent des propriétés et des méthodes qui leur sont propres. Les objets sont une notion complexe mais indispensable, nous verrons plus tard dans le cours et en plus en détails une introduction à la programmation orienté objet. Pour l'instant retenez simplement la manière dont un objet se présente (comme ci dessus, par exemple, chaque valeur peut correspondre à un type, on peut donc retrouver des chaînes de caractères, des nombres, des tableaux ou d'autres objets au sein même des objets). Pour accéder aux valeurs des propriétés des objets vous pouvez simplement procéder de cette façon :

```js
console.log(chat.nom);
```
Résultat de la console : ``"Lucky"``.

Comme pour tout les types de variables vous pouvez utiliser :

```js
const chat = new Object();
const chien = Object();
```
Cependant pour pouvoir assigner des propriétes et des valeurs vous devrez ajouter :

```js
chat.nom = "Lucky";
chat.age = 4;
chien.nom = "Rex";
chien.age = 10;
```
Si vous avez remarqué grâce à ça j'ai réussi à assigner et je peux même réassigner une valeur aux propriétés de l'objet ``chat`` et ``chien`` alors que ma variable est une **constante (const)** 😁

[:arrow_up: Revenir au top](#table-des-matières)

#### 6. Les constructeurs (constructors)

Vous les avez vu plus haut pour chaque type de variable lorsque vous utilisez :

```js
String()
Number()
Boolean()
Array()
Object()
```
Il y a longtemps JavaScript nécessitait l'utilisation des constructeurs avant l'arrivée des **valeurs primitives** :

```js
let string = "";
let number = 0;
let boolean = true; // Or false
let array = [];
let object = {
  propriété: valeur,
};
// Attention ne réutilisez pas les noms de variables ci-dessus !
```

[:arrow_up: Revenir au top](#table-des-matières)

## Les opérateurs (operands)

Les opérateurs permettent de manipuler les variables. Nous avons déjà vu dans les exemples plus haut qu'il était possible d'additionner des nombres et de concaténer (mettre à la suite) des chaînes de caractères, mais il existe une multitude d'autres opérateurs. 

La [MDN](https://developer.mozilla.org/fr/docs/Web/JavaScript/Guide/Expressions_and_Operators) possède une liste de ces opérateurs, dont je vais vous donner quelques exemples, ils sont essentiels à connaître par coeur pour le bon fonctionnement des manipulations que vous souhaitez réaliser sur vos données.

``+`` ➡ Addition<br>
``-`` ➡ Soustraction<br>
``*`` ➡ Multiplication<br>
``/`` ➡ Division<br>
``=`` ➡ Affectation/Assignation<br>
``%`` ➡ Modulo (retourne le reste du nombre de gauche divisé par le nombre de droite par exemple 5/2 retournera 1, 4/2 retournera 0. Le modulo permet entre autre donc de vérifier si oui ou non le chiffre de gauche est divisible par 2)<br>
``<`` ➡ Le nombre de gauche est plus petit que le nombre de droite<br>
``>`` ➡ Le nombre de gauche est plus grand que le nombre de droite<br>
``>=`` ➡ Le nombre de gauche est plus grand ou égal au nombre de droite<br>
``<=`` ➡ Le nombre de droite est plus petit ou égal au nombre de droite<br>
``++`` ➡ Incrémentation (on augmente le nombre de 1)<br>
``--`` ➡ Décrémentation (on diminue le nombre de 1)<br>
``||`` ➡ Opérateur de comparaison "ou"<br>
``&&`` ➡ Opérateur de comparaison "et"<br>
``===`` ➡ Opérateur de comparaison "strictement égal à"<br>
``==`` ➡ Opérateur de comparaison "égal à"<br>
``!==`` ➡ Opérateur de comparaison "strictement différent de"<br>
``!=`` ➡ Opérateur de comparaison "différent de"<br>
``+=`` ➡ Affectation après addition<br>
``-=`` ➡ Affectation après soustraction<br>
``/=`` ➡ Affectation après division<br>
``*=`` ➡ Affectation après multiplication<br>

[:arrow_up: Revenir au top](#table-des-matières)

## Résumé

Les noms de variables ci-dessous ne doivent **pas être réutilisés** !
<br>
D'une part parce qu'ils ne décrivent pas ce qu'ils font ou feront. D'autre part parce que certains sont des **mots-clés déjà définis** par JavaScript !

```js
// Constuctors and new
let stringNew = new String(""); 
let numberNew = new Number(); 
let booleanNew = new Boolean();  // Default value : false
let arrayNew = new Array(); 
let objectNew = new Object();
// L'utilisation du mot-clé new est plus approprié dans la création d'objets plus complexes. Préfèrer donc utiliser la version simplifié pour les types String, Number et Boolean.

// Constructors
let string = String(""); 
let number = Number(); 
let boolean = Boolean();  // Default value : false
let array = Array(); 
let object = Object(); 

// Simplified version, primitive value.
let simpleString = "";
let simpleNumber = 0;
let simpleBoolean = true;
let simpleArray = [];
let simpleObject = {};
```

## Conclusion

Toute cette théorie n'est pas à retenir par coeur, mais vous devez savoir que cela existe et quand vous avez besoin vous pouvez toujours revenir sur ce cours ou simplement "googler".

![](https://media.giphy.com/media/xePnbnJiehT1e/giphy.gif)

[:arrow_right: Suite du cours : *Exercices*](./exo_tableaux.md)

[:arrow_right: Suite du cours : *les fonctions et conditions*](./fonctions_conditions.md)

[:rewind: Retour au sommaire du cours](../../README.md)

> Cours original : Julie Vanderbyse
>
> Modification : [Lucas Ielli](https://github.com/LucasIelli)