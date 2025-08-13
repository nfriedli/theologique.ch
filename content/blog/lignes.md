+++
title = "Sauts de lignes sémantiques"
description = ""
date = 2025-08-13
draft = true
+++

Plusieurs systèmes de balisage léger ne prennent pas en compte les saut de ligne (sauf ceux qui sont forcés).
[Markdown](/blog/markdown/) dont j'ai parlé sur ce site procède ainsi.

C'est particulièrement intéressant quand on fait des copier-coller, par exemple de fichiers PDF.

Mais c'est intéressant dans le texte source.
Il est possible d'utiliser une ligne par idée.
Et d'effectuer un saut à chaque phrase.

La source du dernier paragraphe:

```
Mais c'est intéressant dans le texte source.
Il est possible d'utiliser une ligne par idée.
Et d'effectuer un saut à chaque phrase.
```

Je ne savais pas que cela avait été systématisé.
Puis j'ai découvert [Semantic Line Breaks](https://sembr.org/).

En travaillant avec un éditeur de texte (plutôt qu'un traitement de texte), c'est vraiment intéressant.
C'est très lisible, parce que le texte est assez étroit.
Il est facile de naviguer dans le document par numéro de ligne.
Et, dans tout éditeur qui se respecte, changer l'ordre des lignes se fait plus rapidement qu'un copier-coller.

Avec un système de gestion de versions, comme Git, c'est un vrai bonheur pour les différences (`diff`).
En langage courant: c'est beaucoup plus intéressant de savoir quelle *ligne* a changé plutôt que quel *paragraphe* a changé.

Certaines personnes limitent volontairement la longueur de la ligne (même si la phrase est longue).
On peut alors afficher les différence dans des parties de phrases.
L'article [Semantic Linefeeds](https://rhodesmill.org/brandon/2012/one-sentence-per-line/) de Brandon Rhodes l'illustre par un exemple.
Mais je n'utilise pas cette méthode des lignes tronquées.

XXX Est-ce que ça change?

En tout cas Python, ça change!
