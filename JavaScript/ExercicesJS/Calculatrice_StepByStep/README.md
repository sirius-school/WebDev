<!-- omit in toc -->
# Calculatrice étape par étape
<!-- omit in toc -->
## Table des matières
- [Étape habituelle : Créez un repository](#étape-habituelle--créez-un-repository)
- [Étape 1 : Mise en place du fichier HTML](#étape-1--mise-en-place-du-fichier-html)
- [Étape 2 : Ajout des boutons de la calculatrice](#étape-2--ajout-des-boutons-de-la-calculatrice)
- [Étape 3 : Stylisation avec CSS](#étape-3--stylisation-avec-css)
- [Étape 4 : Ajout de l'interactivité avec JavaScript](#étape-4--ajout-de-linteractivité-avec-javascript)

## Étape habituelle : Créez un repository

## Étape 1 : Mise en place du fichier HTML
1. Créez un fichier HTML nommé `index.html`
2. À l'intérieur du fichier HTML, créez votre structure en utilisant Emmet `!`
3. Liez votre fichier `./script.js` et `./style.css`
4. Dans le `<body>`, créez un conteneur pour la calculatrice, par exemple, une `<div>` avec un ID comme `calculator`

## Étape 2 : Ajout des boutons de la calculatrice
1. À l'intérieur de la `<div>` avec l'ID `calculator`, créez plusieurs boutons
2. Chaque bouton représente un chiffre de `0 à 9`, un opérateur `+, -, ×, ÷` et des boutons spéciaux `•, =, C`(décimal, égal, effacer)
3. Pour chacun des boutons ajoutez un attribut `value` qui correspondra au texte affiché sur votre bouton. Exemples : `• sera .`, `= sera =`, `÷ sera /`. Petite précision, ce n'est pas la manière la plus pratique et efficace mais ce sera bien plus simple de "jouer" avec la value en JavaScript
4. Ajoutez un écran qui permettra d'afficher le résultat du calcul, vous pouvez lui spécifiez une ID `screen`

## Étape 3 : Stylisation avec CSS
1. Créez un fichier CSS nommé `style.css`, vérifiez que vous avez bien lié votre page de style avec votre HTML
2. Utilisez le CSS pour styliser le conteneur de la calculatrice
3. Stylez vos différents boutons, par exemple le bouton effacer en rouge et le bouton égal en bleu
4. Comme pour l'exercice de la Todo Liste, ne vous prenez pas trop la tête au niveau du CSS, le principale c'est que ce soit plus facile à utiliser durant le développement des fonctionnalités en JavaScript. N'oubliez pas qu'il n'est pas nécessaire de créer des classes étant donné que vous avez déjà des attributs HTML `value` qui normalement ont une valeur unique 😉

## Étape 4 : Ajout de l'interactivité avec JavaScript
1. Créez un fichier JavaScript nommé `script.js` et vérifiez si vous l'avez bien lié à votre HTML
2. Créez une variable qui reprendra **tout** les boutons de votre page et ce sous forme de `tableau`
3. Créez une variable qui contiendra votre écran sur lequel vous devez afficher le résultat
4. `Pour chaque` boutons de votre page, vous allez devoir utilisez une réaction événements de type `click` avec un paramètre `event`
5. Ouvrez une condition `switch...case`, cette condition est assez simple :
   1. La condition à regarder est l'attribut `value` de notre cible (target 😉) `event`
   2. Dans le cas où cette condition est égale à `=` vous voulez afficher le résultat grâce à la méthode [`eval()`](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/eval), cette méthode n'est pas très sécurisée mais pour cette calculatrice ce sera simple et efficace
   3. Dans le cas où cette condition est égale à la valeur de votre bouton effacer `C`, le contenu de votre écran doit disparaitre
   4. Le cas par défaut reprendra tout les autres boutons et devra affiché sur votre écran le bouton sur lequel votre utilisateur va cliquer
> Astuce : pensez à l'affectation après addition dans le cas par défaut 😊

N'oubliez pas que cet exercice étape par étape est une façon de faire parmi tant d'autres. N'hésitez surtout pas à aller voir des tutoriaux, des documentations ou même simplement de taper sur Google "comment faire une calculatrice en JS".

Voici le résultat que j'ai obtenu :<br>
![](../../Ressources/Images/calcResult.gif)

> Created by [Lucas Ielli](https://github.com/LucasIelli)
