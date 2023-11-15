---
title: "Offrez votre site a internet !"
date: "2023-11-14T00:05:00Z"
description: "Merci papa microsoft"
author: "DestCom"
ShowReadingTime: true
---

## GitHub & GitHub Pages

### Dans un premier temps

Tout d'abord, vous aurez besoin d'un compte GitHub, puis liez votre dépôt Git à cette remote GitHub.

Comme vu dans le récapitulatif GitHub, poussez votre code sur le dépôt distant.

### Préparer notre code au déploiement

Pour récupérer votre code et le mettre sur internet, HUGO nous donne la commande `hugo` (oui, elle est assez simple).
Cela va vous créer un dossier PUBLIC, avec tout votre site web.
Vous pouvez ensuite l'envoyer en FTP sur votre serveur APACHE.

### Ne pas se casser la tête

On est en 2023, il y a énormément de solutions pour se faciliter la vie, l'une d'entre elles est **_GitHub Pages_**.

#### GitHub Pages

GitHub Pages permet d'héberger, par repository GitHub, un site web statique, de la simple page web HTML à une SPA React (enfin son build).

#### GitHub Actions

Mais comment faire pour que notre site se build tout seul lorsque l'on pousse nos commits ?
Pour cela, il y a **_GitHub Actions_**.

Les GitHub Actions sont une suite de méthodes lancées sur des serveurs distants pouvant faire diverses choses, dans notre cas, construire et publier notre site.

### Installer une Action

Pour avoir notre GitHub Action, nous pouvons nous baser sur celle fournie par HUGO dans leur documentation.

[La GitHub Action (Étape 6)](https://gohugo.io/hosting-and-deployment/hosting-on-github/)

Créez un fichier à `.github/workflows/<lenonapasdimportance>.yaml` et copiez le contenu du code de l'étape 6.

Commitez vos changements et poussez-les.

Si tout se passe bien, l'action devrait se lancer et vous donner l'URL de votre nouveau site !
