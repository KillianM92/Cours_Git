Liste des commandes (entre *) de Git pour les branches :

*git branch dev* crée une branche
*git branch* affiche l'ensemble des branches présentes dans le dépôt
*git checkout dev* se déplacer sur la branche dev
*git checkout master* se déplacer sur la branche master
*git checkout -b feature_header* crée la branche "feature_header" et se déplace directement dessus
*git branch -d [nom de votre branche]* supprimer une branche
*git branch -D [nom de votre branche]* forcer la suppression de la branche
*git merge dev* si l'on est sur la branche master, on merge la branche dev dans la branche master
*git merge dev --no-ff* effectue un commit de merge
*git branch --no-merged* affiche la liste de toutes les branches non mergées

Remisage :

*git stash* remiser le code non terminé
*git stash list* liste sur la branche tous les stash
*git stash apply* on récupère l'ancien code modifié
*git stash drop* on supprime ce qui se trouve dans la remise
*git stash apply --index* essaye de remettre ce qui était dans l'index
*git stash apply stash@{1}* appliquer un stash particulier
*git stash drop stash@{1}* supprimer le stash appliqué
*sh deploy_stash.sh* création d'un dépôt

Tags :

*git tag -a v1.0 -m "version 1 de l'appli"* création d'un tag annoté
*git tag v1* création d'un tag léger (peu utilisé)
*git tag -a v1.0.1 -m "version 1.0.1" 9fceb3* étiquetter après coup un commit donné
*git tag* affiche la liste des tags
*git tag -1 'v8.¤'* rechercher un tag particulier
*git show v8.2* voir un tag annoté

Création d'un serveur :

Liste des commandes à suivre :
*cd GitServer*             (à effectuer sur le bureau)
*mkdir nom_du_dossier_server.git* création du dossier pour le serveur
*cd nom_du_dossier_server.git*

*git --bare init* création du serveur

*cd nom_du_dossier*
*git init*
*echo "# Lessons" > README.md*
*git add .*
*git commit -m "first commit"*
*git remote add origin C:\Serveurs_Git\nom_du_dossier_server.git* (penser à ne pas mettre d'espace, ni de caractères spéciaux dans le chemin d'accès au fichier)

*git push origin master* push la branche master dans votre dépôt dans le server origin
*git push [nom_distant] [nom_de_branche]* publier sur la branche distante (serveur)

*git pull origin master* permet de retirer ce que vous avez mis dans le depôt distant (server)
*git remote* permet de lister les dépôts distants
*git remote -v* idem en mode verbeux
*git remote add [alias] [chemin_du_serveur_distant]* ajouter un dépôt distant
*git remote rm [alias]* supprimer un dépôt distant
*git remote rename [alias] [new_alias]* renommer un dépôt distant
*git fetch origin* permet de récupérer la branche distante localement sans fusion avec sa branche master
*git log master..origin/master* permet de comparer les différences entre master local et distant (après avoir effctué un fetch)
(*git pull* = *git fetch* + *git merge*)
*git fetch origin*
*git merge origin/master*
*git remote show origin* inspecter un dépôt distant