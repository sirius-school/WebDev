# classList et ses méthodes

- [classList et ses méthodes](#classlist-et-ses-méthodes)
  - [Introduction](#introduction)
  - [Accéder à classList](#accéder-à-classlist)
  - [Méthodes de classList](#méthodes-de-classlist)
  - [Utilisation pratique](#utilisation-pratique)


## Introduction

La propriété `classList` en JavaScript est utilisée pour accéder et manipuler les classes CSS d'un élément HTML. Elle fournit des méthodes pratiques pour ajouter, supprimer, vérifier la présence de classes et bien plus encore. Cela offre une manière plus élégante et efficace de gérer les classes CSS par rapport à la manipulation manuelle de la chaîne de caractères de la propriété `class`.

## Accéder à classList

Pour accéder à la propriété `classList` d'un élément HTML, vous pouvez simplement utiliser la syntaxe suivante :

```javascript
const element = document.getElementById("monElement");
const class = element.classList;
```

## Méthodes de classList

1. **`add()`** : Ajoute une ou plusieurs classes à l'élément.

   ```javascript
   element.classList.add("maClasse");
   element.classList.add("classe1", "classe2");
   ```

2. **`remove()`** : Supprime une ou plusieurs classes de l'élément.

   ```javascript
   element.classList.remove("maClasse");
   element.classList.remove("classe1", "classe2");
   ```

3. **`toggle()`** : Ajoute la classe si elle n'est pas présente, la supprime si elle est présente.

   ```javascript
   element.classList.toggle("maClasse");
   ```

4. **`contains()`** : Vérifie si l'élément a une classe spécifique.

   ```javascript
   if (element.classList.contains("maClasse")) {
       console.log(element);
   }
   ```

5. **`replace()`** : Remplace une classe par une autre.

   ```javascript
   element.classList.replace("ancienneClasse", "nouvelleClasse");
   ```

6. **`item(i)`** ou **classList[i]** : Récupère la classe à un index spécifique dans la liste des classes.

   ```javascript
   const classeAtIndex = element.classList.item(0); // Récupère la première classe
   const classeAtIndex = element.classList[0]; // Donne le même résultat qu'avec item()
   ```

7. **`length`** : Récupère le nombre total de classes sur l'élément.

   ```javascript
   const nombreClasses = element.classList.length;
   ```

8. **`toString()`** : Convertit la liste de classes en une chaîne de caractères.

   ```javascript
   const classesEnChaine = element.classList.toString();
   ```

9. **`value`** : Quasiment identique à `toString()`, retourne la liste de classes en tant que chaîne de caractères.

   ```javascript
   const classesEnChaine = element.classList.value;
   ```

## Utilisation pratique

La propriété `classList` peut être utilisée en conjonction avec les événements et la logique de votre application pour créer des interactions plus dynamiques en modifiant les classes CSS en temps réel. Comme vous l'avez fait sur l'exercice de la Todo Liste.

Par exemple, vous pouvez créer des animations CSS en ajoutant ou en supprimant des classes lorsque certains événements se produisent (clics, survols, etc). De plus, cela peut être utilisé pour activer ou désactiver des styles spécifiques en fonction de l'état de votre application.

En conclusion, la propriété `classList` en JavaScript est un outil puissant pour gérer les classes CSS des éléments HTML de manière propre et efficace, en offrant une meilleure organisation et une manipulation plus simple des styles de votre page web.

> Made by [Lucas Ielli](https://github.com/LucasIelli)
