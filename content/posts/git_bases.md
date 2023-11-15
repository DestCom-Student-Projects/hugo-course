---
title: "Bases sur Git"
date: "2023-11-14T00:01:00Z"
description: "Petite liste de commande Git."
author: "DestCom"
ShowReadingTime: true
---

## Installation de Git

- [Windows](http://msysgit.github.io/)
- [MacOS](http://code.google.com/p/git-osx-installer/downloads/list?can=3)
- [Linux](http://book.git-scm.com/2_installing_git.html)

## Récapitulatif des commandes Git

### Créer un nouveau dépôt

Créez un nouveau dossier, ouvrez-le et exécutez la commande `git init` pour créer un nouveau dépôt.

### Cloner un dépôt

Créez une copie de votre dépôt local en exécutant la commande `git clone /path/to/repository`.
Si vous utilisez un serveur distant, cette commande sera `git clone username@host:/path/to/repository`.

### Arbres

Votre dépôt local est composé de trois "arbres" gérés par Git.  
Le premier est votre _espace de travail_ qui contient réellement vos fichiers. Le second est un _Index_ qui joue un rôle d'espace de transit pour vos fichiers, et enfin _HEAD_ qui pointe vers la dernière validation que vous avez faite.
![branch](http://up1.github.io/git-guide/img/trees.png)

### Ajouter & Valider (add & commit)

Vous pouvez proposer un changement (l'ajouter à l'Index) en exécutant les commandes

```git
git add <filename>
git add *
```

C'est la première étape d'un workflow Git basique. Pour valider ces changements, utilisez `git commit -m "Message de validation"`.
Le fichier est donc ajouté au HEAD, mais pas encore dans votre dépôt distant.

### Envoyer des changements (PUSH)

Vos changements sont maintenant dans le HEAD de la copie de votre dépôt local. Pour les envoyer à votre dépôt distant, exécutez la commande `git push origin master`.

> (Remplacez "master" par la branche dans laquelle vous souhaitez envoyer vos changements.)

Si vous n'avez pas cloné votre dépôt existant et souhaitez le connecter à votre dépôt sur un serveur distant, vous devez l'ajouter avec `git remote add origin <serveur>`.

> (Maintenant, vous pouvez envoyer vos changements vers le serveur distant sélectionné.)

### Branches

Les branches sont utilisées pour développer des fonctionnalités isolées des autres. La branche master est la branche par défaut lors de la création d'un dépôt. Utilisez les autres branches pour le développement et fusionnez-les ensuite dans la branche principale lorsque vous avez terminé.

![branch](http://up1.github.io/git-guide/img/branches.png)

- Créez une nouvelle branche nommée "feature_x" et passez dessus pour l'utiliser avec `git checkout -b feature_x`.
- Revenez sur la branche principale avec `git checkout master`.
- Supprimez la branche avec `git branch -d feature_x`.
- Une branche n'est pas disponible pour les autres tant que vous ne l'avez pas envoyée vers votre dépôt distant avec `git push origin <branche>`.

### Mettre à jour & Fusionner

- Pour mettre à jour votre dépôt local avec les dernières validations, exécutez la commande `git pull` dans votre espace de travail pour récupérer et fusionner les changements distants.
- Pour fusionner une autre branche avec la branche active (par exemple master), utilisez `git merge <branche>` ; dans les deux cas, git tente d'auto-fusionner les changements.
- Malheureusement, ce n'est pas toujours possible et peut résulter en des conflits. Vous devez alors régler ces conflits manuellement en éditant les fichiers indiqués par git. Après cela, vous devez les marquer comme fusionnés avec `git add <nom_fichier>` ; après avoir fusionné les changements, vous pouvez avoir un aperçu en utilisant `git diff <source_branch> <target_branch>`.

### Tags

Il est recommandé de créer des tags pour les releases de programmes.
C'est un concept connu, qui existe aussi dans SVN.

Vous pouvez créer un tag nommé 1.0.0 en exécutant la commande
`git tag 1.0.0 1b2e1d63ff`

> Le "1b2e1d63ff" désigne les 10 premiers caractères de l'identifiant du changement que vous voulez référencer avec ce tag.

Vous pouvez obtenir cet identifiant avec `git log`. Vous pouvez utiliser moins de caractères de cet identifiant, tant qu'il reste unique.

### Remplacer les changements locaux

Dans le cas où vous auriez fait quelque chose de travers (ce qui bien entendu n'arrive jamais ;)), vous pouvez annuler les changements locaux en utilisant cette commande `git checkout -- <nom_fichier>`.
Cela remplacera les changements dans votre arborescence de travail avec le dernier contenu du HEAD. Les changements déjà ajoutés à l'index, y compris les nouveaux fichiers, seront gardés.

Si vous souhaitez supprimer tous les changements et validations locaux, récupérez le dernier historique depuis le serveur et pointez la branche principale locale dessus comme ceci :

```git
git fetch origin
git reset --hard origin/master
```
