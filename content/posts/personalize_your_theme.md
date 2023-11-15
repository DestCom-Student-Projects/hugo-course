---
title: "Personalisez votre thème !"
date: "2023-11-14T00:04:00Z"
description: "Votre theme ne vous siez guere, reprenez la main"
---

## La personalisation

Vous aimerez adapter votre theme a vos gouts ? C'est possible.
En HUGO, vous pouvez surcharger les thèmes.

### La surcharge

Chaque fichier de votre themes est changeable, mais etant donnée que vous utilisez un submodule, vous ne pouvez pas changer le code directement.

Pour cela, il faut suivre l'exact chemin de votre theme, par exemple:

- Imaginez que le theme de votre footer suis ce chemin `./themes/VotreTheme/layouts/global/footer.html`
- Creez un fichier qui suis ce chemin sur votre layout de votre dossier HUGO, dans l'exemple : `./layouts/global/footer.html`
- Copiez le contenu du fichier du theme sur votre nouveaux et fait vos modifications

Vous pouvez faire cela avec le fichier statiques comme des images, du styles, etc...
