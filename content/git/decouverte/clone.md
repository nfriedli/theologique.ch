+++
title = "Cloner un dépôt avec... clone"
weight = 40
+++

Les deux passages précédents `commit`{.interpreted-text role="doc"} et
`diff`{.interpreted-text role="doc"} présentaient deux actions
courantes. On effectue un commit à chaque modification qui le mérite et
un diff très souvent, pour voir ce qui a été modifié, ce qui sera
commité, etc.

Avec clone, nous parlons d’une action beaucoup plus rare. Elle
intervient en principe une seule fois, et avant commit et diff.

Pourtant, nous avons décidé d’en parler plus tard parce qu’elle est
incompréhensible sans avoir saisi ce qu’est un commit.

## Cloner quoi?

La fonction de clone, c’est de copier l’ensemble d’un projet
ailleurs. Mais c’est beaucoup plus qu’une simple copie de répertoire.

En clonant un dépôt, on copie:

-   L’ensemble des répertoires et fichiers compris dans la racine.
    C’est plus ou moins l’équivalent d’un copier-coller sur votre
    ordinateur.
-   Mais aussi l’ensemble des commits (avec leurs messages, SHA1, date
    et auteur).
-   Et aussi toutes les branches. (Voir XXX)

Dit en langage courant, en clonant un dépôt, je copie le texte,
l’histoire du texte et les commentaires à l’histoire du texte!

## Cloner pourquoi?

Il y a deux raisons pour cloner un dépôt:

-   Pour le copier à un autre endroit: par exemple sur mon ordinateur
    fixe et mon ordinateur portable.
-   Pour permettre à d’autres personnes de le posséder et le suivre. En
    d’autres termes, pour participer, passivement ou activement, au
    projet d’autrui.

Une fois le dépôt cloné à un nouvel endroit, cette commande ne sera plus
utilisée. On suivra les commits d’une autre manière.

::: topic
**Et init, on n’en parle pas?**

Sachez simplement que pour tout travail avec un système de suivi de
versions, il faut *amorcer la machine*. Tout projet aura, une fois, été
commencé avec init.

Si vous clonez un projet, vous n’utiliserez jamais init. C’est
pourquoi nous n’en parlerons que dans la partie pratique.
:::

## Le travail d’Alice

Alice travaille son cours de Nouveau Testament à coup de commit et de
diff, comme nous l’avons vu plus tôt. Comme elle est séduite par
l’efficacité de cet outil, elle a décidé d’aller un peu plus loin.
Elle a donc placé l’ensemble de son projet (nous verrons comment un peu
plus tard) sur un serveur.

Alice vient de s’acheter un nouvel ordinateur portable. Elle clone donc
le dépôt situé sur le serveur sur son portable.

Elle dispose désormais de 3 copies de l’ensemble de son projet,
comprenant tout le corpus et son histoire commentée:

-   une sur son ordinateur de bureau
-   une sur le serveur distant
-   une sur son nouveau portable

Comme clone reprend l’ensemble des commits, les 3 versions sont
absolument identiques. La sécurité du projet est désormais (presque)
assurée, puisque la survie d’un seul dépôt permet de le cloner ensuite
vers d’autres machines!

::: note
::: title
Note
:::

Tous les dépôt clonés à partir d’un serveur se *souviennent d’où ils
viennent*. Un clone est donc très différent d’une simple copie,
puisqu’il reste lié à son origine.

Ce sera très important pour la suite!
:::

## Et Bob débarque

Bob, qui connaît les travaux d’Alice, vient d’apprendre qu’elle a
(enfin) placé son cours sur un serveur distant. Il va donc cloner le
dépôt sur son propre ordinateur (avec une identification sécurisée ou un
accès libre, selon ce qu’Alice a choisi).

Bob, à l’autre bout du monde, dispose maintenant du même dépôt
qu’Alice sur son propre portable. Il a l’occasion de voir l’évolution
des différentes parties du cours dans la durée. Et les messages de
commit d’Alice lui permettent de comprendre le pourquoi de ces
évolutions.

::: note
::: title
Note
:::

Si, pour une raison difficilement explicable, Alice perdait
simultanément ses trois versions du projet, celle de Bob constituerait
une sauvegarde supplémentaire!
:::
