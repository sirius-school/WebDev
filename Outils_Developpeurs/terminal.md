<!-- omit in toc -->
# Le Terminal

<!-- omit in toc -->
## Tables des matières
- [A quoi cela sert ?](#a-quoi-cela-sert-)
- [Installation](#installation)
- [Les commandes](#les-commandes)
- [Exercices](#exercices)


# A quoi cela sert ?

Aujourd'hui Windows est pourvu d'une interface graphique qui est facile et intuitive mais ça n'a pas toujours été le cas. Pour les moins jeunes, vous vous souviendrez peut-être de l'image ci-dessous. Oui, au début les ordinateurs avait une interface qui n'était composé que de lignes de texte parfois incompréhensible. C'était la seule manière d'afficher ce qui était contenu dans un ordinateur, évidemment le contenu n'était autre que des données, des fichiers et des dossiers. Aujourd'hui le terminal est indispensable pour les utilisateurs de Linux mais Windows aurait pu s'en passer **cependant** les informaticiens et nous les développeurs avons toujours besoin de certaines fonctionnalités que nous aurons l'occasion d'aborder dans peu de temps. Fun fact : parmi les développeurs aguéris (surtout sur Linux) l'utilisation de la souris est quasiment proscrite et donc le terminal devient la seule manière de naviguer et de manipuler les données.

<img src='./src/Images/oldComputerTerminal.png' width='128px'/>

# Installation

Dans un premier temps nous allons vérifier que vos ordinateurs possèdent bien la bonne version du terminal Windows PowerShell, en effet si votre ordinateur est sur Windows 10 vous risquez d'avoir les yeux qui piquent un peu.

Pour ouvrir votre terminal vous avez deux options :
- Via votre barre de recherche en tapant ``Windows Powershell``<br>
![](./src/Images/windowsPowerShellSearch.png) 
- Via le menu démarrer en cliquant droit ou en utilisant le raccourci ``Win+X`` (en admin = moins de problèmes)<br>
![](./src/Images/windowsRightClick.png)

Si vous êtes sur Windows 10 il y a de grandes chances que vous tombiez sur ceci :<br>
![](./src/Images/windowsPowerShell5.png)
> Je vous avais dit que ça piquerait 😂

En réalité c'est simplement que Windows 10 n'embarque pas la nouvelle version du PowerShell. Nous allons donc remedier à cela :

1. [Ce lien vers la documentation Microsoft](https://learn.microsoft.com/fr-fr/powershell/scripting/whats-new/migrating-from-windows-powershell-51-to-powershell-7?view=powershell-7.3) nous explique comment migrer de la version Windows Powershell 5.1 vers la 7.x. Nous y trouvons une information **importante** : ``PowerShell 7 fonctionne côte à côte avec Windows PowerShell``. En d'autres termes le terminal présent sur votre machine Windows 10 gardera de toute façon la version 5.1 du PowerShell et la nouvelle version aussi.

2. [Ce lien d'installation](https://learn.microsoft.com/fr-fr/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.3#winget) nous donne deux commandes : 
   - ``winget search Microsoft.PowerShell`` qui vérifie quelle est la version en cours.
   - ``winget install --id Microsoft.Powershell --source winget`` qui installera la version 7.x.

Maintenant que l'installation est finie vous devriez obtenir ceci :<br>
![](src/Images/windowsPowerShell7.png)
> C'est quand même un peu mieux 😜

# Les commandes

Étant donné que nous allons utiliser le terminal pour la gestion de fichiers, nous verrons uniquement les commandes associées :<br>

> ***Astuce : faire ``tab`` dans le terminal vous permet d'avoir l'auto-complétion !***<br>

| Commande | Description | 
| :---: | :---- |
| gci, dir, ls | Liste les fichiers/dossiers du répertoire. Exemple : ``ls`` ou ``ls .\Sirius\`` | 
| gc, type, cat | Obtenir le contenu d'un **fichier**. Exemple : ``cat .\fichier.txt``  |
| help, man | Aide. |
| cls, clear | Efface l'écran. |
| cpi, copy, cp | Copier un ou plusieurs fichiers/l'arborescence complète. Exemple : ``cp D:\Sirius\WebDev\fichier.txt C:\Autres`` |
| mi, move, mv | Déplacer un fichier/répertoire. Exemple : ``mv .\fichier.txt .\Sirius\`` |
| del, rmdir, rd, rm | Suppression de fichier/répertoire. Exemple : ``rm .\fichier.txt``|
| start | Ouvrir un fichier dans un autre programme. Pas obligatoire vous pouvez simplement mettre le nom du fichier. |
| ni, New-Item | Créer un nouveau fichier, il faut spécifier son extenstion. Exemple : ``ni fichier.txt``. Attention uniquement sur PowerShell. |
| ren, mv | Renommer un fichier/répertoire. |
| cd, chdir | **L'une des commandes les plus importante**. Changer de répertoire courant. Exemple : ``cd .\Sirius``, ``cd .\Sirius\Autres\``, ``cd..`` ce dernier vous permettra de revenir en arrière un fois. ``cd ..\..`` celui-ci vous fera revenir en arrière deux fois. |
| echo, write | Afficher des chaînes, variables etc sur la sortie standard. Permet aussi d'écrire dans les fichiers. Exemple : ``echo "Bonjour"``, ``echo "Bonjour" > .\fichier.txt`` |
| gps, ps | Liste de tous les processus en cours d'éxectution. |
| spps, kill | Arrêter un processus en cours d'exécution. |
| Ctrl + C | Arrêter un processus au sein du terminal. |
| sls, findstr | Recherche d'une chaine de caractère. |
| iwr, wget, curl | Obtenir le contenu d'une page web. |
| code | Ouvrir VSCode. Exemple : ``code .``, ``code .\Sirius\`` |


[Ressources Wikipedia](https://fr.wikipedia.org/wiki/Windows_PowerShell#Comparaison_du_langage_PowerShell_et_des_langages_de_script_UNIX)

# Exercices

Après l'apprentissage des quelques commandes ci-dessus vous pouvez enfin un peu pratiquer et essayer de résoudre cet exercice :

> N'utilisez pas la commande ``clear`` que je puisse voir les commandes que vous avez utilisées.

- Dans l'interface graphique Windows rendez-vous dans le dossier **``Sirius``** et créez un **dossier ``WebDev``**.
- Dans ce nouveau dossier vous allez créer via le terminal un **fichier ``test.txt``**.
- Trouvez ce fichier dans le terminal et **afficher ``test.txt``**.
- Dans le fichier ``test.txt`` écrivez **(via une commande !)** votre nom et prénom suivi de "Je participe à Sirius 2023 !".
- Copiez ce fichier dans votre dossier Sirius, attention **copier pas déplacer** vous devez avoir ``test.txt`` dans le dossier WebDev **et** Sirius.
- Revenez dans votre dossier Sirius et lister les fichiers/dossiers présents.
- Affichez le contenu du fichier ``test.txt``.
- Supprimez le fichier ``test.txt`` se trouvant dans votre dossier ``WebDev``.
- Toujours via le terminal ouvrez le fichier ``test.txt``.

[:arrow_up: Revenir au début](#table-des-matières)

[:arrow_right: Suite du cours : *Git & Github*](../Outils_Developpeurs/Github/git_github.md)

[:rewind: Retour au sommaire du cours](../README.md)

> Cours original : [Lucas Ielli](https://github.com/lucasielli)