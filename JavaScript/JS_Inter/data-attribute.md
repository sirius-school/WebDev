<!-- omit in toc -->
# Attributs HTML personnalisés
<!-- omit in toc -->
## Table des matières
- [Introduction](#introduction)
- [Attributs `data-*`](#attributs-data-)
- [Accès aux attributs `data-*` en JavaScript](#accès-aux-attributs-data--en-javascript)
- [Modification des attributs `data-*` en JavaScript](#modification-des-attributs-data--en-javascript)
- [Utilisation dans les sélecteurs CSS](#utilisation-dans-les-sélecteurs-css)
- [Utilisation dans les scripts JavaScript](#utilisation-dans-les-scripts-javascript)
- [Avantages des attributs `data-*`](#avantages-des-attributs-data-)
- [Considérations importantes](#considérations-importantes)

## Introduction

Les attributs HTML personnalisés `data-*` offrent une manière élégante d'ajouter des métadonnées à des éléments HTML sans altérer leur fonctionnalité ou leur style. Ces attributs commencent par "data-" suivi d'un nom que vous pouvez personnaliser pour stocker des informations supplémentaires sur les éléments, ce qui est très utile dans l'utilisation de JavaScript et CSS.

## Attributs `data-*`

Les attributs `data-*` sont conçus pour stocker des informations personnalisées liées à un élément. Ils peuvent être utilisés pour stocker n'importe quel type de données, comme des identifiants, des valeurs booléennes, des chaînes de caractères, etc.

Voici un exemple d'utilisation d'un attribut `data-*` :

```html
<div id="monElement" data-couleur="bleu" data-actif="true">Contenu de l'élément</div>
```

## Accès aux attributs `data-*` en JavaScript

Pour accéder aux attributs `data-*` en JavaScript, vous pouvez utiliser la propriété `dataset` sur l'élément. Cette propriété renvoie un objet contenant toutes les valeurs `data-*` de l'élément.

```javascript
const monElement = document.getElementById("monElement");
const couleur = monElement.dataset.couleur; // Résultat "bleu"
const actif = monElement.dataset.actif; // Résultat "true"
```

## Modification des attributs `data-*` en JavaScript

Vous pouvez également modifier les valeurs des attributs `data-*` en utilisant la propriété `dataset`.

```javascript
monElement.dataset.couleur = "vert";
monElement.dataset.actif = "false";
```

## Utilisation dans les sélecteurs CSS

Les attributs `data-*` peuvent être utilisés dans les sélecteurs CSS pour cibler spécifiquement des éléments avec certaines valeurs `data-*`.

```css
[data-couleur="bleu"] {
    color: blue;
}
```

## Utilisation dans les scripts JavaScript

Les attributs `data-*` sont utiles pour stocker des données liées à des éléments, ce qui facilite la manipulation et la personnalisation des interactions en JavaScript.

```javascript
if (monElement.dataset.actif === "true") {
    // Faire quelque chose si l'élément est actif
}
```

## Avantages des attributs `data-*`

- **Sémantique** : Les attributs `data-*` ajoutent de la sémantique à vos éléments HTML en spécifiant leur intention.

- **Souplesse** : Vous pouvez stocker divers types de données dans les attributs `data-*`.

- **Interopérabilité** : Les attributs `data-*` sont bien pris en charge par les navigateurs modernes.

- **Accessibilité** : Les attributs `data-*` n'interfèrent pas avec l'accessibilité des éléments.

## Considérations importantes

- Les noms des attributs `data-*` ne doivent pas contenir de caractères spéciaux ni commencer par un chiffre.

- L'utilisation de noms cohérents et significatifs pour les attributs `data-*` est essentielle pour garantir la compréhension du code.

- Utilisez les attributs `data-*` pour stocker des données de configuration ou de contexte, et non pour des données qui devraient être gérées par une API de données.

En conclusion, les attributs HTML personnalisés `data-*` sont un moyen puissant d'étendre les éléments HTML en stockant des informations personnalisées. Ils facilitent la manipulation en JavaScript et permettent de créer des styles CSS ciblés. Utilisez-les judicieusement pour améliorer la modularité et l'efficacité de votre code.

> Made by [Lucas Ielli](https://github.com/LucasIelli)

