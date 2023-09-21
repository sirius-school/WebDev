<!-- omit in toc -->
# Exercices Animations

Voici quelques exercices pour un peu manipuler les media queries. Vous pouvez juste lire l'énoncé et regardé le gif (quand il y en a un) pour essayer de reproduire l'effet. Je fournis également un pas à pas en guise de guide, mais il n'est pas forcément complet.

<!-- omit in toc -->
## :memo: Objectifs

- Apprendre à manipuler les media queries
- Suivre des consignes précises.
- Apprendre à se débrouiller en allant lire la théorie vue ou la documentation.

<!-- omit in toc -->
## :white_check_mark: Evaluations

- Respect des consignes.
- La syntaxe est correcte.
- L'indentation est correcte.

<!-- omit in toc -->
## Légende des difficultés

Facile: 😄
Modéré: 😊
Exigeant: 😅
Épineux: 😰
Impossible?: 😡

<!-- omit in toc -->
## Table des matières

- [😄 Media Query de Base](#-media-query-de-base)
- [😊 Affichage de Blocs](#-affichage-de-blocs)
- [😅 Menu de Navigation Réactif](#-menu-de-navigation-réactif)
- [Images Réactives](#images-réactives)

## 😄 Media Query de Base

>Sujets: Media Query

Crée une page HTML avec un paragraphe de texte. Utilise une media query pour rendre le texte plus grand lorsque la largeur de l'écran est inférieure à 600 pixels.

![text](img/02/01-text.gif)

1. Utilise `lorem` pour mettre du texte rapidement dans ton `<p></p>`
2. Ajoute ton CSS et met une taille de `2rem` à ton paragraphe.
3. Ajoute ta `media query` pour les `screen` et avec une largeur max de 600px
4. Ajoute dans ta MQ une règle CSS pour que la taille de ton `p` augmente à `3rem`

## 😊 Affichage de Blocs

>Sujets: Media Query, Flexbox

Crée trois blocs de couleur sur une page. Utilise des media queries pour changer leurs hauteurs et couleurs à différents points de rupture d'écran.

![blocks](img/02/02-blocks.gif)

1. Ajoute une balise `<main></main>`
2. Ajoute 3 `div` à l'intérieur de `<main></main>`.
3. Fais en sorte que les `div` aient une taille et qu'elles s'affichent l'une à côté de l'autre.
4. Chaque `div` doit avoir une couleur spécifique (pseudo-sélecteur ou classe.. au choix... mais fais le bon! 😈)
5. Ajoute les MQ pour les écrans et pour une largeur minimum de 600, 800 et 1000px.
6. Change les propriétés des blocs pour chaque MQ. Tu n'est pas obligé de respecter exactement les tailles et couleurs qu'il y a sur le gif tant que le résultat des MQ est bien là.

## 😅 Menu de Navigation Réactif

Conçois un menu de navigation horizontal simple avec des liens. Utilise des media queries pour transformer le menu en une version verticale lorsqu'il est affiché sur un écran plus étroit.

![blocks](img/02/03-menu.gif)

1. Crée ton menu en HTML. Place le dans un `header`. Tu peux utiliser cette commande Emmet pour générer 5 liens rapidement: `li[href="#"]{Lien $}*5`
2. Pas besoin de recopier le style du gif, amuse toi!
3. Il va falloir faire en sorte que notre `ul` soit en `flex`, autorisé le `wrap` et centrer le tout à l'intérieur du `header`. N'oublie pas aussi d'enlever le style de la liste.
4. Ensuite tu peux styliser les `li` à ta guise.
5. Préparons notre MQ comme d'hab, cette fois on va mettre une `max-width:768px`.
6. Dans notre MQ on veut changer la direction de notre `ul` et la largeur de nos `li`
7. On peut également cibler certains de nos éléments pour changer leurs styles (voir gif)

## Images Réactives 

*prochainement...*