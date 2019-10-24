Liste des commandes (entre *) de Git de consultation de l'historique et des modifications :

Git log :

*git --no-pager log --oneline* affiche l'historique sans pagination, la console ne bloque pas
*git --no-pager log -3 --oneline* idem pour les 3 derniers commits
*git log --oneline -2* affiche les 2 derniers commits
*git log --author "Killian"* affiche tous les commits réalisés par cet utilisateur
*git log --since=1.day* affiche tous les commits réalisés depuis 1 jour
*git log --before="2019-09-01"* affiche tous les commits réalisés avant le 01/09/2019
*git log index.html* affiche tous les commits réalisés sur ce fichier uniquement
*git log -p index.html* idem au sein d'un fichier ou de l'ensemble des fichiers
*git log -p* affiche toutes les modifications réalisés dans le dossier depuis le dernier commit
*git log -2 -p* idem pour les 2 derniers commits
*git log --stat index.html* affiche les stats des comits, nombre de lignes ajoutées et supprimées
*git log -E -i --grep='Webflow'* rechercher tous les messages de commit ou le mot "webflow" est présent, E pour occurence et i pour insensible à minuscule/majuscule


Git blame :

*git blame generalites.md* affiche toutes les modifications réalisées dans ce fichier avec son auteur


Git diff :

*git diff* visualiser les modifications dans un fichier avant de l'indexé (WD et index)
*git diff --cached* idem mais entre le dernier commit et l'index
*git diff HEAD~1* voir les modifications d'un commit en arrière
*git diff HEAD~3 HEAD* voir les différences entre le HEAD et 3 commits en arrière

Voir les modifications entre 2 commits:
*git log --oneline* pour récupérer les haches des 2 derniers commits
*git log a6b9470 344ccc5* pour récupérer les logs des deux derniers commits

*git diff stat* affiche des stats sur les différences effectuées dans les fichiers


Git restore (annuler les modifications dans l'espace de travail) :

*git restore generalites.md* remet le dépôt dans l'état dans lequel il se trouvait juste avant la modification dans le fichier
*git restore --staged* dans le cas où le fichier est déja indexé

Modifier un message de commit :
*git commit -m "modification et liste complète de toutes les commandes Git" --amend*
*git commit -m "un message" --amend --no-edit* permet de changer uniquement le message du dernier commit


Git reset HEAD~1 :

*git reset HEAD~1* annule le dernier commit et met tout dans l'espace de travail sans perte (revient au commit précédent)
*git reset --soft HEAD~1* annule le dernier commit et met tout dans la staging area sans perte

Git reset [commit] :

pour annuler le commit d'un fichier il faut :
-- afficher l'historique pour avoir la clé de hachage
-- alors pour annuler le commit du fichier n°33

124f561 (HEAD -> master) file33
6695308 file22
0637561 file11
0a70edb file01

-- il faudra taper *git reset 124f561*


Git reset --hard (A FAIRE AVEC BEAUCOUP DE PRUDENCE !!!):

*git reset --hard HEAD~1* annule le dernier commit et supprime les modifications (DANGER !!!)


Git checkout : 

*git checkout 124f561 file33.txt* permet de revenir avant la refonte et ainsi revenir à l'état initial


Git revert : 

*git revert* annule le commit en créant un commit d'annulation

Création fichiers / dossiers Git :

*mkdir nom_dossier* créer un dossier
*cd nom_dossier* sortir de ce dossier
*echo "Title : file readme" > READMEmd* mettre le texte "Title : file readme" dans un fichier README.md