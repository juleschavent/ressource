## Status
    //premet de connaître l'état actuel de git
    //ex : commit en attente, branche de travaille etc
    git status

## Log
    //voir les dernières infos de ce qui a été fait sur git
    git log --oneline

## Commit
    //ajoute tous les nouveaux fichiers
    git add .
    
    //commit les changements avec un message personnalisé
    git commit -m "mon message"

## Push
    //push les derniers commit sur la branche actuelle
    git push

## Créer nouvelle branche
    git branch nomDeMaBranche

    //crée une nouvelle branche et passe dirèctement dessus
    git checkout -b nomDeMaBranche

## Changer de branche 
    git checkout nomDeMaBranche

## Afficher toutes les branches
    //affiche toutes les branches
    // la branche actuelle est précédée d'un *
    git branch -a

## Supprimer une branche
    //supprime une branche si elle a été merge dans la branche principale
    //attention erreur si la branche n'a pas été merge
    git branch -d nomDeMaBranche

    //supprime une branche même si elle n'a pas été merge
    git branch -D nomDeMaBranche

## Merge une branche
    //il faut se trouver dans branche principale 
    git merge nomDeLaBranche

## Supprimer une branche en remote
    https://stackoverflow.com/questions/35941566/git-says-remote-ref-does-not-exist-when-i-delete-remote-branch
    //mise à jour avec les infos du repo en ligne
    git fetch --prune

    //supprime la version en ligne de la branche
    git push origin --delete maBranche