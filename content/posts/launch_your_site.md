---
title: "Offrez votre site a internet !"
date: "2023-11-14T00:05:00Z"
description: "Merci papa microsoft"
---

## GitHub & GitHub Pages

### Dans un premier temps

Tout d'abord, vous aurez besoin d'un compte GitHub, puis liez votre repository Git a cette remote GitHub.

Comme vu dans le récap github, pushez votre code sur le remote.

### Preparer notre code au déploiment

Pour récuperer votre code et le mettre sur internet, HUGO nous donne la commande `hugo` (oui, elle est assez simple)
Cela va vous creer un dossier PUBLIC, avec tout votre site web.
Vous pouvez ensuite l'envoyer en FTP sur votre serveur APACHE.

### Ne pas se casser la tete

On est en 2023, il y a énormement de solution pour se faciliter la vie, l'une d'entre elle **_GitHub Pages_**

#### GitHub Pages

Github Pages permet d'heberger par repository GitHub, un site web statique.
De la simple page web HTML a une SPA React (enfin son build)

#### GitHub Actions

Mais comment faire pour que notre site, se build tout seul lorsque l'on push nos commits ?
Pour cela, il y a **_GitHub Actions_**

Les GitHub Actions, sont une suite de méthode lancer sur des serveurs distants pouvant faire divers choses, dans notre cas, construire et publier notre site.

### Installer une Actions

Pour avoir notre GitHub Action, nous pouvons nous baser sur celle fournis par HUGO dans leurs documentation.

[La GitHub Action (Étape 6)](https://gohugo.io/hosting-and-deployment/hosting-on-github/)

Creez un fichier a `.github/workflows/<lenonapasdimportance>.yaml` et copiez le contenu du code de la step 6.

Commitez vos changement et pushez les.

Si tout ce passe bien, l'action devrait se lancer et vous donner l'url de votre nouveau site !
