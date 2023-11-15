---
title: "Installation de HUGO sur MACOS"
date: "2023-11-14T00:02:00Z"
description: "Windows débrouillez vous, c'est plus simple avec HomeBrew."
author: "DestCom"
ShowReadingTime: true
---

## Installation via Homebrew

- Ouvrez un terminal sur votre Mac.
- Installez Homebrew si ce n'est pas encore fait, en suivant ce lien : [Installation de Homebrew](https://brew.sh/).
- Copiez-collez cette commande :
  `brew install hugo`
- Redémarrez votre terminal.

## Initialisez votre site HUGO

Dans un terminal, saisissez :

1. `hugo new site <votre-nom-de-projet>`
2. `cd <votre-nom-de-projet>`
3. `git init` (pour initialiser le dépôt GitHub)
4. Ajoutez ensuite un thème de votre choix (de préférence via un submodule git).
5. `hugo server` (pour lancer un serveur de développement)
   > Il est possible d'ajouter -D à la fin pour pouvoir voir les posts en brouillon.
