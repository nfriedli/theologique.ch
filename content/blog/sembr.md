+++
title = "Sauts de ligne sémantiques"
description = ""
date = 2025-09-18
draft = true
+++

Différentes sources produisent le même résultat.
Le formatage de la source est donc une *convention*.
C’est important pour la [collaboration](/blog/collaboration/)

Les sauts de ligne sémantiques sont une convention pour la rédaction des fichiers source. XXX trop compliqué
Les langage de balisage léger, comme [Markdown](/blog/markdown/), permettent

## Exemple de sources

Les trois fichier suivantes produiront le même résultat de sortie:

```markdown
Voici un exemple de texte en Markdown.
Cette syntaxe ne tient pas compte des sauts de ligne.
Des sources différentes présentent des sorties identiques.
C’est ce que j’illustre sur cette page.

```

```markdown
Voici un exemple de texte en Markdown. Cette syntaxe ne tient pas compte des sauts de ligne. Des sources différentes présentent des sorties identiques. C’est ce que j’illustre sur cette page.

```

```markdown
Voici un exemple de texte en Markdown. Cette
syntaxe ne tient pas compte des sauts de ligne.
Des sources différentes présentent des sorties
identiques. C’est ce que j’illustre sur cette
page.
```

Le résultat sera toujours:

> Voici un exemple de texte en Markdown.
Cette syntaxe ne tient pas compte des sauts de ligne ni des espaces multiples.
Ce qui fait que de fichiers différents peuvent présenter des sorties identiques.
C’est ce que j’illustre sur cette page.

## Visualisation des différences

## Avantages d’une convention

[Semantic Line Breaks](https://sembr.org/)
