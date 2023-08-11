<!-- omit in toc -->
# Exercices supplémentaires

Alors comme ça on avance plus vite que les autres? Tu voulais en profiter pour te reposer? La bonne blague! Voici une liste d'exercices supplémentaires. Ceux-ci sont dans leurs ordre de création mais aurons un indicateur de difficulté ainsi qu'un récapitulatif des sujets dont tu auras besoin pour t'en sortir.

Des nouveaux exercices pourront apparaître par moment, je te préviendrai évidement.

:exclamation: Disclaimer: Les énoncés des exercices ne sont pas ultra-détaillés. Oui j'ai la flemme.. ah non pardon, j'veux dire, qu'il est temps de voler de tes propres ailes. Respectes les consignes, mais lâche toi aussi. C'est le moment d'expérimenter. Si tu veux faire plus, fais-le! Pense au contexte dans lequel l'exercice pourrait exister et rajoute toi même des éléments pour que ça ai l'air plus vrai que nature!

Il va falloir aussi faire des recherches sur Google pour résoudre certains exercices car je te demande parfois d'utiliser des propriétés CSS qu'on a pas (encore?) vues. Mais rassure-toi, c'est tout a fait jouable!

![google-that-shit](https://media.giphy.com/media/J5q4qtKqQ4plPl4YJN/giphy.gif)

![good-luck](https://media.giphy.com/media/mqWZoUiub0cyA/giphy.gif)

<!-- omit in toc -->
## Légende des difficultés

Facile: 😄
Modéré: 😊
Exigeant: 😅
Épineux: 😰
Impossible?: 😡

<!-- omit in toc -->
## Table des matières

- [😄 Exercise 1: Styling Headings](#-exercise-1-styling-headings)
- [😊 Exercise 2: Creating Navigation Menu](#-exercise-2-creating-navigation-menu)
- [😄 Exercise 3: Styling Links](#-exercise-3-styling-links)
- [😅 Exercice 4: Styling Card](#-exercice-4-styling-card)
- [😅 Exercice 5: Styling Lists](#-exercice-5-styling-lists)
- [😰 Exercice 6: Simple Flex Gallery](#-exercice-6-simple-flex-gallery)

## 😄 Exercise 1: Styling Headings

>Sujets: html, css, sélecteurs, pseudo-sélecteur, headings

Crée un document HTML avec de multiple **headings** (h1, h2, h3,...) et quelques paragraphes pour remplir. Ensuite écris les règles CSS pour respecter les consignes suivantes:

1. Sélectionne tous les `h2` et change leurs couleurs d'écriture
2. Sélectionne le `h1` et donne lui un style différent en augmentant sa taille et sa police d'écriture
3. Sélectionne les `h3` impaire et ajoute leurs un fond de couleur au choix.

[:arrow_up: Retour à l'index des exercices](bonus-exos-supp.md#table-des-matières)

## 😊 Exercise 2: Creating Navigation Menu

>Sujets: html, css, sélecteurs, pseudo-sélecteur, lists

Crée un document HTML avec une navigation en liste non-ordonnée (ul, li) pour un site de vente. Chaque élément de la liste devra être un lien dont voici les titres: `Home`, `Shop`, `Team`, `Contact`, `My Account`. Ensuite respecte les consignes suivantes:

1. Sélectionne les différents liens et fais en sorte qu'ils soient sur la même ligne (rappel toi la première [maquette Discord](09-exercice-css-maquette-discord.md))!
2. Sélectionne tous les liens et ajoute leurs une bordure en bas uniquement. La couleur est de ton choix.
3. Fais en sorte que quand on passe par dessus les liens avec notre souris, le lien change de couleur de fond.
4. Fais en sorte que le dernier élément de la navigation soit d'une couleur d'écriture différente et aussi qu'il soit une sorte de bouton aux bords arrondis.

[:arrow_up: Retour à l'index des exercices](bonus-exos-supp.md#table-des-matières)

## 😄 Exercise 3: Styling Links

>Sujets: html, css, sélecteurs, pseudo-sélecteur, links

Crée un document HTML avec quelques liens. Ensuite respecte les consignes suivantes:

1. Ajoute une classe `attention` à certains liens. Sélectionne-les en CSS et change leurs couleurs d'écriture.
2. Fais en sorte que quand on passe par dessus les liens ceux-ci sont soulignés. Ce qui donc veut dire que par défaut ils ne doivent pas l'être.
3. Sélectionne les liens `visités` et fais en sorte que leurs couleurs soient différentes et qu'ils soient encadré par un border rouge (il faut que la border existe sur les liens *avant* de changer son style pour les liens visités).

[:arrow_up: Retour à l'index des exercices](bonus-exos-supp.md#table-des-matières)

## 😅 Exercice 4: Styling Card

>Sujets: html, css, sélecteurs, box-shadow

Crée un document HTML et construit une carte. C'est à dire un élément HTML qui contiendra une `image`, en dessous de laquelle tu auras un `titre` et un `sous-titre`. L'élément doit avoir une largeur fixe plutôt petite, genre 300px.

Si tu ne vois pas ce dont je parle: [How To - Cards - W3School](https://www.w3schools.com/howto/howto_css_cards.asp)

Voici quelques consignes à respecter:

1. Fais en sorte que l'image qu'on insère soit toujours **carré** et **non-déformée**.
2. Cherche sur le net comment faire un `box-shadow` sur ta carte entière. Soit subtile dans ton effet.
3. Utilise un pseudo-sélecteur pour changer le style du titre.
4. Utilise le bon pseudo-sélecteur pour changer l'effet de `box-shadow` lorsqu'on survole (hover) la carte.

## 😅 Exercice 5: Styling Lists

>Sujets: html, css, sélecteurs, marker

Crée un document HTML et fais une liste non-ordonnée d'au moins 10 éléments. Ensuite réalise les consignes suivantes:

1. Enlève les bullets points des éléments de ta liste.
2. Rajoute un émoji différents à tes 10 éléments grâce au pseudo-sélecteurs: `::marker`. Oui, va falloir allez chercher sur le net!
3. Pour le fun, fais en sorte que la couleur du texte soit différente pour les éléments pair et impaire.

## 😰 Exercice 6: Simple Flex Gallery

>Sujets: html, css, sélecteurs, flexbox, transform, transition, (position), (attribut)

Alors celui-ci c'est le bonus! Prends ton temps pour relever le défi car il est probable qu'on ai pas encore vu toute la matière pour! Mais c'est le moment idéal pour faire valoir tes talents de chercheur Google!

Crée une galerie d'images. Pour ce faire tu vas devoir placer plusieurs images à l'intérieur d'un container. Ce dernier devra utiliser `flexbox` pour agencer correctement tes images. Voici quelques instructions supplémentaires:

1. Fais en sortes que toutes les images aient la même taille et ne soient pas déformées.
2. Ajoute leurs un petit bord tout discret **ou** un `box-shadow`.
3. Quand on passe sur l'image avec la souris, celle-ci doit s'agrandir légèrement. Utilise la propriété `transform` et si tu veux être encore plus pro ajoute `transition`. 

J'insiste sur ce point: FAIS UNE RECHERCHE GOOGLE!!

<!-- omit in toc -->
### 😡 Encore un peu plus loin

Alors je te préviens, ici ça va être chaud patate comme on dit chez nous!

![welcome-to-hell](https://media.giphy.com/media/mDFpdL1UxdVZRBN2V4/giphy.gif)

1. Ajoute une légende à chaque image en utilisant un attribut personnalisé!
2. Grâce au pseudo-sélecteur, ajoute la valeur de ton attribut avant ou après ton image.
3. Positionne ensuite ce nouvel élément grâce aux positions.

Oui c'est compliqué, mais si tu fais les bonnes recherches tu trouveras facilement!

---

C'est tout pour le moment, mais ne te tracasse pas, j'en ai encore une bonne dizaine en préparation!
