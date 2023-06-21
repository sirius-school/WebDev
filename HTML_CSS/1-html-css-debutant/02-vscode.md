<!-- omit in toc -->
# VSCode, mon amour <3

Pendant cette formation nous utiliserons VSCode comme éditeur de code! Il en existe d'autre évidement (SublimeText, ATOM, Brackets,...) mais histoire de tous commencé sur la même base, VSCode s'est avéré être le choix le plus judicieux. Si par après, lors de ta carrière professionnel, tu décides de changer pour un autre logiciel aucun soucis. Au final c'est juste un éditeur de "texte".

VSCode est un outil merveilleux avec pleins de fonctionnalités, même trop par rapport à ce que l'on a besoin, nous, pour cette formation. Sa première ouverture peut faire peur, mais ne te tracasse pas je vais t'aider à prendre tes marques sur ce logiciel.

<!-- omit in toc -->
## Table des matières

- [L'interface](#linterface)
  - [Écran d’accueil](#écran-daccueil)
  - [Dossier de confiance](#dossier-de-confiance)
  - [Dossier ouvert](#dossier-ouvert)
  - [Menu de gauche](#menu-de-gauche)
  - [Split view](#split-view)
- [Tips dans l'éditeur](#tips-dans-léditeur)
- [Extensions](#extensions)
  - [Live Server](#live-server)
  - [Auto Rename Tag](#auto-rename-tag)
  - [Bearded Icons & Theme](#bearded-icons--theme)
  - [Le reste ?](#le-reste-)
- [Raccourcis](#raccourcis)
  - [Les flèches](#les-flèches)
  - [`Alt` + flèches](#alt--flèches)
  - [`Alt` + `Shift` + flèches](#alt--shift--flèches)
  - [`Ctrl` + `Shift` + P](#ctrl--shift--p)
  - [`Alt` + curseur](#alt--curseur)
  - [`Alt` + `suppr`](#alt--suppr)
  - [`Ctrl` + `suppr`](#ctrl--suppr)
  - [`Ctrl` + `f`](#ctrl--f)
- [Emmet](#emmet)
  - [Structure HTML](#structure-html)
  - [Lorem Ipsum](#lorem-ipsum)
  - [Les listes](#les-listes)
  - [Contenu, Class et ID, multiplicateur, Attribut](#contenu-class-et-id-multiplicateur-attribut)
  - [Cheatsheet](#cheatsheet)

## L'interface

### Écran d’accueil

![vs-code-opening](img/bonus/vscode-screens/vscode-full-opening.png)

À l'ouverture, pour la première fois, VSCode affiche un écran de démarrage qui vous propose de le configurer. Vous pouvez éventuellement sélectionné votre thème. Ce qui nous intéresse ici c'est la création d'un nouveau fichier ou l'ouverture d'un dossier.

Pour tous les exercices il va falloir travailler dans un dossier, du coup cliquons sur "Nouveau dossier..."

### Dossier de confiance

![vs-code-opening](img/bonus/vscode-screens/vscode-trust.png)

Quand vous ouvrez un dossier pour la première fois il est possible que VSCode vous demande si vous pouvez avoir confiance envers les auteurs de ce dossier et de ses fichiers. Évidement, dans notre cas, on peut se faire confiance. Cet avertissement est là pour vous prévenir que si vous avez téléchargé du code en ligne et que vous n'êtes pas sûr de la source, il vaudrait mieux ne pas l'exécuter. Il est possible que du code se lance automatiquement et compromette votre ordinateur. Méfiance donc...

### Dossier ouvert

![vs-code-folder-opened](img/bonus/vscode-screens/vscode-folder-opened.png)

Une fois un dossier ouvert on se retrouve avec l'arborescence de notre dossier sur le côté gauche de la fenêtre de VSCode. De là on peut ouvrir tous les fichiers "texte" que l'on souhaite. Que ce soit de l'HTML, du CSS, du JavaScript ou tout autre langage de programmation. VSCode est aussi capable de vous afficher des images dans la plupart des formats courant (jpg, png,...).

> :white_check_mark: Essayez au plus possible d'avoir un organisation claire de vos dossiers de travail. Par exemple:

<pre>
Nom-de-projet
  |__ img
  |   |__ fb.png
  |   |__ logo.png
  |__ css
  |   |__ global.css
  |   |__ style.css
  |__ js
  |   |__ script.js
  |__ pages
  |   |__ contact.html
  |   |__ footer.html
  |   |__ header.html
  |__ index.html
</pre>

### Menu de gauche

![menu](img/bonus/vscode-screens/menu-left.png)

Vous pouvez retrouver sur le côté gauche un menu qui contient plusieurs panneaux.

![files](img/bonus/vscode-screens/menu-files.png)

- Le premier est la gestion de vos dossiers et fichiers. Vous serez amené à utiliser ce panneau constamment pour passer d'un fichier à un autre.

![search](img/bonus/vscode-screens/menu-search.png)

- Le deuxième est l'outil de recherche global. Il permet de chercher dans tous les fichiers de votre dossier actif. Il est également possible de remplacer toutes les occurrences d'un mot dans vos fichiers. Très pratique!

![plugins](img/bonus/vscode-screens/menu-plugins.png)

- Le cinquième est le panneau qui permet de gérer les extensions installées et d'en trouver des autres. Voyons ça un peu plus loin.

Les autres menus servent notamment à gérer le `versioning` de votre projet ou de lancer des tests pour debugger votre code. Mais nous ne les utiliserons pas.

### Split view

Une fonctionnalité fort appréciable sur VScode surtout lorsque vous n'avez qu'un écran, c'est la possibilité de `split`/séparer les différentes vues. Pour ce faire il suffit d'avoir plusieurs onglets de fichiers ouvert. Ensuite cliquer et glisser un onglet dans un des coins/bords de la fenêtre de VScode pour voir apparaître en transparence l'espace que va prendre le nouvel onglet.

![split-view](img/bonus/vscode-screens/vscode-split.png)
![splitted-view](img/bonus/vscode-screens/vscode-splitted.png)

## Tips dans l'éditeur

Voici quelques astuces quand tu utilises VSCode. Pour le moment, comme c'est le début ça ne te dit pas encore grand chose. Mais n'hésite pas à revenir les lires quand tu auras commencés tes premières pages.

- Comme dans n'importe quel éditeur de texte, si y a du code souligné, c'est que c'est pas bon! Fait bien attention à ce que VSCode t'indique. Si tu vois un soulignement en vague en dessous d'une de tes balises, c'est probablement qu'il y a un soucis. Relis le code qui précède et regarde si il n'y a pas un soucis de balise non-fermée, un point-virgule manquant ou une faute de frappe.
- Les couleurs sont importantes! Quand tu écris du code les **balises** sont dans une couleur, les **attributs** ont une couleur différente, les **valeurs** ont une autre couleur. Si tu écris un élément de code et qu'il ne prend pas la même couleur, c'est probablement que VSCode ne comprend pas ton code correctement. Relis le code qui précède et regarde si il n'y a pas un soucis de balise non-fermée, un point-virgule manquant ou une faute de frappe.
- Quand tu sélectionnes une balise, sa jumelle est sélectionnée également. Cela te permet de savoir si elle est bien fermée ou non.
- L'indentation automatique te permet également de savoir si tu es dans la bonne balise ou non. Si lorsque tu va à la ligne l'indentation ne te semble pas correcte, c'est probablement que ton code est mal interprété et qu'il y a un soucis quelque part. Jette un coup d'oeil aux balises précédentes pour voir ce qu'il se passe.

## Extensions

Vous pouvez personnaliser votre expérience avec VSCode au fur et à mesure de votre apprentissage et de votre carrière grâce aux extensions. Ces petits bout de code qui vont venir vous filer un coup de main pour écrire votre code ou modifier le comportement de VSCode.

### Live Server

Live Server permet de simuler un serveur sur votre machine pour voir comment se comporte votre site. Alors dans cette section on ne va pas l'utiliser pleinement. Cependant il a une utilité très intéressant, c'est la prévisualisation et le "refresh live". C'est à dire qu'à chaque fois que vous enregistrez votre page, votre aperçu se met à jour sans que vous deviez rafraîchir votre page.

Pour utiliser Live Server, il suffit d'ouvrir non pas un fichier avec VSCode, mais un dossier. Vous retrouverez dans la barre latéral l'onglet avec vos fichiers, si vous cliquez droit dessus vous aurez l'option `Open with Live Server`

![live-server](img/bonus/live-server.png)

[:floppy_disk: Installer Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)

### Auto Rename Tag

Une petite extension qui va vous faciliter la vie. Celle-ci va, comme son nom l'indique, renommer la balise correspondante à celle que vous venez de modifier. Pratique!

[:floppy_disk: Installer Auto Rename Tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)

### Bearded Icons & Theme

![bearded-icons](https://beardedbear.gallerycdn.vsassets.io/extensions/beardedbear/beardedicons/1.1.0/1663776059876/Microsoft.VisualStudio.Services.Icons.Default)
![bearded-theme](https://beardedbear.gallerycdn.vsassets.io/extensions/beardedbear/beardedtheme/7.4.0/1663525046452/Microsoft.VisualStudio.Services.Icons.Default)

Une petite extension visuelle pour changer les icônes et l'apparence de vos fichiers et dossier dans l'explorateur de fichiers ainsi que le style complet de l'éditeur.

[:floppy_disk: Installer Bearded Icons](https://marketplace.visualstudio.com/items?itemName=BeardedBear.beardedicons)

[:floppy_disk: Installer Bearded Theme](https://marketplace.visualstudio.com/items?itemName=BeardedBear.beardedtheme)

### Le reste ?  

Il y a évidement des centaines, des milliers d'extensions. Vous pouvez par exemple installer des extensions qui gère la mise en forme du code (Prettier) ou des aides pour écrire votre code JavaScript, Python, C++,...

> :exclamation: Ne pas installer **trop** d'extensions au risque parfois d'avoir des incompatibilités. N'installer que ce dont vous avez besoin.

[:arrow_up: Revenir au top](#table-des-matières)

## Raccourcis

### Les flèches

Ce n'est pas un raccourcis lié à VSCode, mais il est très important d'apprendre à naviguer dans son code à l'aide des flèches. Normalement on garde ses deux mains sur le clavier et ainsi on a plus facile à rectifier du code en utilisant les fmèches.

### `Alt` + flèches

L'utilisation de `alt` est super importante quand vous coder dans VSCode. Le fait de maintenir `alt` et d'ensuite utiliser les flèches haut et bas de votre clavier permet de déplacer une ligne de code. Bien plus pratique que d'utiliser un copier/coller.

### `Alt` + `Shift` + flèches

Ce raccourci permet de dupliquer la ligne sur laquelle se trouve votre curseur actuellement ou la sélection.

### `Ctrl` + `Shift` + P

Ce raccourci permet de faire apparaître la palette de VSCode. Dedans vous pouvez y retrouver différents raccourcis comme celui des préférences ou de vos extensions. Cela est possible tant que `>`se situe devant votre recherche, mais si vous l'effacez vous pouvez aussi rechercher des fichiers!

### `Alt` + curseur

Ce raccourci permet de placer de multiple curseur dans votre document.

### `Alt` + `suppr`

Ce raccourci permet de supprimer mot par mot.

### `Ctrl` + `suppr`

Ce raccourci permet de supprimer toute la ligne où est votre curseur.

### `Ctrl` + `f`

Ce raccourci permet d'afficher la recherche dans le document en cours.

## Emmet

Il s'agit d'un petit plugin directement intégré à VSCode qui permet de taper du code HTML et CSS beaucoup plus rapidement. Alors, ça demande un petit temps d'apprentissage aussi pour l'utiliser, mais ça simplifie grandement la vie.

Pour pouvoir l'utiliser correctement il faut bien être dans un document HTML ou CSS. Donc pense bien à enregistrer ton fichier dans le bon format.

Ensuite dès qu'on rentre le nom d'une balise on a déjà Emmet qui te propose de créer les deux balises directement, plus besoin de le faire toi même. Il suffit d'appuyer sur `enter`.

Voici quelques exemples:

### Structure HTML

En écrivant juste `!` et en validant avec `enter` tu peux directement créer ton squelette HTML de base.

> :exclamation: Lors d'une mise à jour de VScode il est possible que cette dernière fonctionnalité ai changée. Il faut désormais activer `Emmet: Use Inline Completions` qui est un paramètre à  dans VSCode. Ainsi, lorsque tu écriras du code Emmet, VScode te montrera directement le résultat et il faudra valider avec `Tab`.

![vscode-emmet-inline](./img/03/vscode-emmet-inline.png)

### Lorem Ipsum

Le lorem ipsum est un texte fictif en latin qui est devenu la référence du texte de substitution. C'est à dire un texte que l'on utilise pour remplir nos `<div>`et `<p>`dans le but de pouvoir commencer rapidement à styliser notre page, sans devoir attendre le contenu complet.

Pour l'utiliser il suffit d'écrire `lorem`et de valider avec `enter`. Cela va créer un paragraphe de Lorem Ipsum. Si tu veux plusieurs paragraphes tu peux utiliser la commande suivante `lorem*2`qui du coup te créera 2 paragraphe.

### Les listes

Il est également possible de créer des listes plus rapidement, pour ce faire tu n'a qu'a écrire le type de liste que tu veux (`ul`ou `ol`).

Mais ça va plus loin que ça, il y a moyen de directement écrire le nombre de `li` dont tu as besoin dans ta liste: `ul>li*5`. Ceci va créer une liste avec 5 `<li>`. C'est à ça que sert `>`,c'est pour indiquer la descendance.

Et on peut encore pousser le vice plus loin en demandant directement de nous créer une liste et son contenu: `ul>li{lien $}*5`. Ce qui est entre accolades ici c'est le contenu de ma balise `<li>`.

### Contenu, Class et ID, multiplicateur, Attribut

Comme vu plus haut il y a donc moyen de préciser à Emmet le contenu de notre balise en utilisant les `{}`. Il est également possible de lui demander de compter pour nous le nombre d'élément qu'il crée en utilisant `$`, cela va ajouter un chiffre pour chaque fois qu'il doit répéter l'opération avec `*x`

C'est possible de donner la valeur d'un attribut également en utilisant `[]`. Il suffit d'écrire le nom de l'attribut de notre balise comme dans cet exemple: `a[href="#"]`

Il est également possible de préciser la classe ou l'id de notre élément directement: `div.ma-classe` ou `div#monID`

Du coup on peut combiner le tout: `(div.ma-classe#monID$>p>lorem)*5`. Ici ce qui est en parenthèse va être répéter 5 fois. On a un div avec une classe, un id unique et une balise `<p>` à l'intérieur contenant chacun un paragraphe de Lorem, le tout qui se répète 5 fois. Très pratique!

### Cheatsheet

Bref, vous l'aurez compris, Emmet c'est top quand on apprend à l'utiliser. Alors c'est à vous de faire la démarche, ici je n'ai montré que quelques exemples, mais il y a encore tellement plus.

Voici [un lien vers une cheatsheet](https://docs.emmet.io/cheat-sheet/) et un autre vers [la documentation](https://docs.emmet.io/)

[:arrow_up: Revenir au top](#table-des-matières)

[:rewind: Retour au sommaire du cours](./README.md#table-des-matières)
