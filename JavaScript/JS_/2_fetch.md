<!-- omit in toc -->
# La méthode fetch()
<!-- omit in toc -->
## Tables des matières
- [Introduction](#introduction)
- [Fonctions Asynchrones](#fonctions-asynchrones)
- [fetch Kezaco?](#fetch-kezaco)
- [Construire une requête](#construire-une-requête)
  - [Ligne du temps d'une requête:](#ligne-du-temps-dune-requête)
  - [Les Headers](#les-headers)
  - [Les verbes](#les-verbes)
  - [Le corps de la requête](#le-corps-de-la-requête)
- [Construire une requête POST avec fetch()](#construire-une-requête-post-avec-fetch)
- [Manipuler le DOM](#manipuler-le-dom)
- [Petit exercice](#petit-exercice)
  
## Introduction

La méthode fetch() permet de contacter un serveur afin d'y récupérer/modifier/ajouter/supprimer des données.

Vous serez régulièrement amené à utiliser ce type de méthode (il existe différentes librairies qui possèdent leur propres méthodes), il est donc important de bien comprendre son fonctionnement.

Lorsque le navigateur lit et interprète votre code, il le fait de ligne en ligne mais pas que. Il peut passer d'une opération à la suivante avant la fin de l'exécution de la première. Il s'agit de programmation ``"asynchrone"`` que nous verrons prochainement. C'est ce qui arrive dans le cas d'une requête envoyée vers un serveur, le navigateur n'attend pas la réponse à cette requête avant d'exécuter la suite de votre code.

Si vous aviez prévu d'utiliser les données renvoyées par le serveur il faut donc spécifier au navigateur qu'il attend qu'un bout de code (la requête) soit exécuté avant d'utiliser ces données. Si vous ne l'indiquez pas, il est probable que la variable prévue pour stocker les nouvelles données reste vide aux yeux de votre navigateur.

## Fonctions Asynchrones

Arrivés à ce stade de la formation vous n'êtes pas sans savoir que le language JavaScript est synchrone. C'est à dire que votre navigateur lit ligne par ligne votre code. Les fonctions asynchrones permettent de sortir de cette boucle pour forcer votre navigateur à attendre la résolution d'une fonction avant une autre.

- Async :
Déclaré une fonction avec le mot-clé ``async`` devant signifie que votre fonction sera asynchrone. Elle utilise une valeur de retour appellée ``Promise``(promesse), elle sera résolue avec la valeur renvoyée par la fonction asycnhrone ou sera rompue s'il y a une erreur.
- Await :
Ce deuxième mot-clé est **indissociable** de async ! Await (attendre) attendra la résolution de la ``Promise`` de votre fonction asynchrone.

## fetch Kezaco?

Heureusement la méthode ``fetch()`` est exactement construite afin de palier au problème précedemment cité :

```js
fetch("http://l-url-de-la-requete.com/")
  .then(response => {
    console.log(response => response.json();
  })
  .then(response => {
    let data = response
   document.getElementById("text").textContent = data.text
  });
```

Dans l'exemple ci-dessus, on demande à la méthode de contacter un serveur via son url.

Ensuite le mot clé ``.then`` intervient (.then = ensuite). Grâce à lui, le navigateur va attendre qu'il ai reçu la réponse pour exécuter le bout de code qui le suit.

Lorsque ma réponse arrive, dans un premier temps je l'affiche dans ma console, et ensuite je la traite afin de retourner un format ``.json`` grâce à la méthode ``.json()``.
Un second ``.then`` intervient, c'est alors que je crée une variable ``data`` à laquelle j'attribue comme valeur, ma réponse.
Pour finir j'utilise une clé/valeur de la réponse de l'``API``(application programming interface) afin de modifier du contenu HTML.
<!-- Expliquer ce qu'est une API -->
Sans le ``.then``, le navigateur n'aurait pas attendu l'arrivée de la réponse et aurait tenté d'exécuter les bouts de code. Ce qui aurait renvoyé une erreur.

## Construire une requête

Pour construire une requête valide pour le protocole HTTP vous aurez besoin de plusieurs éléments :

- Le verbe de la requête (nous verrons précisément deux de ces verbes au chapitre suivant): `GET, POST, PUT, DELETE`;
- L'en-tête de la requête : qui permettent de préciser ce qu'attend le serveur (réponse) et ce qu'envoie la requête.
- Le corps de la requête : dans le cas d'un ``GET`` ou d'un ``DELETE``, le corps de la requête est envoyé en réponse, il contient l'information renvoyée par le serveur, sous la forme d'un JSON. Le corps (body) si il est envoyé avec la requête dans le cadre d'un ``POST`` ou d'un ``PUT`` peut être rédigé sous forme d'un ``objet``, de ``chaînes de caractères``, ou d'un ``JSON``, il contient les données à envoyer au serveur.

### Ligne du temps d'une requête:

- Prenons l'exemple d'une requête qui va récupérer des données d'un serveur :

On envoie la requête avec l'URL du serveur à contacter et le verbe ``GET``.
Le serveur répond avec un status 200 si la requête est valide, 400 si elle encourt une erreur.

Dans le cadre d'une erreur 400, il peut s'agir d'une erreur du à la configuration des ``headers`` :

Le serveur peut attendre une autorisation spécifique définie par le serveur qui doit être envoyée dans les ``headers`` de la requête pour donner l'accès aux informations : token d'identification, CORS.

Ensuite le corps de la réponse est envoyé : si il s'agit d'un status 200 vous obtiendrez les informations désirées, sinon le message correspondant à l'erreur rencontrée (par exemple : votre domaine n'a pas les accès requis par le serveur).

Dans le cadre d'une requête ``POST`` qui envoie de nouvelles données vers un serveur :

On envoie la requête avec l'URL du serveur, la méthode ``POST``, les headers précisant l'origine du domaine, le type de données envoyées, et le corps de la requête, souvent sous format ``JSON``.
La réponse renvoyée est un message accompagnant le statut de la requête: 200, 400, 500. Configuré par le serveur.

### Les Headers

Ou "en-tête" HTTP : les ``headers`` précisent le type de données attendues/envoyées, le domaine d'origine, les tokens d'authentification, les cookies, les informations sur le corps du message, les proxies, une éventuelle redirection, le contexte de la requête, le contexte de la réponse, une éventuelle pagination, des gardes de sécurité, des WebSockets, le codage de transfert, les différents événements envoyés par le serveur, la date, etc...

Les headers sont **optionnels**. Ils sont configurés par le back-end et doivent être connus du développeur utilisant l'API afin de renvoyer les configurations attendues.

Nous aurons besoin de définir le type de données envoyées par la requête à l'aide de la clé/valeur content-type :

```js
let myHeaders = new Headers({"Content-Type": "application/json"})
```

Tout d'abord je défini une nouvelle variable ``let myHeaders`` destinée à contenir mes headers. Comme vous le voyez, ils sont rédigés sous format JSON avec un objet contenant une paire clé/valeur dont la clé est toujours une chaîne de caractères.

On attribue ensuite cette variable à l'objet ``Headers`` grâce au mot-clé ``new Headers``. Cette définition permet à la variable d'acquérir toutes les méthodes et les propriétés de l'objet global ``Headers``.

Ensuite, à l'intérieur de mon nouvel objet, je défini la paire de clé/valeur à attribuer. Dans ce cadre-ci nous allons définir le type de données à envoyer par notre requête sous format ``json``. Il est indispensable de le configurer, sinon les données envoyées seront traduites sous la forme d'un objet simple et le serveur les interprétera comme un corps vide et renverra une erreur.

### Les verbes

Ils définissent la méthode de la requête. Ce qu'elle "fait" ou "demande".

- **GET:** demande une représentation de la ressource spécifiée, en d'autres termes, il demande au serveur via l'URL donnée, de renvoyer les données spécifiques à cette URL (https://quotes-light-api.herokuapp.com/api/comments/) pointe vers la route "comments" pour récupérer la table commentaire de la base de données.
- **POST:** Envoie un corps de données dont les paires clés/valeurs sont définies par l'API. Ces paires correspondent aux paires présentes dans la base de données, il peut arriver que certaines soient obligatoires à mentionner avec une valeur valide afin de pouvoir performer la requête.
- **PUT:** Met à jour la totalité d'une entité que l'on pointe à l'aide de son ID unique. Toutes les paires de clés/valeurs sont remplacées par le body renvoyé par l'utilisateur.
- **PATCH:** Met à jour uniquement la paire de clé valeur demandée.
- **DELETE:** Demande la suppression d'une entité dans la base de donnée à l'aide de son ID unique.

### Le corps de la requête

Le corps de la requête, ce sont les valeurs récupérées de votre formulaire, entrées par l'utilisateur de votre application. Ces valeurs sont destinées à être enregistrées dans la base de données ou comme données pour la réalisation de méthodes définies par le serveur.

Petit exemple :

Lorsque vous vous authentifiez sur FaceBook, vous ne modifiez pas la base de données, vous renvoyés des informations de connexion que le serveur compare avec votre profil utilisateur, si elles correspondent le serveur vous donne accès à votre profil, sinon il vous indique que vous avez fait une erreur.

Pour envoyer le corps de la requête, vous devez savoir à quoi correspond le schéma de clé-valeur attendu par le serveur, par exemple pour une authentification le serveur pourrait attendre une clé user_name et une clé user_password. Il s'agit d'une information définie que vous ne pouvez pas deviner :

Pour ce faire, il faut se référer à la ``documentation`` de votre ``API`` (application programming interface), ou directement au développeur ``Back-End`` ayant programmé le serveur. Je vous indiquerai donc ce que le serveur attend dans les consignes de votre exercice.

Le corps de la requête est le plus souvent attendu sous format ``JSON``. Pour cette semaine nous allons générer un corps en créant un objet sur base de la récupération de la valeur des ``input`` de votre formulaire et de la méthode ``JSON.stringify()``.

## Construire une requête POST avec fetch()

D'abord nous définissons les ``headers`` nécessaires à notre requête.
Ensuite nous avons besoin de récupérer les valeurs des ``inputs`` du formulaire rempli par l'utilisateur. Pour ce faire nous avons besoin d'un objet ``body`` :

Il va directement récupérer les valeurs introduites pour un formulaire donné (récupérées à l'aide de son ID). Ces données seront ensuite utilisées pour créer le corps de votre requête, mais elles doivent d'abord être transformée sous format ``JSON``, nous aurons donc besoin de la méthode ``JSON.stringify()``.

```js
let myHeaders = new Headers({"Content-Type": "application/json"})
let form = document.getElementById("myForm");
const btnSubmit = document.getElementById("submitBtn")

document.getElementById("submitBtn").addEventListener("click", () => {
  let formAuthor = document.getElementById("author").value;
  let formComment = document.getElementById("comment").value;
  let datas = {
    "author": formAuthor,
    "comment": formComment
  };
  fetch("l'url-de-mon-api", {
    method: "POST",
      headers: myHeaders,
      body: JSON.stringify(datas)
  })
})
```
Observons ce bout de code :

1. A l'événement **click** sur un bouton dont l'id est ``submitBtn`` (le bouton destiné à envoyer le formulaire vers le serveur). On définit deux nouvelles variables ``formAuthor`` et ``formComment`` qui vont récupérer les valeurs des **inputs** ``author`` et ``comment``.
2. On crée un nouvel objet ``datas`` qui va récupérer les pairs de clés/valeurs pointées par les variables ``formAuthor`` et ``formComment``.
3. Ensuite on crée une méthode ``fetch()`` qui prend comme argument/paramètre **l'url** de mon ``API``, et comme second argument ***un*** objet dont les clés sont ``method``, ``headers`` et ``body``.
4. La valeur de ``method`` se rapporte au verbe **HTTP** dont vous avez besoin pour votre requête, dans ce cas-ci il s'agit du verbe ``POST``.
5. La clé ``headers`` elle reçoit comme valeur la variable créée plus haut nommée ``myHeaders``.
6. Pour finir la clé ``body`` est attribuée à une **méthode**, ``JSON.stringify`` qui reçoit en argument la variable ``datas``, elle va transformer les paires de clés/valeurs de votre **formulaire** en format ``JSON``, qui est le format attendu par le serveur.

## Manipuler le DOM

> Créer de nouveaux éléments HTML de façon dynamique et y ajouter le contenu d'une requête HTTP.

La méthode ``fetch()`` nous renvoie souvent un tableau d'objets, sous format ``JSON``. Je vais vous demander de générer des éléments **HTML** pour chaque élément du tableau renvoyé par **l'API**.

Pour ce faire nous aurons besoin :

1. De récupérer le tableau d'objets (via la méthode ``fetch()``).
2. Un fois le tableau récupéré, utiliser la boucle ``forEach()`` pour obtenir chaque objet du tableau.
3. Grâce à cette boucle, pour chaque élément du tableau, je vais générer une **balise HTML** pour l'``auteur``, et une pour le ``commentaire``, pour ce faire nous aurons besoin de :
   - La méthode ``createElement()`` qui va créer notre élément **HTML**.
   - La méthode ``createTextNode()`` qui va remplir notre balise HTML avec les valeurs de l'élément sur lequel nous sommes en train de boucler.
   - La méthode ``appendChild()`` ou ``append()`` qui nous permettent de faire d'un élément HTML l'enfant d'un deuxième élément.
   - La méthode ``insertBefore()`` qui va indiquer l'endroit où insérer le contenu dans notre ``index.html``.



```js
fetch("l-url-de-mon-api", {method: "GET"})
.then(response => {
  return response.json();
})
.then(response => {
  let datas = response;
  datas.forEach(data => {
    let newHtmlElement = document.createElement("HTML TAG");
    let newContent = document.createTextNode(data.author);
    // let newContent = newHtmlElement.createTextNode(data.author); A tester.
    newHtmlElement.appendChild(newContent);
    let currentElement = document.getElementById("#ID");
    document.body.insertBefore(newHtmlElement, currentElement.nextElementSibling);
  })
})
```
Analysons ce bout de code :

1. La méthode ``fetch`` reçoit deux paramètres, ``l'url`` et l'objet contenant une clé ``method`` dont la valeur est la méthode à appliquer, dans ce cas précis je veux aller chercher un tableau d'objet dans mon **API**, donc j'utilise le verbe HTTP ``GET``.
2. Je transforme ma réponse en format ``.json()`` qui le rend lisible pour nous.
3. Ensuite, je stocke la réponse dans une nouvelle variable ``datas``.
4. Comme il s'agit d'un tableau d'objet je peux utiliser la méthode ``forEach()`` pour utiliser *chaque* élément comme générateur de contenu **HTML**.
5. Pour chaque élément je crée un nouvel élément **HTML** à l'aide de la méthode ``createElement()`` qui n'attend qu'un paramètre : le nom de l'élément à créer.
6. Ensuite pour l'élément en cours je vais créer du texte contenant la valeur de l'élément courant avec la méthode ``createTextNode()`` qui attend une valeur en paramètre, dans ce cas je pointe sur mon objet ``data`` et je récupère la valeur de la clé ``author``.
7. Ensuite j'utilise la méthode ``appendChild()`` pour greffer mon nouveau contenu texte à mon nouvel élément ``HTML``, pour ce faire je pointe sur ma variable ``newHtmlElement``, je lui attribue la méthode ``appendChild()`` qui va greffer un élément enfant à l'élément parent, l'élément enfant à greffer est dans ce cas-ci la variable ``newContent`` contenant la valeur de l'auteur.
8. Pour finir je crée une variable récupérant l'élément avant lequel je dois insérer mon contenu. Je pointe vers le body de mon document, je lui attribue la méthode ``insertBefore()`` qui reçoit comme paramètre la variable ``newHtmlElement`` et la variable point de repère `currentElement`, ``nextElementSibling`` spécifie l'élément enfant du parent.


## Petit exercice

Vous allez définir une méthode ``fetch()`` pour le verbe ``GET`` et une méthode ``fetch()`` pour le verbe ``POST``. Vous allez donc créer votre premier formulaire **HTML**, récupérer les valeurs de ce formulaire, les attribuer au corps de votre requête, et pour finir envoyer le corps de votre requête dans la base de données à l'aide de la méthode `POST` et des ``headers`` requis.

> Cours original : Julie Vanderbyse
> 
> Modifications : Lucas Ielli




