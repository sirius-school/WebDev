<!-- omit in toc -->
# NPM
<!-- omit in toc -->
## Table des matières
- [Introduction](#introduction)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Le fichier JSON](#le-fichier-json)
  - [Introduction](#introduction-1)
  - [En résumé](#en-résumé)

## Introduction

NPM est l'acronyme de `Node Package Manager`, il est le plus grand registre de logiciels au monde ! Rien que ça ! Les dévelopeurs du monde entier partagent des logiciels souvent en `open source`. Il est totalement gratuit et inclut un `CLI` (Command Line Client, exemple `C:\>npm install <package>`) qui peut être utilisé pour télécharger et installer pas mal de logiciels. Son installation requiert Node.JS dans votre machine d'ou le nom `Node Package Manager` ce qui signifie gestionnaire de paquets/dépendances Node. Donc oui nous devrons encore écrire des commandes dans notre terminal ! PS : il existe d'autres CLI comme votre `terminal` (oui oui) ou `yarn` ou `bash`.

## Installation

1. Tout d'abord rendez-vous sur le site de [NodeJS](https://nodejs.org/fr/) et téléchargez la version `LTS`. La dernière version disponible est fonctionnelle mais pour notre utilisation il est plus que recommandé d'utiliser une version stable.
2. Une fois votre package NodeJS téléchargé, démarrez son installation.
3. Choisissez ou vous souhaitez l'installer.
4. Cliquez `Next` 3 fois.
5. Cliquez `Install`, votre machine fera le reste.
6. Dernier clique sur `Finish`
7. Redémarrez votre ordinateur, ce n'est pas une nécessité mais c'est préfèrable.
8. Dans VSCode vous avez la possibilité d'utiliser votre terminal, ouvrez-le via l'onglet `Terminal` > `Nouveau Terminal` ou `Ctrl + Shift + ù`.
9. Une fois dans votre terminal nous allons vérifier votre installation avec ces deux commandes `npm -v` et `node -v`, cette commande sert à connaitre la version qui a été installée.
10. Plus qu'à installer les paquets dont vous avez besoin pour vos projets !

La site [npm](https://www.npmjs.com/)

[:arrow_up: Revenir au top](#table-des-matières)

## Utilisation

Vous avez créer votre repositery et vous avez déjà commit votre structure de fichiers. Vous souhaitez maintenant utiliser des packages npm, voici comment faire :

1. Rendez-vous dans votre terminal, à la racine de votre fichier `C:\Users\VotreNom\Dossier\Dossier\VotreProjet`.
2. Nous allons `initialisez npm` localement dans votre projet pour ce faire entrer la commande `npm init`.
3. Cette commande lancera un script et vous demandera plusieurs choses pour ensuite écrire les données dans votre fichier `package.json`.
4. Nous pouvons enfin installer des packages venant de la plateforme, le premier sera [`SASS`](https://www.npmjs.com/package/sass) c'est un compileur CSS qui vous facilitera la tâche. La commande `npm i sass` correspond à `npm install sass` les deux fonctionnent 😁
5. Dans vos `dependencies` (dépendances) vient de s'ajouter `"sass": "version"` et dans vos fichiers un nouveau dossier est apparu `node_modules`, il est **impératif** qu'il soit dans votre `.gitignore`.

[:arrow_up: Revenir au top](#table-des-matières)

## Le fichier JSON

### Introduction

Le format JSON ou Javascript Object Notation, permet de représenter des données basiquement sous la forme d'un objet Javascript au sein d'un fichier pouvant être lu et interprété par un large éventail de langage en dehors du JavaScript. Vous serez souvent amenés à travailler avec ce type de fichier, il est donc important de savoir comment les manipuler.

Il permet d'envoyer et de recevoir des données de la part d'un serveur.

Les données du JSON se présentent sous un format chaîne de caractère. Facile à écrire pour nous, facile à interpréter pour l'ordinateur.

Son arborescence proche de celle d'un objet la rend facile à lire / parcourir pour l'œil humain, mais également pour la machine. Cette facilité le rend évidemment très populaire.

Pour ceux qui n'auraient pas encore le fichier nouvellement ouvert, voici un exemple :

```json
{
    "text": "Difficulties increase the nearer we get to the goal.",
    "author": "Johann Wolfgang von Goethe"
  }
```
``L'objet`` se constitue d'une paire `"clé"` : `"valeur"`. La clé permet de pointer vers la valeur et de l'afficher.
Tout comme un objet en JavaScript pour afficher uniquement le texte à l'écran je peux procéder de cette manière :

```js
console.log(data.text)
```
Contrairement aux objets JS, si vous l'avez remarqué, le **JSON** exige pour être valide d'avoir sa clé et sa valeur introduite toutes deux sous forme de chaîne de caractère.

En effet comme cité plus haut, la ``clé`` et la ``valeur`` doivent être écrites sous forme de chaîne de caractère, cependant un objet **JSON** accepte également les types de données suivants :
- Booléen
- Chiffre
- Tableaux
- Autre objet
- Null

Qui plus est, pour être validée en tant que chaîne de caractère, le format **JSON** n'acceptera uniquement que l'utilisation des guillemets et **pas d'apostrophe** comme ça peut être le cas pour une simple variable de type chaîne de caractère.
Une fois de plus contrairement aux autres objets JavaScript, l'objet JSON ne peut pas être attribué à des méthodes, il ne peut que contenir du texte et ne rendre que du texte également.
Comme dans un objet JS il est possible d'imbriquer des valeurs sous forme de tableaux ou de tableaux d'objets.

Dans l'exemple ci-dessous, la clé ``"powers"`` possède un tableau de valeurs. Comment pointeriez vous vers le pouvoir ``"million tonne puch"`` de ``Madame Uppercute``?
```json
[
  {
    "name": "Molecule Man",
    "age": 29,
    "secretIdentity": "Dan Jukes",
    "powers": [
      "Radiation resistance",
      "Turning tiny",
      "Radiation blast"
    ]
  },
  {
    "name": "Madame Uppercut",
    "age": 39,
    "secretIdentity": "Jane Wilson",
    "powers": [
      "Million tonne punch",
      "Damage resistance",
      "Superhuman reflexes"
    ]
  }
]
```
<!-- Answer : import data from "./package.json" assert { type: "json" };

if (data.test.named === "Madame Uppercut") console.log(data.test.powers[1]); -->

[:arrow_up: Revenir au top](#table-des-matières)

### En résumé

Un fichier JSON peut être sous forme d'un tableau d'objets, dont les clés sont toujours des chaînes de caractères, et les valeurs pouvant être un autre objet, un tableau, une chaîne de caractère, null, ou un chiffre.

Les fichiers JSON servent à stocker les données de votre application, permettent d'en ajouter, supprimer, modifier. Il est très populaire et reconnu par la plupart des languages / base de données. Il se comporte presque comme un objet en JavaScript, ce qui rend les données faciles à atteindre.

![](../Resources/Images/npm_original_wordmark_logo_icon_146402.png)

[:arrow_up: Revenir au top](#table-des-matières)

[:arrow_right: Suite du cours : *Fetch*](./2_fetch.md)

[:rewind: Retour au sommaire du cours](../README.md#au-programme)

> Created by [Lucas Ielli](https://github.com/LucasIelli)
