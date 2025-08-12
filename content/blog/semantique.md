+++
title = "Web sématique facile"
description = "Structurer sa page avec des intertitres, utiliser le bon type de liste, ajouter des emphases faibles ou forte ou des séparateurs. Le web est sémantique quand il est clair (ou l'inverse)."
date = 2025-08-11
draft = true

+++

Je viens de voir la page [Why Semantic HTML Matters For SEO And AI](https://www.searchenginejournal.com/why-semantic-html-matters-for-seo-and-ai/553197/) dans mon agrégateur de flux.
Comme je parle de texte sur ce blog, je me dis qu'une version simplifiée pourrait être utile (et suffisante).

Je signale en passant que je propose des pages qui ont un sens.
Mais je ne le fais ni pour le référencement (SEO) dans les moteurs de recherche, ni pour les intelligences artificielles (IA).
Je publie des pages sémantiquement correctes pour les internautes.
Et en particulier pour améliorer l'accessibilité (A11Y) pour celles et ceux qui ont le plus de difficultés.

## Structure générale de la page

En principe, la structure générale de la page est gérée par votre système de gestion de contenu (CMS).
Si vous n'avez pas décidé de faire n'importe quoi, si l'agence en charge de votre site ne code pas avec les pieds, tous les éléments de structure sont corrects.

Donc, tout ce qui porte sur `header`, `main`, `footer`, `article`, etc. n'a même pas besoin d'être lu dans l'article d'origine.

Contentez-vous de faire du bon boulot *dans* votre page ou votre article, dans sa partie rédactionnelle.

## Structure des publications

Toute publication a un titre, qui est automatiquement balisé `h1`. 
Il n'y a rien à faire, tout est automatique.

Ensuite, vous *pouvez* structurer votre billet avec des intertitres.
Ils sont de niveau `h2` à `h6`.
Dans la majorité des cas, vous pourrez vous contenter de `h2`, voire de `h3`.
Ces intertitres ne sont pas des éléments graphiques, ce sont des éléments sémantiques (qui se distinguent graphiquement du reste du texte).
Dans WordPress, il est facile de vérifier l'enchaînement logique lors de la rédaction (par l'onglet «Structure»).

Quand les intertitres souvent utilisés (par exemple `h2`) ont une apparence qui pose problème, n'essayez pas d'en changer dans l'éditeur.
Soit vous pouvez les modifier à l'échelle du site, soit un développeur ou une développeuse le fera en quelques lignes de CSS.

## Listes

Si on liste une série d'éléments, il faudrait toujours proposer une **vraie liste** (et pas des sauts de ligne ou de simples tirets):

- la liste non ordonnée (comme celle-ci) donne des éléments dans un ordre qui n'a pas de forcément de sens
- la liste ordonnée (souvent avec des numéros) donne toujours une liste d'étapes ou une ensemble d'éléments pour lequel l'ordre est important

Un exemple culinaire tout simple:

- les ingrédients (qui n'ont pas d'ordre mais doivent tous être disponibles) constituent une liste à puces non ordonnée
- les étapes de la recette suivent un ordre (donc une liste numérotée)

N'hésitez jamais à proposer des listes sur vos pages, c'est très lisible et efficace, sur grand écran comme sur un téléphone.

## Mises en évidence

À proprement parler, l'italique et le gras n'existent presque plus sur le web.
Et pourtant, vous voyez souvent du **gras** et de l'*italique*.
Je m'explique.

Historiquement, l'italique était produit par la balise `i` et le gras par la balise `b` (bold).
C'étaient 2 informations de mise en forme «visuelle» plutôt que de sens.

Aujourd'hui, elles ont été «remplacées» (même si elles existent toujours) par des balises sémantiques:

`em`
: pour mise en évidence (emphasis), représentée par défaut en italique

`strong`
: pour mise en évidence forte, représentée par défaut en gras

Quand vous faites de l'italique, c'est que vous mettez les mots en évidence (emphase).
Quand vous faites du gras, c'est que vous insistez fortement (strong) sur quelque chose.
Il faut avoir conscience que les représentations visuelles de ces éléments pourraient n'être ni italique ni gras, Mais, par exemple, des surlignement de couleurs différentes.

Au passage, la liste ci-dessus est une liste de définitions (`dl`).
Elle distingue le mot défini (`dt`) de sa définition (`dd`).
Elle n'est malheureusement pas disponible dans tous les CMS.
WordPress ne la propose pas par défaut, alors qu'elle produit vraiment du sens.

## Liens

Je ne développe pas sur la pertinence des liens qui sont la base du web.
Mais je souligne que, d'un point de vue sémantique, le texte sur lequel s'applique le lien (ancre) est important.
Les «cliquez ici», voire «ici», sont horribles, posent des problèmes d'accessibilité et sont sématiquement faibles.

La [règle Opquast 132](https://checklists.opquast.com/fr/assurance-qualite-web/le-libelle-de-chaque-lien-decrit-sa-fonction-ou-la-nature-du-contenu-vers-lequel-il-pointe) est claire:

> Le libellé de chaque lien décrit sa fonction ou la nature du contenu vers lequel il pointe.

Si c'est votre référencement qui vous intéresse, des bons liens sont votre outil le plus puissant.

## Citations

J'en ai profité pour ajouter une citation, qui a aussi valeur sémantique.
Elle n'est pas un texte *formaté* différemment, mais une balise `blockquote`.
C'est parce qu'il est balisé ainsi qu'il est *présenté* différemment.

WordPress et son éditeur Gutenberg permettent de proposer de belles mises en forme des citations.
Mais avant de bricoler et de faire de la mise en page, attribuez toujours le type «citation» (et non simplement «paragraphe») au texte!

----

J'ajoute --- après ce séparateur `hr`, qui a aussi une valeur sémantique en HTML (et qui existe dans WordPress) –-- que les sauts de lignes ne remplacent pas les paragraphes.
Et que le soulignement est strictement [réservé aux liens](https://checklists.opquast.com/fr/assurance-qualite-web/le-soulignement-est-reserve-aux-liens) (Opquast 134).

Il y a tous les éléments utiles sur cette page.
Vous n'avez besoin de rien d'autre pour proposer un contenu structuré, sématique, lisible et accessible.

----

J'allais oublier...
Pour les images, ajoutez impérativement un texte alternatif `alt` pour aider les personnes atteintes de déficiences visuelles.
