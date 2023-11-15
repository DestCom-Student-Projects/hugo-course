---
title: "Creez votre premier posts !"
date: "2023-11-14T00:03:00Z"
author: "DestCom"
ShowReadingTime: true
---

## Créer votre post

Une commande est là pour vous : `hugo new content/posts/my-first-post.md`

### Le Front Matter

Le front matter est une syntaxe qui vous permet de gérer les métadonnées de vos posts.
Cette portion de code se situe en début de votre fichier. Elle peut être écrite en TOML, YAML ou JSON.
Le front matter possède de nombreuses variables, dont la liste est disponible [ici](https://gohugo.io/content-management/front-matter/#front-matter-variables).

Mais voici les plus courantes :

```toml
---
title: "Creez votre premier posts !"
date: "2023-11-14T00:03:00Z"
description: "Ma description"
---
```

Tous les détails sur le frontmatter sont disponibles sur [https://gohugo.io/content-management/front-matter](https://gohugo.io/content-management/front-matter).

### Le contenu de votre post

Le contenu peut être écrit soit en HTML, soit en Markdown.

#### Petit rappel Markdown

##### Titres

Les éléments HTML suivants `<h1>` à `<h6>` représentent six niveaux de titres de section. `<h1>` est le niveau de section le plus élevé tandis que `<h6>` est le plus bas.

```md
# H1

## H2

### H3

#### H4

##### H5

###### H6
```

##### Paragraphe

```md
Xerum, quo qui aut unt expliquam qui dolut labo. Aque venitatiusda cum, voluptionse latur sitiae dolessi aut parist aut dollo enim qui voluptate ma dolestendit peritin re plis aut quas inctum laceat est volestemque commosa as cus endigna tectur, offic to cor sequas etum rerum idem sintibus eiur? Quianimin porecus evelectur, cum que nis nust voloribus ratem aut omnimi, sitatur? Quiatem. Nam, omnis sum am facea corem alique molestrunt et eos evelece arcillit ut aut eos eos nus, sin conecerem erum fuga. Ri oditatquam, ad quibus unda veliamenimin cusam et facea ipsamus es exerum sitate dolores editium rerore eost, temped molorro ratiae volorro te reribus dolorer sperchicium faceata tiustia prat.

Itatur? Quiatae cullecum rem ent aut odis in re eossequodi nonsequ idebis ne sapicia is sinveli squiatum, core et que aut hariosam ex eat.
```

##### Blocs de citation

L'élément de bloc de citation représente le contenu qui est cité d'une autre source, éventuellement avec une citation qui doit être dans un élément `footer` ou `cite`, et éventuellement avec des modifications en ligne telles que des annotations et des abréviations.

###### Bloc de citation sans attribution

```md
> Tiam, ad mint andaepu dandae nostion secatur sequo quae.
> **Remarque** que vous pouvez utiliser la _syntaxe Markdown_ dans un bloc de citation.
```

###### Bloc de citation avec attribution

```md
> Ne communiquez pas en partageant la mémoire, partagez la mémoire en communiquant.
>
> — <cite>Rob Pike</cite>
```

##### Tableaux

Les tableaux ne font pas partie de la spécification de base de Markdown, mais Hugo les prend en charge nativement.

```md
| Nom   | Âge |
| ----- | --- |
| Bob   | 27  |
| Alice | 23  |
```

###### Markdown en ligne dans les tableaux

```md
| Italique   | Gras     | Code   |
| ---------- | -------- | ------ |
| _italique_ | **gras** | `code` |
```

##### Blocs de code

###### Code en ligne

```md
`Ceci est un code en ligne`
```

###### Seulement `pre`

```md
<pre>
Ceci est un texte préformaté
</pre>
```

##### Types de listes

###### Listes ordonnées

```md
1. First item
2. Second item
3. Third item
```

###### Listes non-ordonnées

```md
- List item
- Another item
- And another item
```

###### Liste indentées

```md
- Fruit
  - Apple
  - Orange
  - Banana
- Dairy
  - Milk
  - Cheese
```
