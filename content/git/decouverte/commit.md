+++
title = "La brique de base: commit"
weight = 20
+++

commit est l’aspect le plus fondamental de tout système de gestion de
version.
Effectuer un commit ou commiter, c’est prendre une
photographie de l’ensemble du corpus à un instant donné.

## Éléments du commit

La particularité du commit, c’est qu’il est composé d’un ensemble
d’éléments:

-   la photographie elle-même, de tous les fichiers du corpus, où
    qu’ils se trouvent dans le répertoire racine
-   le nom et l’email de la personne qui le fait
-   un message, qui explique sur quoi il porte
-   sa date
-   une somme de contôle SHA1, c’est-à-dire une clé unique qui permet
    de l’identifier parmi l’ensemble des commits

## Faire de la prose sans le savoir

Dans l’usage informatique courant, on effectue parfois des opérations
qui ressemblent à un suivi de versions sans le savoir:

-   lorsque l’on enregistre un même fichier avec des noms distincts: un
    numéro de version ou la date dans le nom de fichier
-   lorsque l’on sauve tout notre répertoire de travail chaque soir
-   lorsque l’on utilise un système de sauvegarde comme Time Machine
    sur Mac

Pourtant, ces outils sont beaucoup plus limités que ce dont nous parlons
ici:

-   les différents noms de fichiers nous compliquent la vie: de plus en
    plus de fichiers dans le répertoire, une logique propre à chacun.
-   la sauvegarde vespérale qui regroupe toutes les modifications d’une
    journée sans donner plus de détails
-   un système qui fonction sans que l’on sache à quel moment il
    effectue les sauvegardes


## Particularités du commit

La particularité du commit, c’est d’être appliqué à chaque fois qu’un
ensemble de modifications dans le corpus a lieu.
Son intérêt est de
commenter ce qui a été fait, de le dater et de regrouper des actions
similaires.
Quelques exemples:

-   L’ajout d’un nouveau passage complet justifie un commit
-   L’uniformisation d’une abréviation dans tout le corpus
-   La correction d’une incohérence ou d’une coquille à un seul
    endroit

On choisit donc de regrouper dans un même commit, qui est une action
manuelle, ce qui a été modifié depuis le dernier commit.
Mous verrons
plus loin en quoi cela est important et utile.

**Note.**
Il est important de ne pas modifier le nom du ficher au moment des
sauvegardes.
Un fichier garde un même nom mais est disponible en
plusieurs versions; on ne remplit donc pas son répertoire de travail de
nouveaux fichiers de sauvegarde! Les changements de noms seront
expliqués plus loin.

## Le travail d’Alice

Alice a donc décidé de suivre l’évolution de son corpus, son cours de
Nouveau Testament, dans un système de gestion de version.
Nous nous
intéresseront plus tard à ce qu’elle a fait pour commencer le
processus.
Rejoignons-la pour le moment à un moment m de son travail de
rédaction.

Avant chaque cours qu’elle donnera devant ses étudiants, Alice relit le
passage qu’elle présentera.
Elle le corrige, le modifie, y ajoute des
parties:

-   Elle découvre un coquille dans une référence biblique dans la
    présentation du jour.
Elle corrige donc donc la coquille, dans un
    seul fichier, et effectue un commit, avec un message *Correction
    verset*.
-   Puis elle décide d’ajouter une référence bibliographique.
Elle
    modifie donc deux fichiers: celui relatif au cours en question qui
    renvoie à une référence et le fichier de bibliographie dans lequel
    elle ajoute la référence complète.
Elle effectue un seul commit
    (même s’il y a plusieurs fichiers), avec le message *Ajout
    référence...*.
-   Enfin, elle décide d’inverser deux parties de sa présentation.
Elle
    copie et colle les parties de texte et effectue un commit: *Nouvel
    ordre de présentation*.
