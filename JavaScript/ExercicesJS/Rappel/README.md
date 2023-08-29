<!-- omit in toc -->
# Exercice de rappel JavaScript

<!-- omit in toc -->
## Table des matières
- [LISEZ-MOI](#lisez-moi)
- [Exercice 1](#exercice-1)
- [Exercice 2](#exercice-2)
- [Exercice 3](#exercice-3)
- [Exercice 4](#exercice-4)
- [Exercice 5](#exercice-5)
- [Exercice 6](#exercice-6)
- [Exercice 7](#exercice-7)
- [Exercice 8](#exercice-8)
- [Exercice 9](#exercice-9)
- [Exercice 10](#exercice-10)
- [Exercice 11](#exercice-11)

## LISEZ-MOI

- Reprenez l'[`index.html`](./index.html), le [`style.css`](./style.css), le [`scripts.js`](./script.js) et le dossier [`Ressources`](./Ressources/), sans ça vous ne pourrez pas réaliser l'exercice
- Ne touchez pas au fichier HTML et CSS.
- N'hésitez pas à m'envoyer un message sur Discord ou à m'appeler si besoin.
- Faites-moi un retour sur les choses que vous ne comprenez pas dans les bases JS.
- N'hésitez pas à parcourir l'<span style="color: orange;">HTML</span>, le <span style="color: blue;">CSS</span> et le <span style="color: yellow;">script</span>. N'oubliez pas que vous avez la possibilité d'ouvrir votre console pour vérifier s'il y a des erreurs.
- Une fois que votre structure est prête, **LANCEZ LIVE SERVER** et regardez votre page !
- Assurez-vous de revoir attentivement chaque étape de l'exercice pour bien comprendre les concepts abordés et les appliquer correctement.
- OPTIONNEL : Si vous le souhaitez vous pouvez créer un repository pour chaque exercice. Cependant soyez sur de copier l'HTML et le CSS nécessaire à votre script.


## Exercice 1

- Créez une variable appelée "firstname" qui a pour valeur votre prénom. Assurez-vous que votre nom reste le même 😉
- Créez une variable "lastname" qui a pour valeur votre nom de famille.

## Exercice 2

- Créez une variable "age" qui a pour valeur votre âge et qui sera donc de type Number.

## Exercice 3

- Créez une variable "year" qui contiendra l'année 2023, de type Number.
- Créez une variable "birthYear" qui calcule votre année de naissance en utilisant les deux variables précédemment créées.

## Exercice 4

- Créez une variable "user" de type tableau qui inclut chacune des variables créées précédemment.

## Exercice 5

- Créez une variable "backgroundColor" qui pourra être réassignée et attribuez-lui une valeur de couleur de votre choix, comme vous le feriez en CSS.
- Réassignez une nouvelle couleur à votre variable backgroundColor, soyez inventif.

## Exercice 6

- Créez une variable "car" (voiture) de type objet qui contient 4 propriétés : "brand" (marque), "model" (modèle), "yearConstruct" (année de construction), "color" (couleur) et "image".
- La marque, le modèle et la couleur doivent être de type String, l'image doit être une URL sous forme de String, et l'année de construction doit être un chiffre.

## Exercice 7

- Créez une variable "buttons" pour récupérer TOUS les boutons en utilisant un `querySelectorAll()`.
- Créez une variable "cat" pour récupérer l'élément ayant l'ID `cat` dans votre HTML.
- Pour voir le résultat, appuyez sur l'un des 3 boutons (Photo $) sur votre page.

## Exercice 8

- Sélectionnez l'élément ayant l'ID "output" en utilisant `getElementById()` et insérez deux nouvelles balises HTML avec innerHTML. Vous aurez besoin d'une balise "p" avec un contenu de votre choix et d'une balise "img" avec la source suivante : `https://upload.wikimedia.org/wikipedia/commons/thumb/6/6a/JavaScript-logo.png/800px-JavaScript-logo.png`.

## Exercice 9

- Créez une variable de type tableau dans laquelle vous stockerez plusieurs valeurs dans le thème de votre choix.
- Créez une nouvelle variable pour récupérer l'ID "listOutput" en utilisant `getElementById()`.
- Utilisez une boucle `forEach` pour itérer sur votre tableau.
- Dans cette boucle, injectez plusieurs éléments "li" dans votre variable crée plus haut "listOutput" en utilisant `innerHTML`, chacun des "li" contenant une des valeurs de votre tableau.
- Attention : malgré la boucle, JavaScript recréera un nouvel élément "li" pour chaque élément de votre tableau, ce qui signifie que vous n'aurez finalement qu'un seul élément. Pour éviter cela, utilisez l'opérateur [`+=`](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/Addition_assignment) pour générer plusieurs "li". 

## Exercice 10

- Pour cet exercice, je vous fournis un tableau et dans [Ressources](./Ressources/images/) vous trouverez plusieurs icônes.
- Vous allez rendre l'icône affichée aléatoire lorsque vous accédez à votre page.
- Commencez par sélectionner l'élément ayant l'ID "logo" en utilisant "getElementById".
- Pour éviter de compter le nombre d'éléments de notre tableau, créez une variable contenant la longueur de votre tableau et soustrayez 1 (car l'index commence à 0).
- Ensuite, créez une variable qui génère un chiffre aléatoire entre 0 et 8. N'oubliez pas d'utiliser la variable précédemment créée pour l'index.
- Enfin, créez une variable contenant le chemin/lien des images en utilisant la syntaxe des backticks et en intégrant votre tableau et l'index généré aléatoirement. Utilisez cette variable pour changer la source de votre icône.

## Exercice 11
> Exercice optionnel

- Pour cet exercice, nous allons réutiliser le tableau de l'exercice 10.
- Cette fois, l'objectif est de permettre à l'utilisateur de choisir son icône.
- Dans le HTML, récupérez plusieurs éléments en utilisant la méthode de votre choix. Enregistrez les IDs "iconSelect" (qui permet à l'utilisateur de choisir dans un menu déroulant), "changeIcon" (qui permet de valider le choix) et "iconImage" (qui affichera l'icône sélectionnée).
- Créez une fonction et affichez un message avec console.log() pour vérifier son bon fonctionnement. N'oubliez pas de l'appeler ensuite 😉
- Sous votre fonction, ajoutez un gestionnaire d'événements de type "click". Devinez sur quel élément l'utilisateur doit cliquer pour déclencher votre fonction. Rappelez-vous que la méthode addEventListener prend deux paramètres : le type d'événement à écouter et la fonction à exécuter. Si vous aviez appelé votre fonction "normalement" à l'étape précédente, supprimez cet appel, car il ne sera pas nécessaire.
- Revenons à votre fonction. Vous souhaitez que l'utilisateur puisse choisir. Vous avez déjà effectué toutes vos sélections et appelé la fonction.
  - Votre fonction n'accepte pas de paramètre.
  - Créez une variable contenant la "value" de l'élément "iconSelect".
  - Utilisez une condition "if" (sans le "else") basée sur la valeur de la variable créée à l'étape précédente.
  - Si cette condition est vraie, créez une variable contenant le chemin/lien des images en utilisant la syntaxe des backticks. Intégrez votre variable contenant la valeur de votre sélection.
  - Modifiez ensuite la source de votre icône en utilisant cette nouvelle variable.

Vous êtes à la fin de ces différents exercices et j'espère que cela vous a permis de comprendre certains concepts de JavaScript. Félicitations en tout cas d'être arrivés jusqu'au bout ! 🎉

> Created by [Lucas Ielli](https://github.com/LucasIelli)



