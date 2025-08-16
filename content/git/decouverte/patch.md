+++
title = "Appliquer des corrections avec patch"
weight = 60
+++

patch permet de créer un fichier spécial qui comprend une série de
modifications à faire.

Au départ, cette procédure visait à appliquer des petites corrections
pour corriger rapidement un bug. Mais l’utilisation peut être élargie.

## Qu’est-ce qu’un patch?

Lorsque nous avons deux version différentes de notre corpus, référencées
par deux commits distincts, nous pouvons faire un diff pour lister
toutes les différentes entre ces versions.

Un patch se présente de manière très proche: il liste ce qui est modifié
dans des fichiers, sous forme d’ajouts et de suppressions. Remarque:
une modification, au sens courant, n’est qu’une suppression suivie
d’un ajout.

Un patch, c’est donc un semble d’opérations qui permettent de
reproduire le passage d’un état à un autre sur tout un corpus.

::: note
::: title
Note
:::

Nous verrons au cours de cette documentation que des outils beaucoup
plus puissants que le patch existent. Pourtant, il reste d’actualité
pour deux raisons principales:

> -   Parce qu’il permet de proposer des modifications sans n’avoir
>     aucun droit sur un dépôt (cf. Bob ci-dessous).
> -   Parce qu’il peut être envoyé par mail, par exemple dans une
>     institution dans laquelle certains sites ou protocoles sont
>     bloqués.
:::

## Quand Bob contacte Alice

Nous l’avons vu, Bob s’est mis à suivre le travail d’Alice en suivant
tous les commits de son dépôt. Bob est très heureux de cela, mais il
aimerait maintenant essayer d’aider Alice dans son travail.

Bob va donc mettre son dépôt à jour. Puis il va corriger un certain
nombre de coquilles, modifier quelques passages, ajouter une référence
bibliographique.

Une fois tout ce travail effectué, Bob est bien embarrassé. Il souhaite
en faire profiter Alice mais ne peut pas écrire dans le dépôt du serveur
distant.

Il va donc créer un patch qu’il va envoyer par mail à Alice. C’est
pour eux l’occasion de faire connaissance.

Avec ce patch en sa possession, Alice peut voir rapidement ce que Bob
propose comme modifications. Tout est clair, elle n’a pas à relire des
notes manuscrites ou essayer de comprendre ce qui est dit dans un mail.
Tout est parfaitement *codé*:

-   Quelle ligne disparaît?
-   Quelle ligne est remplacée par une autre?
-   Quelle ligne est ajoutée?

Si le patch de Bob est bien fait, Alice peut l’appliquer très
simplement. Toutes les modifications proposées par Bob sont ainsi
faites, en quelques secondes, quel qu’en soit le nombre, et sur
plusieurs fichiers!
