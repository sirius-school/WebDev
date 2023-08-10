<!-- omit in toc -->
# Les éléments de base des formulaires en HTML

Les formulaires en HTML sont utilisés pour collecter des informations auprès des utilisateurs. Voici les éléments de base que tu peux utiliser pour créer visuellement un formulaire dans une page web. On ne va pas s'inquiéter pour le moment de rendre le formulaire fonctionnel.

<!-- omit in toc -->
## Table des matières

- [Balise `<form>`](#balise-form)
- [Balise `<input>`](#balise-input)
- [Balise `<textarea>`](#balise-textarea)
- [Balise `<select>` avec balises `<option>`](#balise-select-avec-balises-option)
- [Balise `<optgroup>`](#balise-optgroup)
- [Balise `<button>`](#balise-button)
- [Balise `<progress>`](#balise-progress)
- [Le CSS](#le-css)
- [Conclusion](#conclusion)


## Balise `<form>`

La balise `<form>` est utilisée pour définir le début et la fin d'un formulaire. C'est le conteneur principal qui entoure tous les éléments du formulaire.

```html
<form>
  <!-- Les éléments du formulaire seront placés ici -->
</form>
```


## Balise `<input>`

La balise `<input>` est l'élément le plus couramment utilisé dans les formulaires. Il permet aux utilisateurs de saisir différentes informations, telles que du texte, des mots de passe ou des nombres.

```html
<input type="text" placeholder="Saisissez votre nom" />
```

Les attributs **type** et **placeholder** définissent respectivement le type d'entrée (dans cet exemple, du texte) et un texte de substitution qui disparaît lorsque l'utilisateur commence à saisir.

Voici une liste des différents types d'input que l'on peut avoir:

| Type | Description |
|---|---|
|**[button](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/button)**| Un bouton sans comportement propre.|
|**[checkbox](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/checkbox)**| Une case à cocher qui permet de sélectionner ou désélectionner une valeur.
|**[color](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/color)**| Permet de définir une couleur.
|**[date](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/date)**| un contrôle qui permet de saisir une date complète.
|**[email](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/email)**| Un champ qui permet d'introduire une adresse email.
|**[file](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/file)**| Permet de sélectionner un fichier. Se complète avec l'attribut `accept` pour préciser quels type de fichiers sont autorisés.
|**[hidden](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/hidden)**| Permet d'envoyer son contenu sans l'afficher.
|**[image](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/image)**| Affiche une image comme bouton d'envoie (submit). Il faut préciser les attributs `src` et `alt`. `width` et `height`sont également acceptés.
|**[month](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/month)**| Permet de saisir un mois et une année.
|**[number](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/number)**| Permet de saisir un nombre.
|**[password](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/password)**| Un champ de texte en une seule ligne, qui permet d'introduire un mot de passe dont la valeur est masquée. Les attributs `maxlength`et `minlength`permettent de gérer la taille maximale et minimale.
|**[radio](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/radio)**| Définis un bouton pour sélectionner un choix parmi plusieurs |
|**[range](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/range)**| Affiche un contrôleur qui permet de sélectionner un nombre dont la valeur n'est pas importante. |
|**[reset](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/reset)**| Affiche un bouton qui permet de réinitialiser l'intégralité du formulaire. |
|**[search](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/search)**| Affiche un champ prévu pour la recherche de termes. Les sauts à la ligne sont retirés automatiquement |
|**[submit](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/submit)**| Affiche un bouton servant à l'envoi du formulaire (on lui préfère maintenant la balise `<button>`) |
|**[tel](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/tel)**| Affiche un champ pour renseigner un numéro de téléphone. |
|**[text](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/text)**| Définis un champs de texte d'une ligne. Les sauts à la ligne sont retirés automatiquement. |
|**[time](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/time)**| Permet d'indiquer une valeur de temps. |
|**[url](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/url)**| Permet d'indiquer une valeur d'url. |
|**[week](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input/week)**| Permet d'indiquer une date représenté par un numéro de semaine et une année. |

## Balise `<textarea>`

La balise `<textarea> `permet aux utilisateurs de saisir un texte plus long, comme un commentaire ou une description.

```html
<textarea placeholder="Saisissez vos commentaires"></textarea>
```

## Balise `<select>` avec balises `<option>`

La balise `<select>` crée une liste déroulante, tandis que les balises `<option>` définissent les éléments de la liste.

```htm
<select>
  <option value="option1">Option 1</option>
  <option value="option2">Option 2</option>
  <option value="option3">Option 3</option>
</select>
```

## Balise `<optgroup>`

La balise `<optgroup>` permet de créer des groupes de choix dans une liste.

```html
<select name="movies" id="movies-select">
  <optgroup label="thriller">
    <option value="Seven">Sev7n</option>
    <option value="Parasite">Parasite</option>
  </optgroup>
  <optgroup label="horreur">
    <option value="dragme">Drag Me To Hell</option>
    <option value="ring">Ringu</option>
  </optgroup>
  <optgroup label="action">
    <option value="spiderman">Spiderman: Far from home</option>
    <option value="batman">The Dark Knight</option>
  </optgroup>
</select>
```

## Balise `<button>`

La balise `<button> `est utilisée pour créer un bouton à cliquer.

```html
<button type="submit">Envoyer</button>
```

L'attribut **type="submit"** indique que ce bouton est utilisé pour soumettre le formulaire.

## Balise `<progress>`

La balise `<progress>` permet d'afficher une valeur sous forme de jauge de progression.

```html
<label for="theory">Théorie des formulaires:</label>
<progress id="file" max="100" value="90"> 90% </progress>
```

## Le CSS

Il est évidement possible de cibler tous ces éléments en CSS pour leurs donner la forme et les couleurs que vous voulez.

[Voici quelques exemples](https://freefrontend.com/css-forms/)

## Conclusion

Ces éléments de base vont te permettre de créer un formulaire visuellement sur ta page web. Pour rendre le formulaire fonctionnel, tu devra ajouter des actions et des méthodes appropriées à la balise `<form>`, ainsi que gérer les données envoyées côté serveur (ce qui n'est pas couvert dans ce cours).
