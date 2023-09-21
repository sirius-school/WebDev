<!-- omit in toc -->
# Exercices sur les boucles
<!-- omit in toc -->
## Tables des matières
- [Introduction](#introduction)
- [Exercice 1 : Utilisation de la boucle `for`](#exercice-1--utilisation-de-la-boucle-for)
- [Exercice 2 : Utilisation de la boucle `while`](#exercice-2--utilisation-de-la-boucle-while)
- [Exercice 3 : Utilisation de la boucle `for...in`](#exercice-3--utilisation-de-la-boucle-forin)
- [Exercice 4 : Utilisation de la boucle `for...of`](#exercice-4--utilisation-de-la-boucle-forof)
- [OPTIONNEL Exercice 5 : Utilisation de la boucle `do...while`](#optionnel-exercice-5--utilisation-de-la-boucle-dowhile)


## Introduction

Aborder les exercices un par un, en résolvant chaque exercice avant de passer au suivant. Si vous avez des questions ou si vous avez besoin d'aide pour l'un des exercices, n'hésitez pas à demander !

## Exercice 1 : Utilisation de la boucle `for`

**Objectif :** Créer une fonction qui affiche les nombres de 1 à `nombre`, où `nombre` est un paramètre de la fonction.

1. Déclarez une fonction nommée `afficherNombres` qui prend un paramètre `nombre`.
2. Utilisez une boucle `for` pour afficher tous les nombres de 1 à `nombre` dans la console.

Exemple d'utilisation :

```javascript
afficherNombres(5);
// Résultat attendu :
// 1
// 2
// 3
// 4
// 5
```

## Exercice 2 : Utilisation de la boucle `while`

**Objectif :** Créer une fonction qui calcule la somme des entiers de 1 à `nombre`, où `nombre` est un argument de la fonction.

1. Déclarez une fonction nommée `calculerSomme` qui prend un paramètre `nombre`.
2. Utilisez une boucle `while` pour calculer la somme des entiers de 1 à `nombre`.
3. Retournez la somme calculée.

Exemple d'utilisation :

```javascript
const somme = calculerSomme(5);
console.log(somme); // Résultat attendu : 15 (car 1 + 2 + 3 + 4 + 5 = 15)
```

## Exercice 3 : Utilisation de la boucle `for...in`

**Objectif :** Créer une fonction qui affiche les propriétés et les valeurs d'un objet.

1. Déclarez une fonction nommée `afficherObjet` qui prend un argument `objet`.
2. Utilisez une boucle `for...in` pour parcourir toutes les propriétés de l'objet et afficher le nom de la propriété suivi de sa valeur.

Exemple d'utilisation :

```javascript
const personne = {
    prenom: "Bertrand",
    nomDeFamille: "Dupuis",
    age: 30,
    profession: "Développeur",
    naissance: 1993,
    situation: "Marié",
    enfants: 2
};

afficherObjet(personne);
// Résultat attendu :
//  prenom: "Bertrand"
//  nomDeFamille: "Dupuis"
//  age: 30
//  profession: "Développeur"
//  naissance: 1993
//  situation: "Marié"
//  enfants: 2
```

## Exercice 4 : Utilisation de la boucle `for...of`

**Objectif :** Créer une fonction qui calcule la somme des éléments d'un tableau de nombres.

1. Déclarez une fonction nommée `calculerSommeTableau` qui prend un tableau d'entiers comme argument.
2. Utilisez une boucle `for...of` pour parcourir tous les éléments du tableau et calculez leur somme.
3. Retournez la somme calculée.

Exemple d'utilisation :

```javascript
const nombres = [1, 2, 3, 4, 5];
const somme = calculerSommeTableau(nombres);
console.log(somme); // Résultat attendu : 15 (car 1 + 2 + 3 + 4 + 5 = 15)
```

## OPTIONNEL Exercice 5 : Utilisation de la boucle `do...while`

**Objectif :** Créer une fonction qui demande à l'utilisateur de deviner un nombre jusqu'à ce qu'il devine correctement.

1. Déclarez une fonction nommée `devinerNombre`.
2. Générez un nombre aléatoire entre 1 et 10 (inclus) et stockez-le dans une variable.
3. Utilisez une boucle `do...while` pour demander à l'utilisateur de deviner le nombre jusqu'à ce qu'il le devine correctement.
4. Affichez un message de félicitations lorsque l'utilisateur devine correctement.

Exemple d'utilisation (simulation) :

```javascript
devinerNombre(); // Le programme génère un nombre aléatoire, puis demande à l'utilisateur de deviner jusqu'à ce qu'il réussisse.
```