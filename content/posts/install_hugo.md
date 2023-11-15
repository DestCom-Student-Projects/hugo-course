---
title: "Installation de HUGO sur MACOS"
date: "2023-11-14T00:02:00Z"
description: "Windows débrouillez vous, c'est plus simple avec HomeBrew."
---

## Installation via HomeBrew

- Lancez un terminal sur votre mac
- Installez homebrew si ce n'est pas encore le cas ici : [Installation de Homebrew](https://brew.sh/)
- Copiez-collez cette commande :
  `brew install hugo`
- Relancez votre terminal

## Initialisez votre site HUGO

Dans un terminal, tapez :

1. `hugo new site <votre-nom-de-projet>`
2. `cd <votre-nom-de-projet>`
3. `git init` (pour initialiser le repository GitHub)
4. Ajoutez ensuite un theme de votre choix (de préférence via un submodule git)
5. `hugo server` (pour lancer un serveur de développement)
   > Il est possible d'ajouter -D a la fin pour pouvoir voir les posts en draft
