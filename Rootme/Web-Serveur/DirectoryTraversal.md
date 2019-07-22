# Directory trasversal

Cette attaque consiste à utiliser une technique de navigation permettant d'accèder à certain dossier via l'url

Dans notre cas, nous avons une galerie qui a première ne contient rien de ususpect.

Hors, si on entre donc « http://challenge01.root-me.org/web-serveur/ch15/ch15.php?galerie=/ » on remarque 5 images correspondantes aux liens de la page et 1 image ne nous donnant aucune information. En regardant le code source on s’aperçoit que le lien de cette nouvelle image pointe ver « 86hwnX2r » qui est donc notre page cachée.

En entrant comme url « http://challenge01.root-me.org/web-serveur/ch15/ch15.php?galerie=86hwnX2r », on obtient trois icônes. Si on regarde de nouveau le code source de cette page, on peut apercevoir un fichier assez parlant qui est « galerie/86hwnX2r/password.txt » qui contient donc le mot de passe qu’on recherche.

En entrant « http://challenge01.root-me.org/web-serveur/ch15/galerie/86hwnX2r/password.txt» on obtient le mot de passe.
