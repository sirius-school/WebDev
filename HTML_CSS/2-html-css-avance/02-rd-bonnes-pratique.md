<!-- omit in toc -->
# 10 Bonnes pratiques en Responsive Design

<!-- omit in toc -->
## Table des matières
  - [1. Pensez petit... et grand](#1-pensez-petit-et-grand)
  - [2. Pensez au contexte](#2-pensez-au-contexte)
  - [3. Réduire intelligemment le contenu](#3-réduire-intelligemment-le-contenu)
  - [4. Priorisez le contenu différemment](#4-priorisez-le-contenu-différemment)
  - [5. Navigation évolutive](#5-navigation-évolutive)
  - [6. La qualité des images VS vitesse de téléchargement](#6-la-qualité-des-images-vs-vitesse-de-téléchargement)
  - [7. Utiliser des icônes](#7-utiliser-des-icônes)
  - [8. Faites attention à la taille de vos polices](#8-faites-attention-à-la-taille-de-vos-polices)
  - [9. Pensez aux méthodes de saisie](#9-pensez-aux-méthodes-de-saisie)
  - [10. Testez votre design sur des appareils actuels](#10-testez-votre-design-sur-des-appareils-actuels)
  - [Bonus](#bonus)
  - [Source](#source)

## 1. Pensez petit... et grand

On pense souvent que le responsive design ce n'est que d'afficher notre contenu sur un petit écran, mais c'est faux. Réfléchir son design en responsive c'est aussi pour les grands écrans. Même si certains site on tendance a recevoir de plus en plus de visiteurs sur smartphone, ce qui confirme le besoin d'y penser, il y a quand même toujours des visiteurs sur des écrans plus larges.

Le processus de réflexion mis en place doit bénéficier toutes les résolutions, pour ce faire on doit prioriser le contenu en fonction des écrans, il suffit de faire un petit schéma sur papier et classer les éléments par priorité. Faire le tri entre ce qui doit s'afficher obligatoirement sur mobile et ce qui n'est pas nécessaire. Faire de même pour les éléments sur grand écran. Pensez aux breakpoints intermédiaires qui ne sont pas spécialement répandu pour le moment, il se pourrait qu'ils deviennent critique dans les prochains mois avec la sortie d'un nouvel écran.

[:arrow_up:Revenir au top](#table-des-matières)

## 2. Pensez au contexte

Il est important aussi de penser au contexte dans son processus de rendre responsive son design. En effet, il ne suffit pas de réussir a placer tous les éléments sur tous les écrans mais aussi de réfléchir à où afficher ces éléments en fonctions de l'utilisation du visiteur. Imaginez le site d'un restaurant, si celui-ci est visité sur grand écran il est fort à parié que le visiteur est chez lui et qu'il cherche des infos sur comment se rendre sur place ou de quel type de plats il va pouvoir savourer. Mais si il est sur son smartphone il est peut-être déjà dans le restaurant et cherche des informations quant à la valeur nutritionnel des plats proposés. Du coup, il faut penser à rendre ces informations visibles rapidement.

[:arrow_up:Revenir au top](#table-des-matières)

## 3. Réduire intelligemment le contenu

> "En cas de doute, supprimez le. Mais faites attention à ce que vous supprimer."

Cela semble un peu agressif, mais l'approche "mobile first" c'est justement d'afficher QUE les éléments essentiels. Si vous devez penser au contenu et argumentez sur sa présence c'est que c'est un bon candidat pour la poubelle.

Ce processus de réflexion ne sera que bénéfique une fois que vous passerez sur grand écran. Moins d'informations inutiles a afficher, du coup cela sera plus facile de créer votre design.

Il faut apprendre à être sans pitié avec votre contenu pour que votre design ne soit pas trop fouillis.

[:arrow_up:Revenir au top](#table-des-matières)

## 4. Priorisez le contenu différemment

Passer de plusieurs colonnes sur grand écran à une seule colonne sur petit écran est la première chose à laquelle on pense quand on fait du responsive design. Mais ça ne s'arrête pas là. D'autre type de contenu peuvent avoir besoin d'être adapté.

Prenez comme exemple une liste d'articles sur un grand écran, chaque article aurait un titre, un aperçu du contenu, une photo, le nom de l'auteur et la date de publication. Lorsque cette liste est affichée sur un petit appareil, il est préférable de cacher la photo par exemple, pour gagner de la place.

[:arrow_up:Revenir au top](#table-des-matières)

## 5. Navigation évolutive

La navigation sur un site est sans doute la chose la plus importante pour vos visiteurs. Si elle n'est pas claire, votre utilisateur risque de quitter votre site très rapidement.

Quand vous réfléchissez à votre navigation pour les différents écran, il n'est pas pertinent de garder une navigation identique car il est fort probable que ce qui fonctionne sur grand écran ne fonctionnera pas sur un plus petit écran. Il est du coup préférable de changer complètement votre navigation pour assurez une accessibilité parfaite pour chaque type d'utilisateur.

Attention tout de même, changer votre navigation ne doit pas être synonyme de changement total de graphisme, essayez de garder vos couleurs, vos buttons, votre style,...

Un exemple, un menu déroulant qui s'affiche quand on passe notre souris au dessus ne sera pas du tout utilisable par un utilisateur sur smartphone.

[:arrow_up:Revenir au top](#table-des-matières)

## 6. La qualité des images VS vitesse de téléchargement

Une page web fait en moyenne 2.3Mo.

Le principale coupable se sont les images, et encore plus les images mal optimisées. Il faut impérativement trouver la bonne balance entre qualité et poids. Étudiez chacune de vos images et demandez-vous lesquelles sont obligatoires, supprimez celle qui ne le sont pas et réduisez la qualité des autres. Des outils comme Photoshop peuvent vous aidez à avoir un aperçu de l'optimisation de votre image.

Reconsidérez aussi l'intérêt d'un carrousel d'image en page d'accueil, ceux-ci doivent charger plusieurs images de hautes qualités et du javascript.

[:arrow_up:Revenir au top](#table-des-matières)

## 7. Utiliser des icônes

Si vous pouvez utilisez une icône à la place d'un texte explicatif, faites-le! Cela permet de prendre moins de place dans votre design. Généralement votre icône peut être en SVG et du coup est redimensionnable et vous pouvez l'animer grâce au CSS.

[:arrow_up:Revenir au top](#table-des-matières)

## 8. Faites attention à la taille de vos polices

La typographie est une partie importante de votre web design, qu'il soit responsive ou non. Il est important de s'assurer que chacun de vos choix s'affichent correctement.

- Une police avec des caractères fins peut très bien donner sur un grand écran ou même un moyen, mais sur un smartphone elle peut devenir illisible. Cela risque d'affecter la lisibilité de votre site, ce qui n'est jamais une bonne chose.
- Si vous devez utiliser une police aux caractères fins, assurez-vous qu'elle s'affiche correctement ou alors pensez à en changer quand vous êtes sur des plus petites résolutions.
- Plus une colonne de texte est large, plus l'interligne doit être important pour permettre à votre lecteur de trouver plus facilement la prochaine ligne.
- Assurez-vous d'avoir des titres (H1, H2,...) qui ressemblent à des titres, n'utilisez pas une taille trop proche de vos textes. Distinguez les!
- Vérifiez d'avoir un contraste assez élevé entre vos textes et leurs background-color. Pareil pour vos liens. Tout doit être toujours visible, si vous devez plissez les yeux pour les voir, ce n'est pas bon.

[:arrow_up:Revenir au top](#table-des-matières)

## 9. Pensez aux méthodes de saisie

Il est normal pour un utilisateur d'ordinateur d'utiliser une souris et un clavier pour naviguer sur le net, mais ce n'est pas forcément le cas pour quelqu'un qui est sur tablette ou mobile. Du coup, il faut pensez par exemple à agrandir la taille vos champs de formulaire/sélection pour permettre à l'utilisateur de cliquez sur le bon champ facilement.

[:arrow_up:Revenir au top](#table-des-matières)

## 10. Testez votre design sur des appareils actuels

Une fois que vous avez réfléchi à vos règles pour votre Responsive Design, il est de bon ton de tester leurs efficacités sur les appareils en questions. Prenez votre smartphone, votre tablette, votre ordinateur et tester les limites de votre design. Retournez votre design dans tous les sens et expérimentez un max pour trouver des défauts. Une bonne idée aussi, c'est de faire utiliser votre design par des proches avec des appareils différents.

[:arrow_up:Revenir au top](#table-des-matières)

## Bonus

**Inspirez-vous, codez et testez!**

Il n'y a pas de mal a se renseigner sur comment les plus grands sites font pour rendre leur site responsive, que ce soit au niveau de la navigation ou de la gestion du contenu.

Ensuite passez dans votre code et codez un maximum de breakpoints et de propriétés CSS. Testez constamment vos changements pour vous assurez du bon fonctionnement.

## Source

[:book:Article original](https://thenextweb.com/dd/2015/10/19/10-rules-of-best-practice-for-responsive-design/)

[:arrow_up:Revenir au top](#table-des-matières)
