+++
title = "Web sémantique"
description = ""
date = "2025-09-15"
draft = true
+++

Il n'y a pas besoin de beaucoup d'éléments pour produire des pages web avec une forte valeur sémantique.
C'est parce que ces éléments utiles, voire nécessaires, sont peu nombreux qu'il est possible de travailler avec un [balisage léger comme Markdown](/blog/markdown/).
Je liste l'essentiel de ce qui permet de produire de bonnes pages web.
J'essaie de proposer le contenu le moins technique possible.

## Structure

Le titre est essentiel.
Il est balisé automatiquement par `h1` dans tous les outils qui produisent des pages web.
En principe, ce serait bien d'utiliser un seul titre `h1` par page, même si HTML permet d'en utiliser plusieurs.
Il ne faut jamais proposer un titre vide, y compris pour des raisons esthétiques.

Ensuite, la page propose sa hiérarchie avec des titres `h2`, `h3`, etc.
HTML propose 6 niveaux de titres, mais je conseille de vous limiter aux niveaux 2 ou 3 dans la majorité des cas.
Une page très structurée de documentation peut bien entendu aller plus loin.

Il faut respecter la hiérarchie des titres (un `h3`ne peut jamais suivre directement `h1`).
Et, bien entendu, de ne jamais utiliser les titres pour des raisons visuelles.

L'[extension SEO Detailed](https://detailed.com/extension/) permet de vérifier instantanément la structure de la page finale dans son navigateur.
Je conseille à toutes les personnes qui gèrent un site de l'installer et de l'utiliser régulièrement.

La structure est en principe rendue visuellement, par des espacements, des tailles d'écriture, des polices spécifiques, etc.
Parfois, elle est aussi présente dans une table des matières de la page.
Mais, quel que sont son rendu, elle compte énormément, tant pour des questions d'accessibilité (A11Y) que de référencement (SEO).

## Formatage du texte

Le texte, à proprement parler, n'a pas forcément besoin de beaucoup d'éléments sémantiques.
Il peut être clair sans ajouts particuliers.

### Paragraphes (& sauts de lignes)

L'unité naturelle du texte, c'est le paragraphe.
Avec un principe simple: 1 paragraphe = 1 idée.
Le web et les paragraphes simples et courts font très bon ménage.
Toute page n'est pas du Proust.

Souvent, il existe un espacement entre 2 paragraphes successifs.
Quand cela ne convient pas, il est possible d'utiliser des sauts de ligne (qui restent dans la même unité sématique).

C'est utile.  
Parfois.  
Rarement.  
Mais ça existe.

Si votre site propose un espacement problématique entre les paraphraphes (trop petit ou trop grand), il faut le gérer de manière globale.
Une feuille de style CSS ou un petit code dans votre WordPress (CSS additionnel dans la personnalisation) règlent cela pour tout le site, sans changement sémantique.

### Liens

Les liens sont la brique de base du web avec le texte.
Je conseille de toujours les insérer dans le corps du texte, au bon endroit, avec un intitulé correct.

La règle [Opquast 132](https://checklists.opquast.com/fr/assurance-qualite-web/le-libelle-de-chaque-lien-decrit-sa-fonction-ou-la-nature-du-contenu-vers-lequel-il-pointe) est claire:

> Le libellé de chaque lien décrit sa fonction ou la nature du contenu vers lequel il pointe.

Avec des unités de sens de tailles raisonnables et des liens dans le corps du texte, c'est ce qui donne le plus de sens.
Des liens aux intitulés porteurs de sens placés dans le bon contexte sont le meilleur outil sémantique qui soit.

### Emphases

HTML propose 2 types de mises en évidence:

- l'emphase (`em`) rendue par défaut par un *italique*
- l'emphase forte (`strong`) rendue par défaut par un **gras**

Les balises `i` et `b` sont sémantiquement beaucoup moins intéressantes et à abandonner.

### Citations

Les citations doivent être balisées avec `blockquote` et pas être mises simplement en italique ou en gras.
Par défaut dans la majorité des navigateurs, la citation propose un léger retrait.
Ensuite, toutes la variations sont possibles (soit au niveau du site par CSS, soit au niveau de la citation avec WordPress).

La règle Opquast ci-dessus (voir [Liens](#liens)) donne un exemple de citation sur theologique.ch.
Il est possible d'affiner les choses avec un attribut `cite`, mais je me perds dans les débats sur le sujet.
Je préfère donner le lien de la source dans l'introduction à l'extrait.

## Listes

Formellement, les listes sont aussi un formatage du texte.
J'en fait pourtant un élément de structure différent parce qu'elles sont particulières.

### Liste non ordonnée

La liste non ordonnée est souvent appelée «liste à puces».
Toutefois, une liste `ul` (*unordered list*) peut se présenter visuellement sans puces.

Dans une recette de cuisine, la liste non ordonnées présente les ingrédients:

- lait
- beurre
- farine
- sel
- poivre

L'ordre n'est pas fondamental d'un point de vue sémantique, mais il garde son sens à la lecture.
J'omets les quantités et simplifie; pour réaliser une [sauce Béchamel](https://chefsimon.com/gourmets/chef-simon/recettes/sauce-bechamel--8), je vous renvoie chez [Chef Simon](https://chefsimon.com/).

### Liste ordonnée

Dans une liste ordonnée (`ol` comme *ordered list*), comme on peut s'y attendre, l'ordre compte.

Pour poursuivre notre recette de cuisine:

1. Faire fondre le beurre sans coloration.
2. Ajouter la farine.
3. Cuire le roux.
4. Verser le lait en une fois.
5. Etc.

Je trouve les listes ordonnées sous utilisées sur le web.
À chaque fois que l'on poste une liste, il faudrait se demander si son ordre a un sens ou non.

### Liste de définition

La liste de définition est beaucoup trop peu utilisée alors qu'elle est sémantiquement très intéressante.
WordPress, qui motorise la moité du web, ne la propose malheureusement par défaut.

Elle pourrait se présenter ainsi, sans notre suite culinaire:

roux
: tant pour tant de farine et de beurre cuit lentement

sauce
: machin plus ou moins liquide (et plus ou moins bon) pour mettre en valeur (ou pas) un plat

Ce qui est intéressant, c'est la très forte valeur sémantique du code:

```
<dl>

<dt>roux</dt>
<dd>tant pour tant de farine... </dd>

<dt>sauce</dt>
<dd>machin plus ou moins liquide...</dd>

</dl>
```

Le terme (`dt` ou *description term*) est fortement lié à sa description (`dd` ou *description détails*).
C'est exactement la structure que j'utilise sur les pages paroissiales de [Trouver ma paroisse](https://ma-paroisse.ch/) avec de beaux résultats dans les moteurs de recherche (SERP).

## Éléments multimédias

## Tableaux

## Métadonnées

## À propos des données structurées

## À propos des intelligences artificielles (IA)