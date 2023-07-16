<!-- omit in toc -->
# Bonnes pratiques

Voici quelques explications sur des bonnes pratiques. Si tu penses à autre chose que j'ai dit et qui n'est pas présent dans ce fichier, n'hésites pas à me le signaler.

<!-- omit in toc -->
## Table des matières

- [Positionnement](#positionnement)
- [Les classes](#les-classes)
- [HTML](#html)
- [CSS](#css)

## Positionnement

Ne pas positionner des éléments avec des margins/padding et des valeurs en pixels élevés. PRéféré utiliser le positionnement naturel des `blocks`, de `float` ou utiliser `flex`

## Les classes

- Utiliser les classes que lorsque c'est nécessaire. C'est à dire quand on ne sait pas sélectionner un élément autrement ou sans risquer d'en sélectionner un autre non-voulu.
- Utiliser des noms qui ont du sens, qui décrivent ce à quoi elles correspondent ou ce qu'elle font (utility-class)! (ex: container, galerie, bg-white,~~firstDiv~~,......)
- Pas de chiffre en premier, voir dans toute la classe! ex: ~~1container~~
- Pas de noms à rallonge non plus. Il faut rester claire!

## HTML
<!-- omit in toc -->
### Petit à petit l'oiseau...

Lorsque tu dois écrire ton HTML, commence par mettre tout le contenu sans aucune `classes` ou `id`. Penses aux balises sémantiques (section, main, header, footer, nav,...) pour structurer au mieux ta page. Tu viendras placer des balises qu'au dernier moment quand tu en as vraiment besoin dans ton CSS pour cibler l'élément.

<!-- omit in toc -->
### Div-hell

Éviter les "div-hell", voir l'exemple en dessous et sa correction.

```html
<div>
  <div>
    <h1>Coucou</h1>
  </div>
  <div class="container">
    <div>
      <img src="" alt="">
    </div>
    <div>
      <div>
        <h2>Titre</h2>
      </div>
      <div>
        <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Corrupti, officia.</p>
      </div>
    </div>
  </div>
</div>
```

```html
<section>
  <h1>Coucou</h1>
  <div class="container">
    <img src="" alt="">
    <div>
      <h2>Titre</h2>
      <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Corrupti, officia.</p>
    </div>
  </div>
</section>
```

> :bulb: N'oubliez pas que la plupart des éléments sont déjà des `block` et donc se comportent déjà très bien tout seul sans devoir être compris dans une `div`.

## CSS
<!-- omit in toc -->
### Regrouper ses propriétés identiques dans un même sélecteur

```css
.container-gallery{
  width: 80%;
  background: grey;
  display: flex;
  margin: 0 auto;
}

.container-contact{
  width: 90%;
  background: grey;
  display: flex;
  margin: 0 auto;
}
```

L'exemple ci-dessus peut devenir ceci:

```css
.container-gallery, .container-contact{
  background: grey;
  display: flex;
  margin: 0 auto;
}

.container-gallery{width: 80%;}
.container-contact{width: 90%;}
```

> :bulb: Cela permet une lecture plus simple de nos sélecteurs et de leurs propriétés.
<!-- omit in toc -->
### Attention à la spécificité des sélecteurs

Lorsque tu crée tes sélecteurs essaye de ne pas être trop précis non plus. Si ton sélecteur fait plus de 3 éléments et que ce n'est pas possible de faire autrement, c'est probablement qu'il y a un soucis dans ton HTML.

```css
body > header > nav > ul > li {
  /* code css */
}
```

> :bulb: ici on est trop spécifique, on passe par trop de 'chemins' pour accéder à nos `li`. Si le code change d'un coup, genre la nav qui doit quitter le `header`, ce genre de sélecteur pourrait poser problème et il faudrait le refaire.

```css
nav li{
  /* code css */
}
```

> :bulb: On lui préférera ce genre de code, bien plus propre et plus global. Il y a moins de chance qu'il casse.
