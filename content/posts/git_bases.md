---
title: "Bases sur Git"
date: "2023-11-14T00:01:00Z"
description: "Petite liste de commande Git."
---

## Installation de git

- [Windows](http://msysgit.github.io/)
- [MacOS](http://code.google.com/p/git-osx-installer/downloads/list?can=3)
- [Linux](http://book.git-scm.com/2_installing_git.html)

## Récapitulatif de commandes Git

### Créer un nouveau dépôt

Créez un nouveau dossier, ouvrez le et exécutez la commande `git init` pour créer un nouveau dépôt.

### Cloner un dépôt

Créez une copie de votre dépôt local en exécutant la commande `git clone /path/to/repository`
si vous utilisez un serveur distant, cette commande sera `git clone username@host:/path/to/repository`

### Arbres

Votre dépôt local est composé de trois "arbres" gérés par git.  
Le premier est votre _espace de travail_ qui contient réellement vos fichiers. Le second est un _Index_ qui joue un rôle d'espace de transit pour vos fichiers et enfin _HEAD_ qui pointe vers la dernière validation que vous ayez fait.
![branch](http://up1.github.io/git-guide/img/trees.png)

### Ajouter & Valider (add & commit)

Vous pouvez proposer un changement (l'ajouter à l'Index) en exécutant les commandes

```git
git add <filename>
git add *
```

C'est la première étape dans un workflow git basique. Pour valider ces changements, utilisez `git commit -m "Message de validation"`
Le fichier est donc ajouté au HEAD, mais pas encore dans votre dépôt distant.

### Envoyer des changements (PUSH)

Vos changements sont maintenant dans le HEAD de la copie de votre dépôt local. Pour les envoyer à votre dépôt distant, exécutez la commande `git push origin master`.

> (Remplacez master par la branche dans laquelle vous souhaitez envoyer vos changements.)

Si vous n'avez pas cloné votre dépôt existant et voulez le connecter à votre dépôt sur un serveur distant, vous devez l'ajouter avec `git remote add origin <server>`

> (Maintenant, vous pouvez envoyer vos changements vers le serveur distant sélectionné.)

### Branches

Les branches sont utilisées pour développer des fonctionnalités isolées des autres. La branche master est la branche par défaut quand vous créez un dépôt. Utilisez les autres branches pour le développement et fusionnez ensuite à la branche principale quand vous avez fini.

![branch](http://up1.github.io/git-guide/img/branches.png)

- créer une nouvelle branche nommée "feature_x" et passer dessus pour l'utiliser `git checkout -b feature_x`
- retourner sur la branche principale `git checkout master`
- supprimer la branche `git branch -d feature_x`
- une branche n'est pas disponible pour les autres tant que vous ne l'aurez pas envoyée vers votre dépôt distant `git push origin <branch>`

### Mettre à jour & Fusionner

- Pour mettre à jour votre dépôt local vers les dernières validations exécutez la commande `git pull` dans votre espace de travail pour récupérer et fusionner les changements distants.

- Pour fusionner une autre branche avec la branche active (par exemple master), utilisez `git merge <branch>` dans les deux cas, git tente d'auto-fusionner les changements.

- Malheureusement, ça n'est pas toujours possible et résulte par des conflits. Vous devez alors régler ces conflits manuellement en éditant les fichiers indiqués par git. Après l'avoir fait, vous devez les marquer comme fusionnés avec `git add <filename>` après avoir fusionné les changements, vous pouvez en avoir un aperçu en utilisant `git diff <source_branch> <target_branch>`

### Tags

Il est recommandé de créer des tags pour les releases de programmes.
C'est un concept connu, qui existe aussi dans SVN.

Vous pouvez créer un tag nommé 1.0.0 en exécutant la commande
`git tag 1.0.0 1b2e1d63ff`

> le 1b2e1d63ff désigne les 10 premiers caractères de l'identifiant du changement que vous voulez référencer avec ce tag.

Vous pouvez obtenir cet identifiant avec `git log` vous pouvez utiliser moins de caractères de cet identifiant, il doit juste rester unique.

### Remplacer les changements locaux

Dans le cas où vous auriez fait quelque chose de travers (ce qui bien entendu n'arrive jamais ;)
Vous pouvez annuler les changements locaux en utilisant cette commande `git checkout -- <filename>`
Cela remplacera les changements dans votre arbre de travail avec le dernier contenu du HEAD. Les changements déjà ajoutés à l'index, aussi bien les nouveaux fichiers, seront gardés.

Si à la place vous voulez supprimer tous les changements et validations locaux, récupérez le dernier historique depuis le serveur et pointez la branche principale locale dessus comme ceci

```git
git fetch origin
git reset --hard origin/master
```
