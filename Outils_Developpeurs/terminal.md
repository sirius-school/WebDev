<!-- omit in toc -->
# Le Terminal

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

Étant donné que nous allons utiliser le terminal pour la gestion de fichiers, nous verrons uniquement les commandes associées :

| Commande | Description | 
| :---: | :---- |
| gci, dir, ls | Liste les fichiers/dossiers du répertoire. Exemple : ``ls`` ou ``ls .\Sirius\`` | 
| gc, type, cat | Obtenir le contenu d'un **fichier**. Exemple : ``cat .\fichier.txt``  |
| help, man | Aide. |
| cls, clear | Efface l'écran. |
| cpi, copy, cp | Copier un ou plusieurs fichiers/l'arborescence complète. Exemple : ``cp D:\Sirius\WebDev\fichier.txt C:\Autres`` |
| mi, move, mv | Déplacer un fichier/répertoire. Exemple : ``mv .\fichier.txt .\Sirius\`` |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |

	gcm	help	help, which	Liste des commandes
	help, man	help	man	Aide
	cls, clear	cls	clear	Efface l'écran
	cpi, copy, cp	copy	cp	Copier un ou plusieurs fichiers / l'arborescence complète
	mi, move, mv	move	mv	Déplacer un fichier / répertoire
	ri, del, erase, rmdir, rd, rm	del, deltree, erase, rmdir, rd	rm, rmdir	Supprimer un fichier / répertoire
	rni, ren, mv	ren, rename	mv	Renommer un fichier / répertoire
	gl, pwd	cd	pwd	Afficher le répertoire de travail courant
	popd	popd	popd	Changer le répertoire courant vers le répertoire le plus récemment poussé sur la pile
	pushd	pushd	pushd	Pousser le répertoire courant sur la pile
	sl, cd, chdir	cd, chdir	cd	Changer le répertoire courant
	tee	NC	tee	Diriger l'entrée vers un fichier ou une variable, puis la passer dans un pipeline
	echo, write	echo	echo	Afficher des chaînes, variables etc sur la sortie standard
	gps, ps	tlist	ps	Liste de tous les processus en cours d'exécution
	spps, kill	kill	kill	Arrêter un processus en cours d'exécution
	sls, findstr	find, findstr	grep	Recherche d'une chaine de caractère
	sv, set	set	env, export, set, setenv	Définir la valeur d'une variable / créer une variable
	iwr, wget, curl	NC	wget, cURL	Obtient le contenu d'une page web

https://fr.wikipedia.org/wiki/Windows_PowerShell


