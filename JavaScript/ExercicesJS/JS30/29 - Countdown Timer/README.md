<!-- omit in toc -->
# Countdown timer étape par étape
<!-- omit in toc -->
## Table des matières
- [Introduction](#introduction)
- [Étape 1: Sélection des éléments HTML](#étape-1-sélection-des-éléments-html)
- [Étape 2: La fonction `timer(seconds)`](#étape-2-la-fonction-timerseconds)
- [Étape 3: Calcul du temps de fin](#étape-3-calcul-du-temps-de-fin)
- [Étape 4: Affichage du temps restant](#étape-4-affichage-du-temps-restant)
- [Étape 5: Affichage de l'heure de fin](#étape-5-affichage-de-lheure-de-fin)
- [Étape 6: Démarrage du minuteur avec les boutons](#étape-6-démarrage-du-minuteur-avec-les-boutons)
- [Étape 7: Gestion du formulaire personnalisé](#étape-7-gestion-du-formulaire-personnalisé)

## Introduction
- Créez un repository, faites des commits et push. Envoyez moi le résultat de l'exercice par message privé sur Discord.
- L'objectif de ce code est de créer une page web interactive qui affiche un minuteur que les utilisateurs peuvent utiliser pour définir des durées de temps et déclencher un compte à rebours. Le minuteur est conçu pour diverses utilisations, telles que la gestion du temps de travail, la prise de courtes pauses, le décompte du temps jusqu'à un événement, etc.
- N'oubliez pas d'utiliser console.log() pour vérifier ce que vous avez récupérer.

## Étape 1: Sélection des éléments HTML
- Commencez par sélectionner les éléments HTML nécessaires. Utilisez `document.querySelector` et `document.querySelectorAll` pour obtenir les éléments `timerDisplay`, `endTime`, et `buttons`.

## Étape 2: La fonction `timer(seconds)`
- Créez la fonction `timer` qui prend un argument `seconds` (nombre de secondes pour le minuteur).
- À l'intérieur de la fonction, commencez par effacer tout minuteur existant en utilisant `clearInterval(countdown)`. Cette étape garantit qu'un seul minuteur est actif à la fois.

## Étape 3: Calcul du temps de fin
- Calculez le moment de fin en ajoutant le nombre de secondes au moment actuel. Utilisez `Date.now()` pour obtenir le temps actuel.

## Étape 4: Affichage du temps restant
- Créez une fonction `displayTimeLeft(seconds)` qui prend un argument `seconds` et calcule les minutes et les secondes restantes.
- Mettez en forme le temps restant sous forme de texte (minutes:secondes) et mettez-le à jour dans `timerDisplay.textContent`.

## Étape 5: Affichage de l'heure de fin
- Créez une fonction `displayEndTime(timestamp)` qui prend un argument `timestamp` (l'heure de fin).
- Calculez l'heure et les minutes à partir du timestamp, ajustez l'heure si nécessaire (pour un format 12 heures), et affichez l'heure de fin dans `endTime.textContent`.

## Étape 6: Démarrage du minuteur avec les boutons
- Ajoutez un gestionnaire d'événements à chaque bouton dans la liste `buttons`. Lorsqu'un bouton est cliqué, appelez la fonction `startTimer` avec la durée appropriée en secondes.

## Étape 7: Gestion du formulaire personnalisé
- Ajoutez un gestionnaire d'événements au formulaire `customForm`. Lorsque le formulaire est soumis, empêchez son comportement par défaut (rechargement de la page).
- Récupérez la valeur entrée par l'utilisateur (minutes) et convertissez-la en secondes (en multipliant par 60).
- Appelez la fonction `timer` avec cette durée personnalisée.
- Réinitialisez le formulaire avec `this.reset()` pour effacer la zone de saisie.

Une fois que ces étapes sont suivies, le script devrait permettre de démarrer et de gérer un minuteur en fonction de la durée sélectionnée par l'utilisateur ou saisie dans le formulaire. Testez votre code dans votre navigateur pour s'assurer que tout fonctionne correctement.

> Created by [Lucas Ielli](https://github.com/LucasIelli)
