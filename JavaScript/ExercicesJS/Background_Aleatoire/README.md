<!-- omit in toc -->
# Exercice étape par étape : changer aléatoirement la couleur de fond
<!-- omit in toc -->
- [Étape 1 : Structure HTML](#étape-1--structure-html)
- [Étape 2 : Liens CSS et JavaScript](#étape-2--liens-css-et-javascript)
- [Étape 3 : Écriture du CSS](#étape-3--écriture-du-css)
- [Étape 4 : Écriture du JavaScript](#étape-4--écriture-du-javascript)
- [Étape 5 : Ajout de l'Écouteur d'Événements](#étape-5--ajout-de-lécouteur-dévénements)


## Étape 1 : Structure HTML
- Crée un fichier HTML avec les balises de base (faites confiance à votre éditeur de code et utilisez `!`).
- Ajoute un bouton dans le corps de la page avec un identifiant (id) de `changeColorBtn`. Ce bouton servira à déclencher le changement de couleur.

## Étape 2 : Liens CSS et JavaScript
- Lier votre fichier ``style.css`` à votre HTML dans la balise ``<head>``.
- Lier votre fichier ``script.js`` à votre HTML à l'aide de la balise ``<script>`` et toujours en bas de page comme vu dans la [théorie](https://github.com/sirius-school/WebDev/blob/main/JavaScript/JS_Bases/bases_JS.md#la-balise-script).

## Étape 3 : Écriture du CSS
- Dans le fichier ``style.css``, définis le style de base de la page. Centre le contenu verticalement et horizontalement, utilise une [transition](https://developer.mozilla.org/fr/docs/Web/CSS/transition) pour adoucir le changement de couleur de fond.
> Pour effectuer la transition n'hésitez pas à cliquer sur le lien que je vous fourni plus haut.

## Étape 4 : Écriture du JavaScript
- Dans le fichier script.js, commence par sélectionner le bouton en utilisant `document.getElementById()`.
- Ensuite, crée une [fonction](https://github.com/sirius-school/WebDev/blob/main/JavaScript/JS_Bases/fonctions_conditions.md#les-fonctions-functions) (par exemple, `changeColor`) qui sera appelée lorsque le bouton est cliqué. À l'intérieur de cette fonction, génère une couleur aléatoire en utilisant `Math.round` et `Math.random`, comme dans les exemples de la [théorie](https://github.com/sirius-school/WebDev/blob/main/JavaScript/JS_Bases/manipulation_DOM_1.md#mathrandom-mathfloor-et-mathround).
- Modifie la couleur de fond du corps de la page en utilisant/copiant ce bout de code : 
```js
document.body.style.backgroundColor = // couleur aléatoire générée
```

## Étape 5 : Ajout de l'Écouteur d'Événements
- À l'extérieur de la fonction `changeColor`, [ajoute un écouteur d'événements](https://github.com/sirius-school/WebDev/blob/main/JavaScript/JS_Bases/manipulation_DOM_1.md#eventlistener) pour le bouton en utilisant `addEventListener()`. Cet écouteur déclenchera la fonction `changeColor` lorsque le bouton est cliqué.

> Created by [Lucas Ielli](https://github.com/LucasIelli)
