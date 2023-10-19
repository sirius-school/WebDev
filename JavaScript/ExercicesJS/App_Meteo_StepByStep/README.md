# Application météo étape par étape

## Étape 1 : Préparation du projet

1. Comme chacun des projets n'oubliez pas de créer un repository et de faire des commits réguliers.
2. Rendez-vous sur le site OpenWeatherMap à l'adresse suivante : [https://openweathermap.org](https://openweathermap.org).
3. Inscrivez-vous ou connectez-vous à votre compte si nécessaire.
4. Une fois connecté, accédez à votre tableau de bord ou à la section "API keys" pour créer une nouvelle clé API.
5. Suivez les instructions pour générer une nouvelle clé API pour accéder aux données météorologiques.
6. Accédez à la documentation de l'API OpenWeatherMap à l'adresse : [https://openweathermap.org/forecast5](https://openweathermap.org/forecast5).
7. Familiarisez-vous avec la documentation, en particulier avec les éléments suivants :
   - Les paramètres nécessaires pour effectuer une requête météo, tels que les coordonnées géographiques (latitude et longitude).
   - Les unités de mesure disponibles (par exemple, les températures en Celsius).
   - L'URL de base pour effectuer des requêtes météo.
   - Les informations sur les données renvoyées par l'API, y compris la structure des réponses.

## Étape 2 : Création de l'HTML

1. Créez un fichier index.html vide.
2. Ajoutez la structure de base d'un document HTML en utilisant `!`.
3. À l'intérieur de la balise `<head>`, n'oubliez pas de lier votre fichier style.css.
4. Déclarez le titre de la page en utilisant la balise `<title>` avec par exemple le texte "Weather App".
5. Créez un modèle HTML en utilisant la balise `<template>` avec un identifiant unique, par exemple, `id="weather-template"`. À l'intérieur du modèle, créez une liste (`<ul>`) avec un identifiant `id="weather-output"`.
6. Dans le `<body>`, créez un en-tête (`<main>`) avec un titre `<h1>` indiquant par exemple "Upcoming Weather".

## Étape facultative : Création de votre style

## Étape 3 : JavaScript - Variables

1. Créez un fichier JavaScript.
2. Déclarez les variables nécessaires pour stocker la latitude (`liegeLat`), la longitude (`liegeLon`), la clé API (`apiKey`), l'URL de l'API (`weatherUrl`), et la référence à l'élément HTML où vous afficherez les données météo (`weatherOutput`).

## Étape 4 : JavaScript - Fetch

1. Utilisez la fonction `fetch()` pour effectuer une requête à l'API OpenWeatherMap en utilisant l'URL `weatherUrl`.
2. Gérez les réponses du serveur en utilisant la méthode `.then()`.

## Étape 5 : JavaScript - Conversion de la Réponse en JSON

- Dans le `.then()`, utilisez `response.json()` pour convertir la réponse en un objet JavaScript contenant les données météo.

## Étape 6 : JavaScript - Affichage des Données

1. Créez le prochain `.then()`, accédez aux données météo à partir de l'objet JavaScript résultant (`weatherData`).
2. Parcourez les prévisions météorologiques (`weatherList`) à l'intérieur de cet objet.
3. Utilisez les données pour remplir le modèle HTML (template) en insérant dynamiquement les éléments nécessaires dans l'élément `<ul id="weather-output">`.

## Étape 7 : JavaScript - Gestion des Erreurs

- Gérez les erreurs potentielles avec `.catch()` en affichant les erreurs dans la console.

> Created by [Lucas Ielli](https://github.com/LucasIelli)
