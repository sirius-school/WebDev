<!-- omit in toc -->
# Comprendre le WEB, l'HTML et le CSS

<!-- omit in toc -->
## Table des matières

- [Comment fonctionne le web](#comment-fonctionne-le-web)
- [Quelle est la différence entre un site statique et un site dynamique ?](#quelle-est-la-différence-entre-un-site-statique-et-un-site-dynamique-)
  - [Site statique](#site-statique)
  - [Site dynamique](#site-dynamique)
- [Qu'est ce que le HTML ?](#quest-ce-que-le-html-)
- [Qu'est ce que le CSS ?](#quest-ce-que-le-css-)
- [MDN et autres ressources](#mdn-et-autres-ressources)

## Comment fonctionne le web

En anglais, WEB (aussi appelé World Wide Web) signifie "la Toile", on peut l'imaginer telle une toile d'araignée tissée reliant tous ses utilisateurs par delà les frontières physiques, de langues et de distances.

Ce réseau inventé entre 1989 et 1990 a permis de donner accès à la connaissance et au partage à travers le monde et fait aujourd'hui partie intégrante de notre quotidien.

Imaginez vous une journée sans accès à votre réseau social favoris? Que feriez vous sans Wikipédia ?

Le Web a permis de créer des liens entre les populations, et de rendre l'information disponible à tous. Actualité, livres, vidéos, musique, jeux...

Mais savez vous à qui vous devez cette merveilleuse invention?

Tim Berners-Lee ainsi que Robert Cailliau ont inventé ce merveilleux outils. Ce dernier est un ingénieur Liégeois, plutôt cool n'est ce pas? Le web est à moitié belge! #proud

## Quelle est la différence entre un site statique et un site dynamique ?

### Site statique

Contrairement aux idées reçues un site statique n'est pas un site dépourvu d'animations.

Lorsque nous parlons de site statique nous parlons de "pages statiques" visibles telles qu'elles ont été conçues et ne pouvant recevoir de modification extérieur.

Pour être modifiées ces informations doivent d'abord repasser dans les mains du développeur pour ensuite être codées, uploadées et déployées.

Si non, elles resteront toujours identiques à ce qui a été développé à sa création.

Un site statique ne permet aucune interaction avec l'utilisateur et donc aucune modification ou ajout de données de sa part.

### Site dynamique

Contrairement au site statique, un site dynamique peut être modifié par son utilisateur.

Prenons comme exemple facebook, vous pouvez ajouter des publications, likez celles de vos amis, changer de photo de profil, etc.

Dans le panel des sites ou application dynamiques nous pouvons retrouver: réseaux sociaux, blogs, plateforme de téléchargements ou de streaming telles que Netflix, application de gestion de temps (To-do liste), etc...

Pour ce faire l'utilisateur va devoir envoyer une requête au serveur, ces requêtes peuvent uploader un nouveau contenu, récupérer un contenu, le modifier, ou le supprimer. Le serveur traite la demande et effectue l'opération pour ensuite recevoir une réponse contenant le contenu demandé, modifié, ajouté, ou supprimé.

## Qu'est ce que le HTML ?

HTML est l'acronyme de HyperText Markup Language.
Le HTML n'est pas un langage de programmation à proprement parlé comme on peut le dire du Javascript ou du PHP.
Il s'agit d'un "langage de balisage", il est directement interprété par le navigateur, c'est à dire qu'il n'a besoin d'aucune traduction pour que le navigateur puisse rendre le contenu visible sur votre ordinateur / tablette / GSM.

Par langage de balisage on entend qu'il utilise des balises pour indiquez au navigateur le type de contenu auquel il a à faire (ex: `<p>` `<h1>` `<h2>`  ). Elles indiquent l'endroit de la page où votre contenu doit être inséré, comme un coup de marqueur sur une carte.

C'est le squelette de votre page web, comme vos os soutiennent votre corps et ses différents tissus, le HTML soutient le contenu de votre page, permet de le styliser, de l'animer, de le rendre dynamique.

[:arrow_up: Revenir au top](#table-des-matières)

## Qu'est ce que le CSS ?

Le CSS ou Cascading Style Sheets (feuilles de style en cascade), permet la mise en forme de votre squelette, c'est la partie émergée de l'iceberg, celle que vous pouvez voir quand vous consulter vos pages web.

Couleurs, polices, formes, tailles, mise en page, animations, tout ce qui rend "joli" (ou non) le squelette de votre page web ainsi que son contenu.
Attaché à votre HTML il vous permettra de reproduire une maquette de site.

Voici un exemple de syntaxe CSS que vous pourriez retrouver dans votre code:

```css
h1 {
    font-size: 2rem;
    color: white;
    background-color: black;
}
```

[:arrow_up: Revenir au top](#table-des-matières)

## MDN et autres ressources

[La documentation Firefox](https://developer.mozilla.org/fr/) créée par des développeurs pour les développeurs. Il s'agit de votre nouveau livre de chevet, vous trouverez toutes les informations nécessaires à la réalisation de votre première page web dont le listing des balises HTML et propriétés CSS ainsi qu'un espace pour tester votre code.

Voici les deux ressources qui vous serons indispensables à la réalisation de vos futures exercices, épluchez-les, testez, découvrez, faites vous la main:

- [Référencement des éléments(ou balises) HTML](https://developer.mozilla.org/fr/docs/Web/HTML/Element)
- La documentation MDN pour le CSS étant un peu plus avancée, je vous recommande la [W3school](https://www.w3schools.com/css/default.asp )

Il y a également des resources dans [La boîte à outils de l'intégrateur junior!](bonus-outils.md)

[:arrow_up: Revenir au top](#table-des-matières)

[:rewind: Retour au sommaire du cours](./README.md#table-des-matières)

> Cours original: Julie Vanderbyse
>
> Modification: Jeremy Scala
