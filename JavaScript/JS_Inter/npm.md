<!-- omit in toc -->
# NPM
<!-- omit in toc -->
## Table des matières
- [Introduction](#introduction)
- [Command Line Interface](#command-line-interface)
- [Installation de NPM](#installation-de-npm)
- [Le site **npm**](#le-site-npm)
- [Utilisation](#utilisation)
- [Le versionning](#le-versionning)
- [Le fichier JSON](#le-fichier-json)
  - [Introduction](#introduction-1)
  - [En résumé](#en-résumé)


## Introduction

**NPM** est l'acronyme de "Node Package Manager". Il s'agit du plus grand registre de logiciels au monde ! Les développeurs du monde entier partagent des logiciels souvent en open source. **NPM** est totalement gratuit et inclut un **CLI (Command Line Interface**, par exemple `C:\>npm install <package>`) qui peut être utilisé pour télécharger et installer de nombreux logiciels. Son installation nécessite **Node.JS** sur votre machine, d'où le nom "Node Package Manager", ce qui signifie gestionnaire de paquets/dépendances Node. Donc, oui, nous devrons encore écrire des commandes dans notre terminal ! PS : il existe d'autres **CLIs** comme "yarn" ou "bash".

## Command Line Interface

Un CLI est un moyen de donner des ordres à un ordinateur en tapant des mots dans une fenêtre de texte. Au lieu de cliquer sur des icônes comme dans une interface graphique, tu tapes des commandes pour effectuer des actions.

Voici quelques points clés :

- **Texte vs Graphique** : Au lieu de cliquer avec la souris, tu utilises le clavier pour entrer des commandes en texte.

- **Efficace** : C'est souvent plus rapide pour faire des choses comme copier des fichiers, exécuter des programmes, ou gérer un serveur.

- **Scripting** : Tu peux créer des séquences de commandes pour automatiser des tâches, ce qui est très pratique.

- **Exemples** : Les CLIs sont utilisés dans les terminaux Unix/Linux, le PowerShell de Windows, et d'autres programmes.

En résumé, un CLI est comme une conversation en texte avec un ordinateur pour lui dire quoi faire. C'est rapide, puissant et permet de faire des choses avancées en tapant des commandes.

## Installation de NPM

1. Tout d'abord, rendez-vous sur le site de [**NodeJS**](https://nodejs.org/fr/) et téléchargez la version **LTS**. La dernière version disponible fonctionne, mais pour notre utilisation, il est plus que recommandé d'utiliser une version stable.
2. Une fois votre package **NodeJS** téléchargé, lancez son installation. Cette dernière installera **NodeJS** mais aussi **NPM**.
3. Choisissez où vous souhaitez l'installer.
4. Cliquez "**Next**" 3 fois.
5. Cliquez sur "**Install**", votre machine fera le reste.
6. Dernier clic sur "**Finish**".
7. Redémarrez votre ordinateur, ce n'est pas nécessaire, mais c'est préférable.
8. Dans **VSCode**, vous avez la possibilité d'utiliser votre terminal, ouvrez-le via l'onglet "**Terminal" > "Nouveau Terminal**" ou `Ctrl + ù` ou `Ctrl + Shift + ù`.
9. Une fois dans votre terminal, nous allons vérifier votre installation avec ces deux commandes : "**npm -v**" et "**node -v**". Ces commandes permettent de connaître la version qui a été installée.
10. Vous n'avez plus qu'à installer les paquets dont vous avez besoin pour vos projets !

## Le site [**npm**](https://www.npmjs.com/)

Quand vous serez développeur, s'inscrire sur le site sera indispensable pour partager les packages que vous avez vous même créé ou que votre entreprise vous demandera d'installer. Nous allons parcourir le site ensemble pour vous montrer comment rechercher un package et l'installer sur votre machine.

[:arrow_up: Revenir au sommaire](#table-des-matières)

## Utilisation

Vous avez créé votre répository et vous avez déjà commit votre structure de fichiers. Vous souhaitez maintenant utiliser des packages npm, voici comment faire :

1. Rendez-vous dans votre terminal, à la racine de votre fichier `C:\Users\VotreNom\Dossier\Dossier\VotreProjet`.
2. Nous allons initialiser npm localement dans votre projet. Pour ce faire, entrez la commande `npm init`.
3. Cette commande lancera un script et vous demandera plusieurs informations pour ensuite écrire les données dans votre fichier "package.json".
   1. Il vous demandera le nom du package, pour plus de facilité ce sera le nom de votre repositery. Faites `Enter`
   2. La version (j'en reparlerais plus tard), évidemment il est logique de commencer par la version 1.0.0. Faites `Enter`
   3. Une description pour le projet, à vrai dire ce n'est pas le plus utile. Faites `Enter`.
   4. Le point d'entrée, si vous n'avez pas créé de fichier script il vous proposera index.js d'ou l'importance de créer votre srtucture de projet avant d'initialisé npm. Faites `Enter`.
   5. Test command, dans le cadre de l'initiation Sirius nous n'utiliserons pas cette fonctionnalité. Faites `Enter`.
   6. Le repository Git, si vous avez bien créé votre repository il vous proposera le lien de ce dernier. Si ce n'est pas le cas, aucune valeur par défaut ne sera ajoutée, d'où l'importance une fois de plus de créer un repository dès le départ du projet. Faites `Enter`.
   7. Keywords, dans le cadre de l'initiation Sirius nous n'utiliserons pas cette fonctionnalité. Faites `Enter`.
   8. Author, purement facultatif, vous avez la possibilité d'ajouter votre nom et prénom en tant qu'auteur du projet. Faites `Enter`.
   9. License, dans le cadre de l'initiation Sirius nous n'utiliserons pas cette fonctionnalité. Faites `Enter`.
   10. La fin de ce script vous demande si les informations sont bien correctes si c'est bien le cas, tapez `yes` ou `y` suivi de `Enter`.
4. Nous pouvons enfin installer des packages venant de la plateforme. Le premier sera [**SASS**](https://www.npmjs.com/package/sass), c'est un compilateur CSS. La commande `npm i sass` correspond à `npm install sass`, les deux fonctionnent 😁 L'importance n'est pas portée sur le package que nous installons mais bien sur NPM.
5. Dans vos dépendances (**dependencies**) vient de s'ajouter "**sass**: **version**" et dans vos fichiers, un nouveau dossier est apparu, "**node_modules**". Il est ***IMPERATIF*** qu'il soit dans votre fichier ".gitignore".

[:arrow_up: Revenir au sommaire](#table-des-matières)

## Le versionning

Le versionning dans la construction d'un projet est crucial pour plusieurs raisons. Il permet de suivre et de gérer l'évolution du projet au fil du temps, ce qui est essentiel pour la collaboration, la maintenance et la garantie de la stabilité.

1. **Historique et Suivi** : En attribuant des numéros de version à votre projet, vous créez un historique de son évolution. Cela vous permet de suivre les modifications apportées au fil du temps, de savoir qui a fait quoi et quand. Cela facilite la rétro-ingénierie en cas de problèmes ou de régressions.

2. **Collaboration** : Lorsque plusieurs personnes travaillent sur un projet, le versionning devient essentiel. Chacun peut travailler sur une version spécifique du projet sans perturber le travail des autres. Les branches et les tags de version aident à organiser le travail.

3. **Maintenance et Réparations** : En cas de bogues ou de problèmes de sécurité, le versionning permet de revenir à une version précédente du projet pour identifier quand le problème est survenu. Cela simplifie la correction des erreurs.

4. **Garantie de la Stabilité** : Les versions stables du projet sont marquées par des numéros de version spécifiques. Cela permet aux utilisateurs de savoir quelles versions sont fiables pour une utilisation en production, et quelles versions sont en cours de développement.

5. **Documentation** : Les numéros de version servent également de points de repère dans la documentation du projet. Les utilisateurs peuvent se référer à la documentation correspondant à leur version spécifique.

En résumé, le versionning d'un projet est essentiel pour maintenir un historique clair, faciliter la collaboration, gérer les bogues et garantir la stabilité. Il offre une structure et une organisation vitales pour la construction d'un projet à long terme.

## Le fichier JSON

### Introduction

Le format **JSON**, ou **JavaScript Object Notation**, permet de représenter des données de base sous la forme d'un objet JavaScript au sein d'un fichier pouvant être lu et interprété par un large éventail de langages en dehors de JavaScript. Vous serez souvent amenés à travailler avec ce type de fichier, il est donc important de savoir comment les manipuler.

Il permet d'envoyer et de recevoir des données de la part d'un serveur.

Les données du **JSON** se présentent sous forme de chaînes de caractères. Faciles à écrire pour nous, faciles à interpréter pour l'ordinateur.

Son arborescence proche de celle d'un objet le rend facile à lire/parcourir pour l'œil humain, mais également pour la machine. Cette facilité le rend évidemment très populaire.

Pour ceux qui n'auraient pas encore le fichier nouvellement ouvert, voici un exemple :

```json
{
    "text": "Les difficultés augmentent plus on se rapproche du but.",
    "auteur": "Johann Wolfgang von Goethe"
}
```

L'objet se compose d'une paire "clé" : "valeur". La clé permet de pointer vers la valeur et de l'afficher.
Tout comme un objet en JavaScript, pour afficher uniquement le texte à l'écran, je peux procéder de cette manière :

```js
console.log(data.text)
```

Contrairement aux objets JS, le **JSON** exige, pour être valide, que sa clé et sa valeur soient introduites toutes deux sous forme de chaînes de caractères.

En effet, comme cité plus haut, la clé et la valeur doivent être écrites sous forme de chaîne de caractères. Cependant, un objet **JSON** accepte également les types de données suivants :
- Booléen
- Chiffre
- Tableaux
- Autre objet
- Null

Qui plus est, pour être validé en tant que chaîne de caractères, le format **JSON** n'acceptera uniquement que l'utilisation des guillemets et pas d'apostrophe, comme ça peut être le cas pour une simple variable de type chaîne de caractères.
Une fois de plus, contrairement aux autres objets JavaScript, l'objet **JSON** ne peut pas contenir de méthodes, il ne peut que contenir du texte et ne peut rendre que du texte également.
Comme dans un objet JS, il est possible d'imbriquer des valeurs sous forme de tableaux ou de tableaux d'objets.

Dans l'exemple ci-dessous, la clé "**powers**" possède un tableau de valeurs. Comment pointeriez-vous vers le pouvoir "**million tonne punch**" de "**Madame Uppercut**" ?

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

if (data.test.name === "Madame Uppercut") console.log(data.test.powers[1]); -->

[:arrow_up: Revenir au sommaire](#table-des-matières)

### En résumé

Un fichier **JSON** peut être sous forme d'un tableau d'objets, dont les clés sont toujours des chaînes de caractères, et les valeurs peuvent être un autre objet, un tableau, une chaîne de caractères, null ou un chiffre.

Les fichiers **JSON** servent à stocker les données de votre application, permettent d'en ajouter, supprimer et modifier. Il est très populaire et reconnu par la plupart des langages et des bases de données. Il se comporte presque comme un objet en JavaScript, ce qui rend les données faciles à atteindre.

![](../Resources/Images/npm_original_wordmark_logo_icon_146402.png)

[:arrow_up: Revenir au sommaire](#table-des-matières)

[:arrow_right: Suite du cours : "Fetch"](./2_fetch.md)

[:rewind: Retour au sommaire du cours](../README.md#au-programme)

> Créé par [Lucas Ielli](https://github.com/LucasIelli)