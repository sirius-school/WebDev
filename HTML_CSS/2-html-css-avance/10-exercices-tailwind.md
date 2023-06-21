<!-- omit in toc -->
# Exercices Tailwind

Parcourons ensemble [la documentation de Tailwind](https://tailwindcss.com/docs) pour apprendre à l'utiliser.

Malheureusement celle-ci est en anglais. N'hésite pas à utiliser Google Traduction si besoin.

Je vais te guider pas à pas.

<!-- omit in toc -->
## Table des matières

- [Mise en place](#mise-en-place)
- [Concept de base](#concept-de-base)
  - [Utility-First](#utility-first)
  - [Responsive Design](#responsive-design)
  - [Hover, Focus, & Other States](#hover-focus--other-states)
- [Première page](#première-page)
  - [Le début](#le-début)
  - [Allons plus loins](#allons-plus-loins)
  - [Un bouton](#un-bouton)
  - [Et ensuite ?](#et-ensuite-)

## Mise en place

Utilise la méthode de l'[Installation via Tailwind Play CDN](./09-theorie-tailwind.md#installation-via-tailwind-play-cdn) ou [Installation via Tailwind CLI (recommandé)](./09-theorie-tailwind.md#installation-via-tailwind-cli-recommandé) selon tes préférences

## Concept de base

### Utility-First

1. Consulte la page [utility-first](https://tailwindcss.com/docs/utility-first)

**Ce qu'il faut retenir:**

- On applique des styles directement via des classes, sans écrire de CSS
- On ne perd pas de temps à inventer des noms de classes
- Ton CSS ne grossit plus, plus besoin de dupliquer tes valeurs, tu utilise celle de Tailwind
- C'est plus sûr, quand tu agis sur ton CSS c'est global et tu peux à tout moment tout casser. Avec les classes, tout se passe sur ta page et ton élément.

[:arrow_up: Revenir au top](#table-des-matières)

### Responsive Design

1. Consulte la page [responsive design](https://tailwindcss.com/docs/responsive-design)

**Ce qu'il faut retenir:**

- Les différents breakpoints (sm, md, lg, xl et 2xl)
- Il suffit d'écrire un breakpoint suivi de 2 points et la nouvelle valeur pour appliquer un nouveau style à ton élément.
- Il faut penser son design en mobile-first
- Il est possible de customiser ses breakpoint

[:arrow_up: Revenir au top](#table-des-matières)

### Hover, Focus, & Other States

1. Consulte la page [Hover, Focus, & Other States](https://tailwindcss.com/docs/hover-focus-and-other-states)

**Ce qu'il faut retenir:**

- Un peu comme les breakpoints, il suffit d'écrire l'état voulu suivi de 2 points puis du nouveau style.
- Il est possible de cibler les éléments enfants avec `first`, `last`, `even`, `odd`,...

[:arrow_up: Revenir au top](#table-des-matières)

## Première page

Voyons maintenant un peu comment on peut commencer notre page.

Je vais décrire ici mon processus de réflexion pour créer cette page en imaginant que je n'y connais rien à Tailwind.

### Le début

1. J'aimerai commencer par mettre un block qui contiendra un titre avec un fond de couleur.
2. Je consulte la page [container](https://tailwindcss.com/docs/container)
3. Dans la page `tailwind.html` j'insère une `<div>` avec la classe `container`. J'ajoute un simple `Bienvenue`.
4. J'aimerai un fond rouge, je consulte donc la page [background-color](https://tailwindcss.com/docs/background-color)
5. J'insère alors dans ma classe de ma `<div>` le nom suivant: `bg-red-700`
6. Je me rends compte que mon container n'est pas centré, je consulte donc la page [margin](https://tailwindcss.com/docs/margin) car j'aimerai avoir des marges automatiques de chaque côté.
7. J'ajoute la classe `mx-auto` pour ajouter une Marge auto sur l'axe X (gauche et droite)
8. Ajoutons maintenant un fond à notre page. Dans la balise `<body>` j'ajoute une classe `bg-red-100`.
9. Le texte de mon container est noir et j'aimerai bien qu'il ressorte un peu plus. Je consulte la page [text-color](https://tailwindcss.com/docs/text-color)
10. J'ajoute à mon container la classe `text-white`.
11. J'aimerai que toutes les lettres soient en majuscules, je consulte la page [text-transform](https://tailwindcss.com/docs/text-transform) et j'ajoute `uppercase` à la suite de ma classe.
12. Il faudrait augmenter un peu la taille de mon texte, je consulte donc la page [font-size](https://tailwindcss.com/docs/font-size) et j'ajoute `text-4xl`.
13. Augmentons la weight de notre police en consultant [font-weight](https://tailwindcss.com/docs/font-weight) et en ajoutant `font-bold`
14. Maintenant il faudrait centrer le texte, voyons voir ce qu'on trouve sur la page [text-align](https://tailwindcss.com/docs/text-align). On peut donc utiliser `text-center`
15. Ajoutons maintenant un peu de [padding](https://tailwindcss.com/docs/padding) et margin à notre container. On va ajouter `p-5 my-5`.
16. Finissons par donner un petit côté un peu plus doux à notre container avec un [border-radius](https://tailwindcss.com/docs/border-radius): `rounded-3xl`

Voilà déjà un élément mis en place très facilement. Tu vois, c'est simple, il suffit d'allez voir la documentation et d'expérimenter.

[:arrow_up: Revenir au top](#table-des-matières)

**Ce qu'il faut retenir:**

- La documentation est bien fichue et se sert du noms des propriétés CSS qu'on connaît déjà pour nous indiquer quoi faire.
- La documentation c'est le bien absolu!

### Allons plus loins

Vous vous souvenez de notre cher ami Flexbox? Et bien il est disponible aussi avec Tailwind (encore heureux!). Voyons vite fait comment on peut mettre ça en place.

1. Commençons pas créer un nouveau container centré (voir plus haut)
2. Insérons 4 images, voici un élément déjà tout fait pour les plus paresseux:

```html
<img src="https://media.giphy.com/media/euMGM3uD3NHva/giphy.gif?cid=ecf05e478yejx0rjg6e7zg0lajpf46fcm7tgh72fj5syjkn3&rid=giphy.gif&ct=g" alt="">
```

3. On se rend compte que nos images se comporte comme prévu car notre container est toujours un block. Changeons cela en consultant la page de [flex](https://tailwindcss.com/docs/flex).
4. Ajoutons donc les classes `flex` et `flex-wrap`.
5. Ensuite on aimerait pouvoir utiliser **justify-content** pour centrer nos images. Voyons donc la page [justify-content](https://tailwindcss.com/docs/justify-content) et ajoutons `justify-center`

Ben voilà, c'est déjà finis. Simple d'utiliser Flex comme ça, non? Allez faisons maintenant un petit bouton pour le fun

### Un bouton

Histoire d'utiliser les états comme `hover`, `focus`,... 

1. Créons une `<div>` avec dedans `<button>` et le texte **click me**. Appliquons une taille, pour ce faire, je consulte donc la page [width](https://tailwindcss.com/docs/width) et [height](https://tailwindcss.com/docs/height).
2. J'ajoute les classes suivantes à mon `<button>`: `w-max` et `h-max`(pour qu'il s'adapte à la talle max du contenu).
3. J'aimerai aussi que mon bouton respire un peu, je vais donc appliquer un padding à mon bouton: `px-5` et `py-3`.
4. J'arrondis les bords: `rounded-2xl`
5. J'ajoute un fond: `bg-yellow-200`
6. Et vite fait un petit `hover:bg-yellow-400` en consultant la page [Hover, Focus, & Other States](https://tailwindcss.com/docs/hover-focus-and-other-states).

Voilà, on a notre bouton. De nouveau, c'est super simple à faire.

### Et ensuite ?

Il y a encore tellement de choses à voir sur Tailwind, mais au final, vous l'aurez compris, c'est du CSS classique. Il n'y a rien de nouveau à apprendre à part le noms des classes. Mais si vous avez compris comment ça fonctionne en CSS, il est facile de chercher dans la doc comment ça fonctionne avec Tailwind.

Il est maintenant temps d'appliquer ça sur un nouvel exercice... Si vous voulez!