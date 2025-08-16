+++
title = "Fusionner: merge"
weight = 80
+++

merge est l’outil qui permet de fusionner deux éléments en un seul,
plutôt que de remplacer l’un par l’autre.

## Que signifie fusionner?

**À voir: comment nommer ces branches pour être plus clair\...**

Il existe deux fusions différentes qu’il faut bien comprendre avant
d’aller plus loin.

Une fusion simple, qui survient par exemple lorsque l’on a créé une
branche pour expérimenter quelque chose.
Dans cette branche, un certain
nombre de modification ont été commités et le résultat est acceptable.
Il est possible de rappatrier en une fois toutes les modifications
faites (en un ou plusieurs commits) sur la branche de départ.
Il se se
passe alors deux choses:

-   Les fichiers qui restent identiques sur les deux branches ne
    changent simplement pas
-   Les fichiers qui ont été modifiés sur la branche de développement
    remplacent ceux de l’ancienne branche.

Une fusion complexe, qui survient lorsque des mêmes fichiers ont été
modifiés sur les deux branches! Si merge était un remplacement, cette
opération se déroulerait comme un merge simple, et les fichiers d’une
branche seraient remplacés par ceux de l’autres.
Voici ce qui se passe:

-   Les fichiers non modifiés sur les deux branches ne changent
    simplement pas.

-   Les fichiers modifiés uniquement sur la branche de développement de
    départ remplacent ceux de l’ancienne branche.

-   Les fichiers modifiés sur l’ancienne branche mais pas sur la
    branche de développement ne sont pas remplacés.

-   Les fichiers modifiés sur les deux branches:

    > -   sont fusionnés, avec les modifications des deux branches, si
    >     elles concernent des parties différentes du fichier,
    > -   ne sont pas fusionnés si la même partie a été modifée de deux
    >     manières différentes: il y a conflit!

Cette approche peut sembler complexe ou abrupte, mais au contraire, elle
permet d’éviter ou de résoudre les conflits, voyons comment.

## Résoudre les conflits

L’outil merge permet donc d’éviter les conflits:

-   en rendant le remplacement invisible lorsqu’il est logique
-   en étant minutieux lorsque le remplacement n’est pas trivial
-   en ne remplaçant rien et en avertissement l’utilisateur lorsqu’il
    y a conflit objectif

Dans ce dernier cas, l’utilisateur hérite d’un fichier qui comprend
les deux version concurrentes (deux modifications incompatibles).
Il
agit alors manuellement, en en supprimant une au profit de l’autre ou
en proposant une troisième solution.
Ensuite, il termine l’opération de
fusion merge.

Il est important de comprendre que deux branches peuvent avancer
simultanément et que les modifications des deux branches seront reprises
au moment de la fusion.
Soit de manière automatique, soit manuellement,
tous les conflits seront réglés.
Personne n’aura travaillé pour rien!

## Alice a bien travaillé

Alice a bien travaillé dans sa branche de développement et son cours de
l’année prochaine est désormais présentable.
Alice va donc fusionner sa
branche de développement (le cours de l’année prochaine) dans la
branche courant (le cours de cette année).

Concrètement, il se passe les choses suivantes:

-   Toutes sa nouvelle organisation et ses nouveaux contenus sont repris
    dans la branche courante (= tout le travail d’Alice est bien
    fusionné avec l’ancien).
-   Toutes les petites modifications qu’Alice avait apportées à sa
    branche de l’année sont conservées, même si elles n’étaient pas
    dans la branche de développement (= des modifications comppatibles
    sont reprises sans réserve).
-   Dans un ou deux cas, Alice règle un conflit en éditant un fichier à
    la main (= les modifications sur les deux branches s’opposent).

Ainsi, Alice a pu travailler durant plusieurs semaines sur deux versions
différentes de son cours, en conservant l’ensemble de ses efforts!

## Et Bob était triste

Bob était un peu triste.
Il suivait régulièrement les avancées du
travail d’Alice, mais il n’y avait plus que quelques modifications
mineures.
Bob suivait la branche de maintenance d’Alice, sans savoir
qu’elle travaillait à sa branche de développement.

Bob a donc décidé de modifier certaines choses sans en faire part à
Alice, pour adapter ce cours à sa pratique.

Soudain, il découvre une quantité impressionnant de modifications et ne
sait comment les gérer.
Dans le monde *normal*, Bob avait ces choix:

-   Abandonné tout son travail en se disant qu’Alice à meieux travaillé
    que lui.
-   Ne pas tenir compte du travail d’Alice et continuer sur sa voie.
-   Comparer chaque fichier pour reprendre le meilleur\...

Comme Bob et Alice travaillent dans un monde tel qu’il devrait être,
Bob va merge toutes les modifications d’Alice avec les siennes.
Ainsi,
il va capitaliser le travail de deux personnes, de manière presque
magique!
