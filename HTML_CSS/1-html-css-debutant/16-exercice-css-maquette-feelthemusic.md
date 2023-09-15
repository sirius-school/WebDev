<!-- omit in toc -->
# Maquette Feel The Music

Il est temps de mettre en pratique toutes tes connaissances. Tu vas devoir réaliser une maquette complète! Il va falloir utiliser Flexbox pour la mettre en page!

Ton designer t'as envoyé le design en screenshot. À toi de le reproduire en HTML le plus fidèlement possible.

## :memo: Objectifs

- Réaliser une maquette sans HTML et CSS de base.
- Suivre des consignes précises.
- Apprendre à se débrouiller en allant lire la théorie vue ou la documentation.

## :white_check_mark: Evaluations

- Respect des consignes.
- La syntaxe est correcte.
- L'indentation est correcte.

## Consignes

- Sois le plus fidèle possible au modèle
- Chaque page doit contenir le même header et footer. Soit tu le fais sur une page et tu recopies le code sur les autres, soit tu utilises [le "hack" en JavaScript](#en-javascript) expliqué plus bas.
  - **Le header**: doit contenir le logo et le titre à gauche. Le menu est sur la droite.
  - **Le footer**: un menu à gauche vers d'autres pages (`href="#"`) et à droite les liens sociaux.
- Il te faut 3 pages:
  - **index.html**: la page d'accueil
    - Il faut le portrait de la femme
    - A sa droite doit se trouver le titre d'accroche, le sous-titre et le bouton pour arriver sur la page "comments.html" ("Join Now")
    - Il y a des bulles (enfin!) présentes en arrière-plan. Tu devras utiliser la propriété `z-index`et `border-radius`pour y arriver!
  - **discover.html**: la page qui présente le produit. Cette page est un peu plus libre.
    - Affiches quelques pochettes d'album que tu aimes, essayes de reproduire le style sur le screenshot.
    - Places un texte d'accroche
  - **comments.html**: la page avec le formulaire. Celui-ci ne doit pas être fonctionnel, juste stylisé comme sur le screenshot.
- Il te faut **une feuille** de style **"style.css"** lié à chacune de tes pages qui contient le style global de tout le site. Tu peux ensuite séparer tes styles dans différentes feuilles de styles pour chacune des pages. Pour ce faire il suffit de créer plusieurs balise `<link>` dans tes pages HTML. Voici un exemple de structure pour le projet:

```text
images
|___ landing-page-girl.png
styles
|___ bubulles.css
|___ comments.css
|___ discover.css
|___ index.css
|___ style.css
pages
|___ comments.html
|___ discover.html
index.html
```

```html
<!-- discover.html -->
<head>
  <link href="./styles/style.css">
  <link href="./styles/discover.css">
</head>
```

## Screenshot

### index.html

![index](./img/16/index.png)

![index-decoupe](./img/16/index-decoupe.png)

> La découpe en "bloc" et donc en éléments HTML!

### discover.html

![discover](./img/16/discover.png)

### comments.html

![comments](./img/16/comment.png)

## Les ressources

Tu peux retrouver les images et logos nécessaires à la réalisation de cet exercice par ici:

[https://github.com/sirius-school/WebDev/tree/main/HTML_CSS/1-html-css-debutant/assets/feelthemusic](https://github.com/sirius-school/WebDev/tree/main/HTML_CSS/1-html-css-debutant/assets/feelthemusic)

## Les couleurs

- Le fond de la page: #2F3038
- Le fond du formulaire: #202027
- Le fond des inputs: #2F3038
- Le fond du footer: #202027
- La couleur d'accent (rose): #BC3A80
- La couleur du bouton du formulaire (bleu): #1867A7

## La Google font

Pour reproduire la maquette il te faudra la police d'écriture `Poppins` pour ce faire, il suffit de l'importer via Google Font.

```css
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;800;900&display=swap');

*{
  font-family: 'Poppins', sans-serif;
}
```

## Petit hack pour répéter son header/footer sur plusieurs pages

Voici quelques solutions pour répéter notre header et footer sur chacune de nos pages sans devoir recopier et recoller du code à chaque fois. Ceci est un "hack" donc ce n'est pas la bonne solution pour développer un site web. Mais on va reproduire la logique qu'utilise un framework pour créer des sites.

[En JavaScript](#en-javascript) | [En JQuery](#en-jquery)

### En JavaScript

Alors là mes amis, on a une solution intéressante en JS, mais y a beaucoup de lignes. Du coup, je vais vous guider pas à pas sur la création et l'utilisation de cette méthode. Il y a des choses que vous n'avez pas encore vue comme les fonctions asynchrones ou les RegEx. Mais pas de panique, je vais vous en toucher un mot au fur et à mesure.

Soit tu recopies le code ci-dessous et tu lis les commentaires, soit tu parcours le pas à pas qui suit.

#### Le code complet

```js
// Préparons nos variables pour récupérer le nom de notre page
// Il y a plusieurs choses à comprendre ici
// regex: permet de supprimer l'extension de la page dans l'url
// path: récupère l'url de la page en cours
// match: récupère dans 'path' toute les valeurs qui correspondent à notre regex. Du coup on a la valeur sélectionnée en première position, puis la valeur sans l'extension en deuxième position. tout cela stocké dans un tableau
// page: contient la deuxième valeur de match (tableau) qui est le nom de notre page sans son extension
let regex = new RegExp(/\/([^/]+)\.[^/.]+$/);
let path = window.location.pathname;
let match = path.match(regex);
let page = match ? match[1] : null;

// fonction asynchrone qui va servir a ajouter une page HTML comme "texte" à l'intérieur d'une div
async function fetchHtmlAsText(url) {
  return await (await fetch(url)).text();
}

// fonction asynchrone qui va charger nos "header" et "footer". 
// on sélectionne nos balises "header" et "footer"
// et pour chacune on utilise notre fonction 'fetchHtmlAsText' pour charger la page header/footer
// peut-être que vous devrez changer les liens vers les fichiers html
// on a aussi une condition pour ne pas charger le footer sur la page index
async function loadComponents() {
  const headerDiv = document.querySelector("header");
  headerDiv.innerHTML = await fetchHtmlAsText("../components/header.html");
  if (page !== "index" && page !== null){
    const footerDiv = document.querySelector("footer");
    footerDiv.innerHTML = await fetchHtmlAsText("../components/footer.html");
  }
}

// Ici on commence le code pour faire en sorte que chaque lien dans ma nav ai la classe 'active' si c'est la page sur laquelle on est
// on commence par sélectionner tous nos liens dans header
function setActiveNavLink() {
  const navLinks = document.querySelectorAll("header a");

  // pour chaque liens on va récupérer l'attribut 'href'
  navLinks.forEach((link) => {
    const href = link.getAttribute("href");
    // On vérifie si le href correspond à la page
    if (page && href.includes(page)) {
      // On ajoute la classe active si c'est le cas
      link.classList.toggle("active");
    }
  });
}

// Ici on crée une fonction qui va ajouter le résultat de toutes nos fonctions quand elle aura le résultat des autres fonctions
async function initializePage() {
  await loadComponents();
  setActiveNavLink();
}

// Et enfin on fait appel à cette dernière fonction pour lancer toute la machine
initializePage();

```

#### Le pas à pas

Ce pas à pas n'est pas un exercice, je ne vous demande pas de trouver les réponses, je vous explique plutôt ce que le code fait. Vous pouvez copier/coller chaque bout de code à la suite.

Commençons par créer un nouveau fichier `script.js` qu'on ajoutera à toutes nos pages (pas header/footer).

##### Variables

On va avoir besoin de récupérer le nom de notre page actuelle pour pouvoir plus tard empêcher le footer d’apparaître sur la page 'index.html' ainsi que pouvoir changer le style de nos liens si on est sur la même page. On va utiliser la propriété [pathname](https://developer.mozilla.org/en-US/docs/Web/API/Location/pathname) de l'interface [Location](https://developer.mozilla.org/fr/docs/Web/API/Location).

```js
let path = window.location.pathname;
```

Ceci nous retourne une valeur texte qui contient la page sur laquelle on est actuellement. Seulement il y a un slash et une extension de fichier en trop qui gène un peu. On va devoir y remédier. Pour ce faire on va faire appel à une Regular Expression. Alors les RegEx c'est un peu compliqué mais ça va permettre de comparer les règles établies dans la RegEx et de supprimer une partie d'un string. Donc on va pas rentrer dans le détail de la création de cette RegEx, c'est compliqué et moi-même j'ai recours à l'aide d'internet pour en créer une. Donc la voici:

```js
let regex = new RegExp(/\/([^/]+)\.[^/.]+$/);
```

Ensuite on va chercher dans notre variable `path` après ce qui correspond à notre RegEx et on va stocker ça dans un tableau grâce à la méthode [match()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match). On aura un tableau avec 2 valeurs, celui qui correspond à la RegEx et la valeur corrigée par la RegEx. On va donc créer une dernière variable qui va récupérer la deuxième valeur de notre tableau pour enfin avoir le nom de la page.

```js
let match = path.match(regex);
let page = match ? match[1] : null;
```

##### La fonction pour charger du contenu

Alors maintenant il va falloir créer une fonction qui va récupérer le contenu d'une url de page et l'intégrer en tant que texte dans un élément au choix. Ceci doit se faire de manière asynchrone, c'est à dire qu'on doit attendre d'appeler la fonction et avoir le retour de la promesse (réponse) du fetch avant de pouvoir continuer. Votre code, en temps normal, s'exécute d'une traite, donc si on lui demande d'exécuter ce code sans avoir attendu la réponse, il ne saura pas quoi faire. Donc on va utiliser [async](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function) et [await](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/await). Une fois que le `fetch` a été effectué, on utilise la méthode `.text()` pour renvoyer le contenu de la page en texte. De nouveau on utilise `await` pour attendre que cette opération s"exécute et qu'on ai le résultat complet. Et pour finir on `return` le résultat quand la fonction est appelée. Il s'agit ici d'un concept assez poussé, on va donc pas allez plus loin dans l'explication pour le moment, vous le verrez plus tard en JavaScript.

```js
async function fetchHtmlAsText(url) {
  return await (await fetch(url)).text();
}
```

##### La fonction pour charger le contenu dans le header et footer

Alors maintenant qu'on a notre fonction qui va ajouter du contenu, il faut qu'on prépare une fonction qui va sélectionner notre header et footer et va y charger les pages grâce à la fonction précédente. De nouveau, on va avoir recours à une fonction asynchrone car de nouveau on doit attendre le chargement complet de la page pour que nos éléments soient créés et aussi on doit attendre que la précédente fonction ai fait son travail.

Pour commencer on va créer la fonction et y créer nos variables pour sélectionner notre header et footer.

```js
async function loadComponents() {
  const headerDiv = document.querySelector("header");
  const footerDiv = document.querySelector("footer");
  }
```

Ensuite on va ajouter à nos éléments sélectionnés le contenu avec `innerHTML` et notre fonction `fetchHtmlAsText`.

```js
async function loadComponents() {
  const headerDiv = document.querySelector("header");
  const footerDiv = document.querySelector("footer");
  headerDiv.innerHTML = await fetchHtmlAsText("../components/header.html");
  footerDiv.innerHTML = await fetchHtmlAsText("../components/footer.html");
  }
```

C'est quasi fini, il ne reste plus qu'à mettre une petite condition pour la page `index.html` pour ne pas avoir d'erreur car techniquement la balise `footer` n'existe pas sur cette page. Il faut utiliser la condition "si `page` est différent de `index`" mais aussi "si `page` est différent de `null`" car parfois au lancement de LiveServer, `page` est `null`. Donc comme ça, on évite les erreurs.

```js
async function loadComponents() {
  const headerDiv = document.querySelector("header");
  headerDiv.innerHTML = await fetchHtmlAsText("../components/header.html");
  if (page !== "index" && page !== null){
    const footerDiv = document.querySelector("footer");
    footerDiv.innerHTML = await fetchHtmlAsText("../components/footer.html");
  }
}
```

Maintenant on va lancer toutes ces fonctions et voir si ça fonctionne. Pour ce faire on va de nouveau préparer une fonction asynchrone, vu qu'elle doit attendre toutes les autres. Et on oublie pas d'appelez cette fonction à la fin de notre `script.js`

```js
async function initializePage() {
  await loadComponents();
}

initializePage();
```

###### Changer le style des liens

Maintenant que nous avons notre header, ça serait sympa de faire en sorte que les liens dedans aient un style différent si on est sur la page qui lui correspond. Cette fois-ci on va faire une fonction normale car elle s'exécutera à la suite de `loadComponents()` et donc le contenu sera déjà présent.

Commençons par créer la fonction et à sélectionner tous nos liens dans notre header avec un petit `querySelectorAll`

```js
function setActiveNavLink() {
  const navLinks = document.querySelectorAll("header a");
}
```

Ensuite il va falloir récupérer l'attribut `href` de chaque liens.

```js
function setActiveNavLink() {
  const navLinks = document.querySelectorAll("header a");
  navLinks.forEach((link) => {
    const href = link.getAttribute("href");
  }
}
```

Et maintenant on vérifie si le `href` contient le nom de la `page` grâce à la méthode [includes()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes) et si c'est le cas on ajoute la classe `active` avec la méthode [toggle()](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/toggle)

```js
function setActiveNavLink() {
  const navLinks = document.querySelectorAll("header a");
  navLinks.forEach((link) => {
    const href = link.getAttribute("href");
    if (page && href.includes(page)) {
      link.classList.toggle("active");
    }
  });
}
```

Et pour finir, on va mettre à jour notre fonction d'initialisation de page en ajoutant cette nouvelle fonction.

```js
async function initializePage() {
  await loadComponents();
  setActiveNavLink();
}
```

N'oubliez pas que pour que tout ça fonctionne il vous faut:

- une page `header.html` dans un dossier `components`
- une page `footer.html` dans un dossier `components`
- vos pages (index, comments, discover) doivent avoir une balise `header` et `footer`
- les liens doivent être au moins dans la balise `header`
- créer une classe `active` dans le css

### En Jquery

Voici une solution en Jquery, simple à mettre en place. Jquery c'est une bibliothèque JavaScript qui permet de faire pleins de choses en JS plus "facilement". Mais il faut aussi apprendre à l'écrire. Nous ici on va juste se contenter de recopier le code et de le comprendre.

Ajouter cette balise scripts à votre `<head>` pour inclure Jquerry à **chacune de vos pages** (index/discover/comments).

```html
<script src="https://code.jquery.com/jquery-3.5.1.js" integrity="sha256-QWo7LDvxbWT2tbbQ97B53yJnYU3WhH/C8ycbRAkjPDc=" crossorigin="anonymous"></script>
```

Créez une page `script.js`et ajoutez ce bout de code.

```js
$(function(){
  $("#header").load("../components/header.html"); 
  $("#footer").load("../components/footer.html"); 
});
```

> :bulb: Comme nous utilisons LiveServer pour tester nos pages, on peut mettre dans nos chemins "../" pour toujours revenir à la racine de notre site pour chercher après nos composants. Car si on ne le fait pas, les chemins seront différents si on est sur "index.html" qui est censé être à la racine et les autres pages qui sont dans un dossier "pages"

:exclamation: Attention, regarder bien le chemin vers le header/footer et ajuster vos fichiers en fonction.

:exclamation:**NPO**: ajouter la ligne qui permet d'inclure votre page script à **chacune de vos pages**.

```html
<script src="script.js"></script>
```

Ensuite on va ajouter nos ID définit plus haut à **chacune de nos balises header et footer** sur chacune de nos pages(index/discover/comments) pour définir l'endroit où le contenu de vos pages header et footer apparaîtront.

```html
<header id="header"></header>
<footer id="footer"></footer>
```

Vous pouvez maintenant créer une page `header.html` et `footer.html`, les placées dans un dossier "components" et elles seront ajoutées dans les balises header et footer.

#### Changer le style du menu (optionnel)

Si vous souhaitez changer le style du lien dans le menu en fonction de la page sur laquelle vous êtes, il va falloir de nouveau "hacker" le système un tout petit peu.

On va de nouveau utiliser un peu de JQuery pour parvenir à nos fins.

Créez une nouvelle page `nav.js`et copiez le code suivant:

```js
$('nav a').each(function() {
  if ($(this).attr('href') == location.href.split("/").slice(-1)){ $(this).addClass('isActive'); }
});
```

Ce code va sélectionner toutes nos balises `<a>` contenue dans notre balise `<nav>`. Donc ayez une navigation dans votre header qui fonctionne avec ce principe, ou alors changer la partie du script pour qu'elle corresponde à ce que vous avez vous. Ensuite le script va comparer le nom du fichier dans l'attribut `href`et le comparer au nom du fichier dans l'adresse du navigateur (sans le .html), si il y a une correspondance il va ajouter une classe 'isActive` à ce lien.

```html
<nav>
  <a href="discover.html">Discover</a>
  <a href="comments.html">Comments</a>
</nav>
```

Il reste à créer une classe CSS `isActive` avec les propriétés voulue et le tour est joué.

```css
.isActive{
  background-color: red;
}
```

:exclamation: N'oubliez pas de lier votre nouvelle page `nav.js` dans votre `header.html`!

##### Variante bonus (optionnel)

Si vous voulez une propriété différente pour chacun de vos liens, vous pouvez employez ce code Jquery.

```js
let fileName = location.href.replace(/\.[^/.]+$/, "").split("/").slice(-1);
$('nav a').each(function() {
  if ($(this).attr('href') == location.href.split("/").slice(-1)){ $(this).addClass(fileName); }
});
```

Ensuite il faudra un sélecteur CSS pour chacun des noms de fichier que vous avez.

```css
.fileName{
  font-size: 2em;
}
```

La différence ici c'est qu'il va ajouter une classe avec le même nom que le fichier. Du coup vous pouvez séparer vos styles pour chacun des liens du menu.

[:rewind: Retour au sommaire du cours](./README.md#table-des-matières)