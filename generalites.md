Listes des commandes (entre *) générales de Git : 

Configuration de Git :

nom d'utilisateur: *git config --global user.name Killian*
email: *git config --global user.email killian.moutinard@ynov.com*

Git est composé de 3 zones : Working Area, Staging Area et le Dépôt

Pour passer de la zone de travail au répertoire, on doit indexé notre fichier avec *git add nom_fichier.extension* (exemple: *git add index.html*)
Si on a beaucoup de fichiers à ajouter on peut faire un *git add .* ou *git add -A*, ceci va ajouter tous les fichiers présents dans le dossier.
Ensuite pour mettre notre fichier dans le dépot, on doit faire un commit : *git commit -m "nom du commit"* (exemple *git commit -m "first commit"*)
Si on veut taper un texte plus long dans le commit il suffit de faire *git commit* et la un éditeur de texte s'ouvre (nano ou vim).

Tout d'abord, on doit initialiser le projet et ainsi passer en mode (master), pour cela il faut faire un *git init*

Une autre commande est très utile afin de savoir si tout fonctionne c'est le *git status* si en réponse il affiche "nothing to commit, working tree clean" alors notre feuille de travail est propre.

Pour désindexer un fichier on utilise *git rm --cached index.html*

Pour afficher tous les commits réalisés (version longue) on utilise *git log* (EXIT -> "q")
Pour afficher tous les commits réalisés (version courtesur une ligne) on utilise *git log --oneline*
Idem avec moins de détails *git shortlog*
4 derniers commits réalisés *git log -4*

Commandes d'aides : 
*git help [nom de la commande]* ex: *git help log* va ouvrir une page web expliquant la fonction de la commande que vous avez entrer
*git log master..origin/master* pour voir les différences entre deux branches
*git log -p -4* affiche un log avec différence pour chaque commit sur les 4 derniers
*git log --stat* affiche les stats sur les modifications par commit
*git log --since=2.weeks* affiche tous les commits réalisés depuis 2 semaines

Rechercher qui a fait les commits :
*git blame -L 40,60 readme.md* affiche qui a fait des commits de la ligne 40 à 60 sur le fichier readme.md
*git blame --since=3.weeks -- readme.md* affiche qui a fait les commits depuis 3 semaines avec auteurs
*git blame -L "/^### /" readme.md* recherche avec expression régulière

Renommer un fichier :
*git mv mon_ancien_fichier mon_nouveau_fichier* ex: *git mv index.html webflow.html*

Supprimer un fichier :
*git rm mon_fichier* ex: *git rm webflow.html*

Ne plus suivre un fichier :
*git rm --cached images/logo.png* pour ne plus suivre le fichier logo.png présent dans le dossier images

Afficher tous les fichiers suivis : 
*git ls-files*

Configuration du .gitignore :

Commandes à mettre dans le fichier .gitignore:
vendor --> ignore tous les dossiers vendor
/vendor --> ignore le dossier vendor à la racine du dépôt
doc/foo/ --> ignore doc/foo mais pas a/doc/foo
foo/ --> ignore a/foo et foo
foo/* ignore n'importe quel fichier autre qu'un "/"
*.txt --> ignore tous les fichiers de l'extension ".txt"
foo/*.txt --> ignore tous les fichiers de ce type dans les dossiers foo de l'application
/*.txt --> ignore jusqu'au niveau racine du dépôt
**/foo --> ignore foo/a, bar/foo/a mais pas foo/a/b
foo[0-9] --> ignore foo0, foo1, foo2, ..., foo9
foo --> ignore a/foo, foo/a/b, a/b/foo, ...
foo/**/bar --> ignore foo/a/b/c/bar, foo/bar, ...

