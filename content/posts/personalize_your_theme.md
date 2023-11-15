---
title: "Personalisez votre thème !"
date: "2023-11-14T00:04:00Z"
description: "Votre theme ne vous siez guere, reprenez la main"
author: "DestCom"
ShowReadingTime: true
---

## La personnalisation

Vous aimeriez adapter votre thème à vos goûts ? C'est possible.
Avec HUGO, vous pouvez surcharger les thèmes.

### La surcharge

Chaque fichier de votre thème est modifiable, mais étant donné que vous utilisez un submodule, vous ne pouvez pas modifier directement le code.

Pour cela, il faut suivre le chemin exact de votre thème, par exemple :

- Imaginons que le thème de votre footer suive ce chemin `./themes/VotreTheme/layouts/global/footer.html`.
- Créez un fichier suivant ce chemin dans votre dossier HUGO, par exemple : `./layouts/global/footer.html`.
- Copiez le contenu du fichier du thème vers votre nouveau fichier et effectuez vos modifications.

Vous pouvez faire cela avec des fichiers statiques tels que des images, des styles, etc...
