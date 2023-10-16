<!-- omit in toc -->
# Type Ahead 👀

<!-- omit in toc -->
## Table des matières
- [Objectif :](#objectif-)
- [Exercice : Création d'un script de recherche de villes](#exercice--création-dun-script-de-recherche-de-villes)
  - [Étape 1 : Préparation du projet](#étape-1--préparation-du-projet)
  - [Étape 2 : Déclaration des variables et récupération des éléments HTML](#étape-2--déclaration-des-variables-et-récupération-des-éléments-html)
  - [Étape 3 : Récupération des données JSON](#étape-3--récupération-des-données-json)
  - [Étape 4 : Création de la fonction de recherche](#étape-4--création-de-la-fonction-de-recherche)
  - [Étape 5 : Formatage des nombres avec des virgules](#étape-5--formatage-des-nombres-avec-des-virgules)
  - [Étape 6 : Affichage des correspondances dans l'interface](#étape-6--affichage-des-correspondances-dans-linterface)
  - [Étape 7 : addEventListener(s)](#étape-7--addeventlisteners)
  - [Étape 8 : Test et finalisation](#étape-8--test-et-finalisation)
  - [Étape 9 : Défi (optionnel)](#étape-9--défi-optionnel)

## Objectif :

Donner à votre utilisateur la possibilité de rechercher une ville américaine grâce au fichier JSON fourni. Cela permettra à vote utilisateur de connaitre le nombre d'habitant de la ville ou l'état choisi.e, ainsi que l'état ou la ville rattaché.e à sa demande. Voici la vidéo [Youtube](https://youtu.be/eQDvA0OeK3E).

> Petit rappel : utilisez console.log() autant de fois que vous jugerez nécessaire.

## Exercice : Création d'un script de recherche de villes

### Étape 1 : Préparation du projet

1. Créez un nouveau repository pour votre projet et placez-y les fichiers HTML, CSS fournis.
2. Ouvrez le fichier HTML dans votre éditeur de code et faites la liaison de votre style et votre script.
3. ❗ **Examinez bien les deux fichiers avant de commencer**.

### Étape 2 : Déclaration des variables et récupération des éléments HTML

1. Créez un nouveau fichier JavaScript nommé `script.js` dans le même dossier que les autres fichiers.
2. Déclarez une variable pour stocker les données des villes. Initialisez cette variable comme un tableau vide.
3. Sélectionnez l'élément d'entrée de recherche (avec la classe "search") et stockez-le dans une variable.
4. Sélectionnez l'élément de liste pour les suggestions (avec la classe "suggestions") et stockez-le dans une variable.

### Étape 3 : Récupération des données JSON

1. Ouvrez le lien dans votre navigateur correspondant à la variable et observez bien ce fichier.
2. Pour plus de facilité de lecture n'hésitez pas à installer l'extension Chrome [JSON Viewer](https://chrome.google.com/webstore/detail/json-viewer/gbmdgpbipfallnflgajpaliibnhdgobh).
3. Utilisez la fonction `fetch` pour obtenir les données JSON à partir de l'URL `endpoint` fournie dans le code.
4. Utilisez `.then()` pour convertir la réponse en JSON.
5. Dans une autre méthode `.then()`, ajoutez les données au tableau de villes en utilisant une méthode pour envoyer les données dans votre variable qui a pour valeur un tableau vide.

> Nous verrons plus tard en détail la méthode Fetch qui permet de contacter une API.

### Étape 4 : Création de la fonction de recherche

1. Créez une fonction nommée `findMatches` qui prendra deux **paramètres** : le terme de recherche et le tableau de villes.
2. Dans la fonction `findMatches`, utilisez cette expression régulière `const regex = new RegExp(this.value, "gi");` pour effectuer une recherche insensible à la casse dans le tableau de villes aussi bien pour les états et les villes.
3. **Retournez** les correspondances trouvées.

### Étape 5 : Formatage des nombres avec des virgules

1. Créez une fonction nommée `numberWithCommas` qui prendra un nombre en paramètre.
2. Dans cette fonction, utilisez une expression régulière pour ajouter des virgules comme séparateurs de milliers au nombre.
3. **Retournez** le nombre formaté.

> Cette fonction est très compliqué car elle comprend une expression régulière très spécifique, je vous fourni donc la fonction complète, à vous de deviner où vous devriez l'utiliser

```js
function numberWithCommas(x) {
  return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ",");
}
```

### Étape 6 : Affichage des correspondances dans l'interface

1. Créez une fonction nommée `displayMatches`.
2. À l'intérieur de cette fonction, utilisez la fonction `findMatches` pour trouver les correspondances avec la valeur de l'élément d'entrée de recherche (`this.value`) dans le tableau de villes.
3. Utilisez `.map()` pour générer une liste HTML des correspondances en mettant en évidence les termes recherchés avec des balises `<span class="hl">`.
4. Utilisez `.join("")` pour convertir la liste en une chaîne HTML.
5. Affichez cette chaîne HTML dans l'élément d'affichage des suggestions (`suggestions.innerHTML`).

### Étape 7 : addEventListener(s)

1. Ajoutez des eventListener pour détecter les changements (`change`) et les frappes de touches (`keyup`) dans l'élément d'entrée de recherche.
2. Devinez la fonction qui devra être appelée.

### Étape 8 : Test et finalisation

1. Testez votre script et débuggez si nécessaire.
2. Saisissez des villes ou des états dans le champ de recherche pour voir les suggestions en action.
3. Vérifiez la console du navigateur pour vous assurer qu'aucune erreur n'apparaît.

### Étape 9 : Défi (optionnel)

1. Challenge : Modifiez le script pour ajouter des fonctionnalités supplémentaires, telles qu'un bouton de réinitialisation pour effacer le champ de recherche ou des filtres de recherche plus avancés.
2. Testez et améliorez votre script en fonction de ces ajouts.