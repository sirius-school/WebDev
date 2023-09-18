<!-- omit in toc -->
# Todo liste étapes par étapes
<!-- omit in toc -->
## Table des matières
- [Introduction](#introduction)
- [Étape 1: Créer un repository](#étape-1-créer-un-repository)
- [Étape 2: Structure HTML](#étape-2-structure-html)
- [Étape 3: Style CSS](#étape-3-style-css)
- [Étape 4: Ajouter une tâche avec JavaScript](#étape-4-ajouter-une-tâche-avec-javascript)
- [Étape 5: Supprimer une tâche avec JavaScript](#étape-5-supprimer-une-tâche-avec-javascript)
- [Étape 6: Styliser les tâches complétées](#étape-6-styliser-les-tâches-complétées)
- [Étape 7: Publier votre projet](#étape-7-publier-votre-projet)

## Introduction
Cet exercice TodoList a pour but de vous familiariser un peu plus avec HTML, CSS et JavaScript. Pour finir l'exercice il faudra être vigilant et suivre chaque étape à la lettre pour éviter une erreur dans votre console. N'hésitez pas à cliquer sur les liens des différentes ressources pour bien comprendre ce qu'éxécutera votre ligne de code. Évidemment votre console est là pour vous aider et comprendre lorsque vous avez une erreur alors *consologer* (oui j'ai inventé un nouveau verbe) un **max**

## Étape 1: Créer un repository
1. Commencez par créer votre repositery sur [Github.com](https://www.github.com/) en public et surtout cochez la case README
2. Copiez l'URL de clône de votre repository sur Github.com
3. Ouvrez votre terminal en administrateur (cela vous évitera des surprises) et sélectionner le dossier dans lequel vous souhaitez mettre votre projet. Logiquement le chemin devrait être `C:/Users/Sirius/WebDev/JS`
4. Utilisez la commande `git clone` et collez l'URL de votre repo à la suite
5. N'oubliez pas de `git add .`, `git commit -m "Votre message explicatif"` à chaque grandes étapes pour éviter toutes pertes de données
6. Il est préfèrable d'utiliser `git push` lorsque vous estimez qu'il y a déjà beaucoup de données ou simplement à midi et/ou en fin de journée. Je précise qu'avant de `git push` vous êtes obligés de `git add .` et `git commit -m ""`
7. Quand vous avez fini votre projet **si** vous avez créé une autre branche, n'oubliez pas de `git merge`
8. Une fois que votre projet est totalement fini et sur la bonne branche ***vous devez m'envoyer votre repository par message privé sur Discord***

## Étape 2: Structure HTML
1. Commencez par créer un fichier `index.html` et ajoutez la structure de base en utilisant emmet sur VSCode `!`
2. À l'intérieur de la balise `<body>`, créez une `<div>` avec une classe `todo-container`
3. À l'intérieur de cette `<div>`, ajoutez un titre `<h1>` avec le texte "Todo List"
4. Ajoutez une balise `<input>` avec un attribut `type="text"`, un id `task`, un attribut `maxlength="30"` et le terme `required` pour que votre utilisateur puisse entrer une tâche qui aura une longueur maximale de 30 caractères et qui sera obligatoire, cela vous évitera d'avoir des tâches vides ou trop longues.
5. Ajoutez un bouton `<button>` avec l'id `add-task` et le texte "Add Task"
6. Ajoutez une liste `<ul>` avec un id `task-list` pour afficher les tâches
7. Dans cette balise `<ul>` ajoutez 3 balises `<li>`
8. Dans chaque balise `<li>`
   1. Ajoutez une balise `<p>`
   2. Ajouter une balise ``<div>``
   3. Dans cette ``<div>``
      1. Ajoutez deux balises `<button>`
      2. Le premier sera le bouton `Done`
      3. Le deuxième sera le bouton `Delete`
> Astuce : créez une première `<li>` ensuite dupliquez la 😉
9. Liez votre CSS `./style.css` et votre script `./script.js` sans oublier le `./` qui est une bonne pratique et qui vous permet d'éviter une erreur quand vous publierez votre page

## Étape 3: Style CSS
1. Créez un fichier CSS séparé nommé `style.css`
2. Commencez par cibler le `<body>`
   1. Définissez une police de caractères
   2. Définissez une couleur d'arrière-plan
   3. Définissez une largeur à `100%`
   4. Définissez, si besoin, le margin et le padding
3. Ciblez la classe `todo-container`
   1. Définissez, si besoin, le margin et le padding
   2. Stylez le conteneur pour qu'il soit centré 
4. Stylez le champ de texte `<input>` et le `<button>`
   1.  Ajoutez du padding `10px` en haut et en bas
   2.  Ajoutez du padding `5px` à droite et à gauche
   3.  Stylez la bordure avec `border-radius`
5. Stylez le bouton `<button>`
   1. Définissez une couleur de fond
   2. Définissez une couleur de bordure
   3. Définissez la propriété `cursor` de type `pointer`
   4. Définissez une propriété [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition)
   5. Définissez une [`box-shadow`](https://developer.mozilla.org/fr/docs/Web/CSS/box-shadow) de survol
6. Ciblez la liste `<ul>`
   1. Changez la marge par défaut
   2. Retirez le padding
   3. Définissez le display en `flex`
   4. Changez la direction pour que le flex soit en `colonne`
   5. Centrez verticalement et horizontalement les éléments
7. Ciblez les éléments `<li>` pour retirer le style par défaut
8. Vous pourrez prendre plus de temps pour styler votre page web lorsque vous aurez terminer le JavaScript, l'exercice est que vous interagissiez avec votre utilisateur.

## Étape 4: Ajouter une tâche avec JavaScript
1. Créez un fichier JavaScript séparé nommé `script.js`
2. Commencez par créez une variable en sélectionnant les éléments HTML importants :
   1. L'élément avec l'id `task`
   2. L'élément avec l'id `add-task`
   3. L'élément avec l'id `task-list`
3. Créez une fonction `addTask()`, dans un premier temps pour vérification, ajoutez simplement un `console.log("Hello");`
4. Ajoutez un [`addEventListener()`](https://developer.mozilla.org/fr/docs/Web/API/EventTarget/addEventListener) de type `click` au bouton "Add Task" qui éxécutera votre fonction
5. Essayez votre script en cliquant sur votre bouton "Add task" dans votre page web et donc regardez dans votre console
6. Retournez dans votre fonction `addTask()`
   1. Créez une variable pour récuperer la valeur de l'input grâce au mot-clé `.value`, n'hésitez pas à `console.log()`
   2. Appelez votre variable attaché à l'ID `task-list` suivi du terme [`innerHTML`](https://developer.mozilla.org/fr/docs/Web/API/Element/innerHTML) qui vous permet d'injecter du code HTML via JavaScript
   3. L'opérateur pour injecter vos tâches ne sera pas un simple `=` mais [`+=`](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/Addition_assignment) cela permet de ne pas écraser les tâches déjà existantes. Le concept derrière cet opérateur est un peu comme la méthode `push()` dans une variable de type tableau.
   4. Il faut maintenant ajouter la tâche de votre utilisateur, que vous avez déjà créé dans votre HTML.
      1. Copiez l'un des `<li>` de votre HTML en prenant bien toute la balise et vous pouvez supprimer les 3 `li` de votre HTML.
      2. Collez votre bout de code HTML à la suite de votre opérateur `+=` et entre des backticks `"``"` sans les guillemets
      3. Dans votre balise `<p>` appelez votre variable contenant la valeur de votre input
7. Testez votre code sur votre page web. Vous remarquerez que cela fonctionne, seulement l'input garde la valeur de ce que vous avez tapé
8. Pour remédier à cela retourné dans votre fonction `addTask()`
   1. Prenez votre variable contenant l'ID `task`
   2. Pointez la valeur grâce à `.value`
   3. Assignez une nouvelle valeur vide ""
> Vous remarquerez que vous n'utilisez pas directement la variable qui pourtant contient déjà la valeur de votre input tout simplement parce que cette valeur est déjà utilisée pour générer la tâche de votre utilisateur
9. Testez votre code, à cette étape lorsque vous entrez une phrase dans l'input et que vous cliquez sur "Add Task" vous devriez pouvoir ajoutez des tâches l'une à la suite de l'autre avec un intitulé, un bouton "Done" et un bouton "Delete"

## Étape 5: Supprimer une tâche avec JavaScript

1. Dans votre fichier `script.js` créez une nouvelle fonction nommée `deleteTask()` avec un paramètre [`event`](https://developer.mozilla.org/fr/docs/Web/Events/Creating_and_triggering_events). Pour ce qui est de son script, pour le moment faites simplement un `console.log();` du paramètre `event`
2. En dessous de la réaction événement pour ajouter une tâche, ajoutez un `addEventListener()` de type `click` à votre variable contenant l'ID `task-list` et appelé votre fonction `deleteTask`
3. Testez votre code en cliquant sur le bouton `Delete` et surtout regardez dans votre console pour voir à quoi correspond `event` alors il y a pas mal de choses mais retenez simplement que c'est l'ensemble des objets que représente un click sur une page web
4. Retournez dans votre fonction `deleteTask()`
   1. Vous allez spécifier un peu plus le paramètre `event` en lui apportant le terme `.target`, n'hésitez pas à le `console.log()`. Cela vous permet de cibler et de récupérer le bouton sur lequel vous cliquez
   2. Créez une variable à laquelle vous allez assigner la valeur `event.target`, mais pas que, vous allez avoir besoin d'utiliser soit [`parentElement`](https://developer.mozilla.org/fr/docs/Web/API/Node/parentElement) soit la méthode [`closest()`](https://developer.mozilla.org/fr/docs/Web/API/Element/closest). Dans les deux cas, cela vous permet de sélectionner le parent de votre bouton
      1. Si vous utilisez `parentElement` il faudra le faire deux fois, en effet le premier parent de votre bouton c'est la `<div>`, le deuxième parent est votre `<li>` ce qui est l'élément que vous voules supprimer
      2. Si vous utiliser la méthode `closest()` vous devrez simplement spécifier `li` comme premier paramètre, en d'autres termes `closest()` permet de sélectionner le premier élément `<li>` ou une autre balise le plus proche de votre cible
   3. Maintenant que votre variable possède la bonne valeur/sélection il vous suffit de faire appel à la méthode [`remove()`](https://developer.mozilla.org/fr/docs/Web/API/Element/remove)
5. Testez votre code, à ce stade vous devriez être capable de supprimer une tâche entièrement en cliquant sur le bouton `Delete` de cette dernière
> Vous pouvez si vous le souhaitez ajouter une méthode confirm() pour que votre utilisateur puisse revenir sur sa décision de suppression, évidemment à l'aide d'une condition

## Étape 6: Styliser les tâches complétées
1. Dans votre fichier CSS, ajoutez une classe `.completed` pour styliser les tâches complétées.
   1. Définissez une couleur qui spécifie que cette tâche est "désactivée", du gris clair est plutôt parlant
   2. Définissez une décoration texte de type `line-trough` pour accentuer cet effet "désactivée", n'oubliez pas la couleur de cette décoration
2. Stylez les boutons
   1. Sélectionnez la classe `done` définissez une couleur d'arrière plan en vert par exemple
   2. Sélectionnez la classe `undo` définissez une couleur d'arrière plan en bleu par exemple
   3. Sélectionnez la classe `delete` définissez une couleur d'arrière plan en rouge par exemple
3. Retournez dans votre fichier `script.js`, il va falloir maintenant faire appel à votre classe `.completed` lorsque votre utilisateur clique sur le bouton "Done" (fait) qui devra se transformer en bouton "Undo" (annuler)
4. Vous allez réutilisez la fonction `deleteTask()` elle vous permet déjà de cibler un élément sur votre page et donc pourra servir à cibler le bouton "Done"
5. Renommez la fonction `deleteTask()` en `deleteOrCompleteTask()`, n'oubliez pas de changer son appel dans l'`addEventListener()`
6. Dans votre fonction `addTask()` la génération de votre `li` nécessite deux changements
   1. Ajoutez une classe `done` sur votre bouton "Done"
   2. Ajoutez une classe `delete` sur votre bouton "Delete"
7. Ajoutez une condition `if...else` dans votre fonction `deleteOrCompleteTask()`
   1. La première condition doit être l'[`event.target.classList[0]`](https://developer.mozilla.org/fr/docs/Web/API/Element/classList), "consologez" le pour voir ce que vous obtenez, classList génère un tableau il faut donc sélectionner le bon indice. Cet élément doit être égale (pas strictement égale) à `"done"`
      1. Si cette condition est respectée, vous devez retirer la classe `done` grâce à la méthode [`remove()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/remove)
      2. Et vous devez ajouter la classe `undo` grâce à la méthode [`add()`](https://developer.mozilla.org/fr/docs/Web/API/DOMTokenList/add)
      3. Il y a deux autres méthode que je vous laisse essayer car elle sont un peu plus complexe à comprendre, [`toggle()`](https://developer.mozilla.org/fr/docs/Web/API/DOMTokenList/toggle) et [`replace()`](https://developer.mozilla.org/en-US/docs/Web/API/DOMTokenList/replace)
   2. La deuxième condition vient s'insérer entre votre `if` et votre `else` grâce au terme `else if (){}` qui est en quelque sorte un deuxième `if(){}` entre les parenthèses sera votre condition qui est la même que le `if` mais cette fois doit être égale à `"undo"`
      1. Si cette deuxième condition est respecté, vous souhaitez retirer la classe `undo`
      2. Et évidemment ajouter la classe `done`
   3. Transformez votre `else` en `else if` avec toujours la même condition à part que cela doit être égale à `delete` cette fois. Si cette condition est remplie elle doit contenir le bout de code qui servait à supprimer la tâche de votre utilisateur. En effet si le bouton cible n'est ni "Done" ni "Undo" alors c'est que le bouton cible est "Delete"
8. Dans votre première condition `if` il faut maintenant s'occuper de "désactiver" la tâche. Précédemment vous aviez créé une variable qui contient votre `li` avec `closest()` ou `parentElement` ajoutez lui la classe `completed`
9. Dans votre deuxième condition `else if` il faut évidemment supprimer la classe `completed` pour "réactiver" la tâche de votre utilisateur
10. Il ne reste plus qu'une chose à prendre en compte, le bouton `done` garde le texte "Done" ce serait plus intuitif que le texte soit "Undo".
    1.  Rien de plus simple dans votre première condition `if` sélectionner de nouveau votre `event.target` qui n'est autre que le bouton sur lequel vous cliquez et utilisez [`textContent`](https://developer.mozilla.org/fr/docs/Web/API/Node/textContent) avec pour valeur `"Undo"`
    2.  Dans votre deuxième condition c'est la même chose à part que le texte sera `Done`
11. Je remarque qu'il y a une erreur lorsque vous cliquez sur le bouton "Done" il y a une ligne qui se créée entre les deux boutons "Undo" et "Delete", ce n'est pas très beau, règlons ça.
    1.  Le problème se situe au niveau de la variable avec la sélection via `parentElement` ou `closest()`
    2.  Dans les deux appels de cette variable il faut sélectionner le premier enfant de votre `li` qui n'est autre que votre balise `p` car c'est cette balise que l'on veut "désactivée" et non l'entièreté du `li`
    3.  Utilisez `firstElementChild` dans l'appel de vos variables. Dans votre première condition et dans la deuxième condition aussi

## Étape 7: Publier votre projet
1. Sur [Github.com](https://github.com) vous avez la possibilité de publier votre projet il sera donc disponible sur internet.
   1. Rendez-vous sur votre repository (github.com/Utilisateur/NomDuRepository)
   2. Dans les onglets d'options de votre repo cliquez sur "Paramètres" ou "Settings" (je vous conseille de ne pas trop traduire la page Github, vous pourriez avoir des erreurs)
   3. Dans le menu des paramètres cliquez sur "Pages"
   4. Plusieurs options s'offrent à vous
      1. La source que vous ne devez pas changer
      2. La branch sur laquelle se trouve le projet que vous voulez publier, il est plus que préfèrable de choisir la branche `main` ou `master`
      3. Une fois la branche selectionnée, ne touchez pas à l'option `/(root)` elle représente la racine de votre dossier
      4. Cliquez sur "Save"
      5. Une URL sera générée et devrait ressembler à ceci `utilisateur.github.io/NomDuRepository`

Votre exercice est terminé ! Bravo 😁 Il ne reste qu'à m'envoyer votre projet en message privé sur Discord, j'ai besoin du lien de votre site `utilisateur.github.io/NomDuRepository` et lien de votre repository `github.com/Utilisateur/NomDuRepository`.

J'espère que cette version vous a plu et que vous n'avez pas hésité à faire des console.log() ou cliquer sur les liens que j'ai mis à votre disposition 😊

> Created by [Lucas Ielli](https://github.com/LucasIelli)



