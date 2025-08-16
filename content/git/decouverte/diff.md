+++
title = "Les différences: diff"
weight = 30
+++

diff, c’est la commande qui nous permet de comparer facilement les
différences deux versions du corpus.

Nous avons vu dans le passage `commit`{.interpreted-text role="doc"} que
chaque photographie du corpus est identifiée par un code unique.

C’est lui qui nous servira à travailler ici.

À partir du moment où chaque commit est correctement effectué, nous
pouvons facilement en retrouver la liste. De manière antéchronologique,
nous pouvons savoir qui a modifié le corpus, quand, et pourquoi (d’où
l’importance des messages).

## diff entre deux commits

Une fois cette liste à ma disposition, je peux aisément lister tout ce
qui a été ajouté, et tout ce qui été supprimé, entre deux commits
quelconques.

Quels sont les intérêts de cet outil?

-   Il n’est pas obligatoire de travailler entre deux versions
    successives du document. Donc, il est possible de comparer les
    version de mars 2012 avec octobre 2012, même si je suis en 2013 et
    qu’il y a eu beaucoup de modifications ensuite.
-   La comparaison porte sur tous les fichiers modifiés du corpus. Donc,
    il n’est pas nécessaire de comparer fichier après fichier.
-   Il est aussi possible de comparer différentes version d’un seul
    fichier, s’il n’est pas souhaitable de s’intéresser à l’ensemble
    du corpus!

## diff avant le commit

Il est aussi possible de visualiser simplement toutes les modifications
sur tout le corpus (ou un seul fichier) avant d’effectuer un commit.

En en précisant pas sur quoi porte le diff, on liste:

-   Tout ce qui a été modifié depuis le dernier commit.
-   Donc tout ce qui n’a pas encore commité.

Cette fonction est très utile pour savoir exactement ce qui va entrer
dans le nouveau commit, et quel est le message le plus adapté pour
décrire ces modifications.

::: note
::: title
Note
:::

git, l’outil que nous utiliserons dans la suite de ce document, permet
plus de finesses dans le choix de ce qui va être commité. Il est
pourtant trop tôt pour en parler ici et c’est par choix que nous
simplifions le propos.
:::

## Le travail d’Alice

Comme Alice effectue un suivi de versions de son cours de Nouveau
Testament, elle peut donc utiliser diff à l’envi.

Supposons qu’elle a distribué l’ensemble de son cours en version
papier. Elle peut, à chaque moment et de manière trivial, lister toutes
les modifications entre sa version de travail et la version papier.

Comme elle donne ce cours chaque année, il lui est possible, en
effectuant un diff sur sa bibliographie, de lister tous les livres
ajoutés depuis l’année précédente. Et demander au service de
bibliothèque de s’assurer que tous les livres, et les nouvelles
éditions, font bien partie du catalogue.

::: note
::: title
Note
:::

Nous verrons plus tard que pour identifier des version très précise du
corpus, la notion de tag est encore plus efficace\... Patience!
:::
