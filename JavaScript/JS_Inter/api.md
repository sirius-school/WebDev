<!-- omit in toc -->
# La méthode fetch()
<!-- omit in toc -->
## Tables des matières
- [Introduction](#introduction)
- [Fonctions Asynchrones](#fonctions-asynchrones)
- [API (Application Programming Interface)](#api-application-programming-interface)
  - [Qu'est-ce qu'une API ?](#quest-ce-quune-api-)
  - [Fonctions Principales d'une API](#fonctions-principales-dune-api)
  - [Fonctionnement d'une API](#fonctionnement-dune-api)
  - [Exemples d'API](#exemples-dapi)
- [Qu'est-ce que fetch ?](#quest-ce-que-fetch-)
- [Construire une requête](#construire-une-requête)
  - [Les verbes](#les-verbes)
  - [Les en-tête](#les-en-tête)
  - [Le corps de la requête](#le-corps-de-la-requête)
  - [Chronologie d'une Requête](#chronologie-dune-requête)
- [Construire une Requête POST avec fetch()](#construire-une-requête-post-avec-fetch)
- [Manipuler le DOM](#manipuler-le-dom)
- [La structure ``try...catch``](#la-structure-trycatch)
  
## Introduction

La méthode fetch() permet de contacter un serveur afin d'y récupérer/modifier/ajouter/supprimer des données.

Vous serez régulièrement amené à utiliser ce type de méthode (il existe différentes librairies qui possèdent leur propres méthodes), il est donc important de bien comprendre son fonctionnement.

Lorsque le navigateur lit et interprète votre code, il le fait de ligne en ligne mais pas que. Il peut passer d'une opération à la suivante avant la fin de l'exécution de la première. Il s'agit de programmation `asynchrone`, c'est ce qui arrive dans le cas d'une requête envoyée vers un serveur, le navigateur n'attend pas la réponse à cette requête avant d'exécuter la suite de votre code.

Si vous aviez prévu d'utiliser les données renvoyées par le serveur il faut donc spécifier au navigateur qu'il attend qu'un bout de code (la requête) soit exécuté avant d'utiliser ces données. Si vous ne l'indiquez pas, il est probable que la variable prévue pour stocker les nouvelles données reste vide aux yeux de votre navigateur.

## Fonctions Asynchrones

Arrivés à ce stade de la formation vous n'êtes pas sans savoir que le language JavaScript est généralement synchrone, ce qui signifie qu'il lit le code ligne par ligne. Toutefois, les fonctions asynchrones vous permettent de sortir de cette séquence pour que le navigateur attende la résolution d'une fonction avant de continuer.

- `async`: En préfixant une fonction avec le mot-clé `async`, vous la déclarez comme asynchrone. Elle renvoie une valeur appelée "Promise", qui sera soit résolue avec la valeur renvoyée par la fonction asynchrone, soit rejetée en cas d'erreur.

- `await`: Ce mot-clé est essentiel dans le cas d'une **fonction asynchrone**. Il attend la résolution de la "Promise" renvoyée par votre fonction asynchrone.

- `Promise`: Une "Promise" est une valeur qui représente une opération asynchrone. Elle peut être en attente, résolue avec une valeur, ou rejetée avec une erreur.

## API (Application Programming Interface)

### Qu'est-ce qu'une API ?

Une API est un ensemble de règles qui permet à différentes applications de communiquer entre elles. Les APIs sont essentielles pour l'intégration, l'échange de données et l'automatisation de tâches entre applications.

### Fonctions Principales d'une API

1. **Accès aux Fonctionnalités** : Les APIs permettent à une application d'utiliser les fonctionnalités d'une autre.

2. **Échange de Données** : Elles facilitent l'échange de données entre applications.

3. **Interactions avec des Services Externes** : Les APIs connectent des applications à des services externes.

4. **Automatisation de Tâches** : Elles automatisent des tâches répétitives entre applications.

### Fonctionnement d'une API

1. **Demande/Requête (Request)** : L'application cliente envoie une demande à l'API du serveur.

2. **Traitement de la Demande** : Le serveur API traite la demande.

3. **Réponse (Response)** : Le serveur renvoie une réponse à l'application cliente.

### Exemples d'API

- **API de Réseaux Sociaux** : Permet l'intégration de fonctionnalités de partage et de connexion via les médias sociaux.

- **API de Cartographie** : Intègre des cartes interactives dans des applications.

- **API de Paiement** : Effectue des transactions financières en ligne de manière sécurisée.

- **API de Messagerie** : Permet l'envoi et la réception de messages via des applications.

Les APIs sont essentielles pour créer des applications interconnectées et enrichir les fonctionnalités existantes.

## Qu'est-ce que fetch ?

Heureusement, la méthode `fetch()` est conçue pour résoudre le problème mentionné dans la partie sur les fonctions asynchrones. Voici un exemple d'utilisation :

```js
fetch("http://l-url-de-la-requete.com/")
  .then(response => {
    console.log(response => response.json();
  })
  .then(response => {
    let data = response; // Facultatif
    document.getElementById("text").textContent = data.text;
  });
```

Dans cet exemple, nous utilisons la méthode `fetch` pour contacter un serveur en spécifiant son URL.

Ensuite, le mot-clé `.then` entre en jeu (`.then` signifie "ensuite"). Grâce à lui, le navigateur attendra la réception de la réponse avant d'exécuter le code suivant.

Lorsque la réponse arrive, nous l'affichons d'abord dans la console, puis nous la traitons pour la convertir en format `.json` en utilisant la méthode `.json()`.

Un deuxième `.then` est utilisé pour créer une variable `data` (la création de la variable n'est pas obligatoire) à laquelle nous attribuons la valeur de la réponse. Enfin, nous utilisons une clé/valeur de la réponse de l'API pour modifier le contenu HTML.

Sans l'utilisation de `.then`, le navigateur n'attendrait pas la réponse et tenterait d'exécuter les morceaux de code, ce qui provoquerait une erreur.

## Construire une requête

Pour construire une requête valide pour le protocole HTTP vous aurez besoin de plusieurs éléments :

- **Le verbe de la requête** : `GET, POST, PUT, DELETE, PATCH`;
- **L'en-tête de la requête** : qui permettent de préciser ce qu'attend le serveur (réponse) et ce qu'envoie la requête.
- **Le corps de la requête** : dans le cas d'un ``GET`` ou d'un ``DELETE``, le corps de la requête est envoyé en réponse, il contient l'information renvoyée par le serveur, sous la forme d'un JSON. Le corps (body) si il est envoyé avec la requête dans le cadre d'un ``POST`` ou d'un ``PUT`` peut être rédigé sous forme d'un ``objet``, de ``chaînes de caractères``, ou d'un ``JSON``, il contient les données à envoyer au serveur.

### Les verbes

Les cinq verbes de requête cités plus haut sont souvent appelés "méthodes HTTP" ou "méthodes CRUD" qui sont couramment utilisés pour interagir avec les ressources d'une API.

1. **GET** : Cette méthode est utilisée pour **récupérer** des données depuis l'API. Elle est généralement utilisée pour lire des informations sans les modifier. Par exemple, lorsqu'un navigateur demande une page web, il effectue une requête GET pour obtenir le contenu de cette page.

2. **POST** : La méthode POST est utilisée pour créer de **nouvelles données** sur le serveur de l'API. Cela peut inclure la soumission de formulaires, l'ajout de nouveaux éléments à une base de données, ou la création de ressources.

3. **PUT** : La méthode PUT est utilisée pour mettre à jour des données existantes sur le serveur. Lorsque vous effectuez une requête PUT, vous envoyez des données qui remplacent **intégralement** les données existantes. Cela signifie que vous devez généralement fournir toutes les informations, même celles qui ne changent pas.

4. **DELETE** : Cette méthode est utilisée pour supprimer des données sur le serveur. Lorsqu'une requête DELETE est effectuée, la ressource ciblée est supprimée de manière **permanente**.

5. **PATCH** : La méthode PATCH est utilisée pour effectuer des mises à jour partielles sur une ressource. Contrairement à PUT, elle **ne remplace pas** complètement les données, mais seulement les parties spécifiées dans la requête.

Ces méthodes HTTP sont les principaux outils que les développeurs utilisent pour interagir avec des APIs. Chacune a un objectif spécifique dans la manipulation des données via l'API.

### Les en-tête

Sont des éléments HTTP : les `headers` précisent le type de données attendues/envoyées, le domaine d'origine, les tokens d'authentification, les cookies, les informations sur le corps du message, les proxies, une éventuelle redirection, le contexte de la requête, le contexte de la réponse, une éventuelle pagination, des gardes de sécurité, des WebSockets, le codage de transfert, les différents événements envoyés par le serveur, la date, etc...

Les headers sont **optionnels**. Ils sont configurés par le back-end et doivent être connus du développeur utilisant l'API afin de renvoyer les configurations attendues.

Nous aurons besoin de définir le type de données envoyées par la requête à l'aide de la clé/valeur content-type :

```js
let myHeaders = new Headers({"Content-Type": "application/json"})
```

Tout d'abord je défini une nouvelle variable `let myHeaders` destinée à contenir mes headers. Comme vous le voyez, ils sont rédigés sous format JSON avec un objet contenant une paire clé/valeur dont la clé est toujours une chaîne de caractères.

On attribue ensuite cette variable à l'objet `Headers` grâce au mot-clé `new Headers`. Cette définition permet à la variable d'acquérir toutes les méthodes et les propriétés de l'objet/constructeur global `Headers`.

Ensuite, à l'intérieur de mon nouvel objet, je défini la paire de clé/valeur à attribuer. Dans ce cadre-ci nous allons définir le type de données à envoyer par notre requête sous format `json`. Il est indispensable de le configurer, sinon les données envoyées seront traduites sous la forme d'un objet simple et le serveur les interprétera comme un corps vide et renverra une erreur.

### Le corps de la requête

Le corps de la requête, ce sont les valeurs récupérées de votre formulaire, entrées par l'utilisateur de votre application. Ces valeurs sont destinées à être enregistrées dans la base de données ou comme données pour la réalisation de méthodes définies par le serveur.

Petit exemple :

Lorsque vous vous authentifiez sur Facebook, vous ne modifiez pas la base de données, vous renvoyés des informations de connexion que le serveur compare avec votre profil utilisateur, si elles correspondent le serveur vous donne accès à votre profil, sinon il vous indique que vous avez fait une erreur.

Pour envoyer le corps de la requête, vous devez savoir à quoi correspond le schéma de clé-valeur attendu par le serveur, par exemple pour une authentification le serveur pourrait attendre une clé ``user_name`` et une clé ``user_password``. Il s'agit d'une information définie que vous ne pouvez pas deviner. Il faudra donc se référer à la ``documentation`` de votre ``API``, ou directement au développeur ``Back-End`` ayant programmé le serveur. Le corps de la requête est le plus souvent attendu sous format ``JSON``.

### Chronologie d'une Requête

Prenons l'exemple d'une requête visant à récupérer des données depuis un serveur :

1. Nous envoyons la requête avec l'URL du serveur à contacter en utilisant la méthode "GET".
2. Le serveur répondra avec un code d'état (status) 200 si la requête est valide, ou 400 en cas d'erreur.

En cas d'une erreur 400, cela peut être lié à la configuration des en-têtes (headers) :

Le serveur peut exiger une autorisation spécifique, définie par le serveur, qui doit être incluse dans les en-têtes de la requête pour accéder aux informations, telles qu'un token d'authentification ou les règles CORS (Cross-Origin Resource Sharing).

3. Ensuite, le corps de la réponse est envoyé. Si le code d'état est 200, vous recevrez les informations souhaitées. Sinon, vous obtiendrez un message d'erreur correspondant à l'incident rencontré (par exemple : votre domaine ne dispose pas des autorisations requises par le serveur).

Dans le cas d'une requête "POST" qui envoie de nouvelles données au serveur :

1. Nous envoyons la requête avec l'URL du serveur en utilisant la méthode "POST", des en-têtes spécifiant l'origine du domaine, le type de données envoyées, et le corps de la requête, souvent au format JSON.
2. La réponse renvoyée sera accompagnée d'un message et d'un code d'état, tel que 200, 400, 500, configuré par le serveur.

## Construire une Requête POST avec fetch()

Pour commencer, définissons d'abord les en-têtes ("headers") nécessaires à notre requête.

Ensuite, nous devons récupérer les valeurs des champs de saisie ("inputs") du formulaire rempli par l'utilisateur. Pour ce faire, nous aurons besoin d'un objet "body" qui récupérera directement les valeurs du formulaire, identifiées par leur ID. Cependant, avant de les utiliser pour construire le corps de la requête, ces données doivent être converties au format JSON en utilisant la méthode "JSON.stringify()", ce qui signifie qu'elles seront transformées en une chaîne de caractères au format JSON, prête à être envoyée au serveur.

```js
const myHeaders = new Headers({"Content-Type": "application/json"});
const form = document.getElementById("myForm");

form.addEventListener("submit", () => {
  const formAuthor = document.getElementById("author").value;
  const formComment = document.getElementById("comment").value;
  let data = {
    "author": formAuthor,
    "comment": formComment
  };
  fetch("l'url-de-mon-api", {
    method: "POST",
    headers: myHeaders,
    body: JSON.stringify(data)
  });
});
```

Examinons ce code :

1. Lorsqu'un événement "submit" se produit sur un formulaire, nous récupérons les valeurs des champs de saisie "author" et "comment".

2. Un nouvel objet "data" est créé pour stocker les paires de clés/valeurs correspondant aux variables ``formAuthor`` et ``formComment``.

3. Ensuite, nous utilisons la méthode ``fetch()`` en lui fournissant comme premier argument l'URL de notre API, et comme deuxième argument un objet contenant les propriétés ``method``, ``headers``, et ``body``.

4. La propriété ``method`` est utilisée pour spécifier la méthode HTTP nécessaire pour notre requête, dans ce cas, il s'agit de la méthode "POST".

5. La propriété ``headers`` reçoit comme valeur la variable "myHeaders" que nous avons créée précédemment.

6. Enfin, la propriété ``body`` est attribuée à la méthode ``JSON.stringify()`` avec la variable ``data`` comme argument. Cette méthode transforme les paires de clés/valeurs de notre formulaire en un format JSON, qui est le format attendu par le serveur.

Cela permet d'envoyer des données au serveur de manière appropriée en utilisant la méthode POST.

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

## La structure ``try...catch``

En JavaScript, `try...catch` est une structure qui permet de gérer les erreurs lors de l'exécution du code. Voici comment cela fonctionne :

- Le code potentiellement problématique est placé dans un bloc `try`.
- Si une erreur survient dans ce bloc, le contrôle est transféré au bloc `catch`, où vous pouvez spécifier comment gérer l'erreur en utilisant l'objet `error`.
- Vous pouvez personnaliser le traitement de l'erreur en fonction de ses propriétés, comme `message`.

Exemple simple :

```javascript
try {
  let x = 10 / 0; // Division par zéro génère une erreur
} catch (error) {
  console.log("Une erreur s'est produite : " + error.message);
} finally {
  // Code à exécuter qu'il y ait une erreur ou non
}
```

De plus, vous pouvez gérer différents types d'erreurs en utilisant plusieurs blocs `catch` pour chaque type.

Enfin, vous pouvez utiliser un bloc `finally` pour exécuter du code quels que soient les résultats du bloc `try`. Cela est utile pour des opérations de nettoyage ou de fermeture.

En résumé, `try...catch` est essentiel pour gérer les erreurs et garantir que votre code JavaScript fonctionne de manière plus robuste, en évitant les arrêts inattendus.

Cette structure est fort utile lorsqu'on fait appel à une API que ce soit avec la méthode ``fetch()`` ou avec une librairie.

> Mostly edited by [Lucas Ielli](https://github.com/LucasIelli)




