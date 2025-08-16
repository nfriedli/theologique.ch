+++
title = "Petit Git illusté"
description = ""
date = 2025-08-14
draft = true
+++

Git est un logiciel de gestion de versions décentralisé.
Il a profondément changé ma manière de travailler sur des textes et des sites web.
J’essaie ici d’illustrer ce que peut apporter Git pour le travail personnel et la collaboration.
Je donne des exemples simples et pratiques en théologies et sciences humaines.

Ce n’est pas un tutoriel ou un guide, je ne détaille pas la mise en pratique.
Ce document reprend de vielles notes.
**Sa réactualisation est en cours.**

## Introduction

La révision de versions répond à un certain nombre de questions classiques du développement logiciel:

- Comment conserver un historique de toutes les étapes de développement?
- Comment comparer facilement deux fichiers à des étapes différentes?
- Comment travailler en commun sur un projet complexe?
- Comment tester des pistes sans prendre le risque de tout casser?
- Comment proposer des modifications à un projet auquel on ne participe   pas avant?

Même si les documents diffèrent fortement entre code informatique et travaux de sciences humaines, les grandes questions restent identiques.

Comment utiliser Git, un logiciel de référence dans le développement informatique, dans un contexte de science humaines, théologie, humanités numériques, etc.?

## Définitions de travail

Pour mieux savoir de quoi nous parlons dans cette documentation, voici quelques définitions:

fichier  
: Un simple fichier texte, par exemple au format [texte](/blog/txt/) ou [Markdown](/blog/markdown/), comprenant une partie des données.

corpus  
: Ensemble de fichiers, classés ou non dans différents répertoires.

racine  
: Répertoire dans lequel se trouve tout le corpus, contient des fichiers et peut-être des sous-répertoires.

projet  
: Évolution du corpus dans la durée et au gré des différentes manipulations.

dépot  
: Espace d’hébergement sur un serveur.

## Remarque sur le vocabulaire

Cette page contient un grand nombre d’anglicismes ou de traductions discutables.

C’est un choix justifié et assumé pour 3 raisons:

- Les termes en anglais sont aussi les commandes du logiciel utilisé.
  Cela signifie que votre vie sera simplifiée ensuite si le vocabulaire est déjà acquis.
- Il n’y a pas consensus pour un certain nombre de termes.
  D’autres sont quasiment impossibles à traduire.
- Le travail communautaire, passant sur les barrières des langues, est simplifié s’il y a dès le débart un vocabulaire commun.

Nous essayerons de nous limiter aux anglicismes qui correspondent aux commandes, en supprimant les autres.

### Alice et Bob (et Charles)

Alice et Bob sont des figures connues en informatique.

Lorsqu’il faut illustrer des exemple de communication ou de travail à deux, Alice et Bob sont appelés à la rescousse.

Nous allons donc travailler avec ces deux personnes, que nous présenterons ci-dessous.
Parfois, une troisième, Charles, arrivera en renfort pour l’illustration des exemples complexes.

Alice  
: Professeure de Nouveau Testament à l’université de la ville d’Alicestadt, en Allemagne.
  Alice est spécialiste des évangiles synoptiques.
  Elle a la responsabilité du cours d’introduction au Nouveau Testament.

Bob  
: Professeur de Nouveau Testament lui aussi, dans une école américaine de la ville de Bobtown.
  Bob est spécialisé dans les épîtres de Paul.
  Il hésite entre utiliser un livre d’introduction au Nouveau Testament existant ou écrire entièrement la sienne.

Charles  
: Étudiant en histoire de l’art à Charleville(-Mézières).
  Charles s’intéresse particulièrement aux scènes de crucifixion.
  Il peine à trouver une introduction au Nouveau Testament adaptée aux étudiants en Lettres.

## Choix du Nouveau Testament

L’idée de prendre comme corpus d’exemple un cours d’introduction au Nouveau Testament se justifie:

- parce que l’auteur principal de cette documentation est théologien et que c’est une matière qu’il connaît
- parce que le Nouveau Testament constitue en soi un corpus diversifié et intéressant qui se prêtera bien aux exemples donnés

## La brique de base: `commit`

commit (qui pourrait avoir un autre nom) est l’aspect le plus fondamental de tout système de gestion de version.
Effectuer un `commit` ou «commiter», c’est prendre une photographie de l’ensemble du corpus à un instant donné.

### Éléments du `commit`

La particularité du `commit`, c’est qu’il est composé d’un ensemble d’éléments:

- la photographie elle-même, de tous les fichiers du corpus, où qu’ils se trouvent dans le répertoire racine
- le nom et l’email de la personne qui le fait
- un message, qui explique sur quoi il porte
- sa date
- une somme de contôle `SHA1`, c’est-à-dire une clé unique qui permet de l’identifier parmi l’ensemble des commits

### Faire de la prose sans le savoir

Dans l’usage informatique courant, on effectue parfois des opérations qui ressemblent à un suivi de versions sans le savoir:

- lorsque l’on enregistre un même fichier avec des noms distincts (un numéro de version ou la date dans le nom de fichier)
- lorsque l’on sauve tout notre répertoire de travail chaque soir
- lorsque l’on utilise un système de sauvegarde comme Time Machine sur Mac

Pourtant, ces outils sont beaucoup plus limités que ce dont nous parlons ici:

- les différents noms de fichiers nous compliquent la vie (de plus en  plus de fichiers dans le répertoire, une logique propre à chacun·e)
- la sauvegarde vespérale qui regroupe toutes les modifications d’une journée sans donner plus de détails
- un système qui fonctionne en tâche de fond sans que l’on sache à quel moment il effectue les sauvegardes

### Particularités du `commit`

La particularité du `commit`, c’est d’être appliqué à chaque fois qu’un ensemble de modifications dans le corpus a lieu.
Son intérêt est de commenter ce qui a été fait, de le dater et de regrouper des actions similaires.

Quelques exemples:

- l’ajout d’un nouveau passage complet justifie un `commit`
- l’uniformisation d’une abréviation dans tout le corpus
- la correction d’une incohérence ou d’une coquille à un seul endroit

On choisit donc de regrouper dans un même `commit`, qui est une action manuelle, ce qui a été modifié depuis le dernier `commit`.
Nous verrons plus loin en quoi cela est important et utile.

**Note.**
Il est important de ne pas modifier le nom du ficher au moment des sauvegardes.
Un fichier garde un même nom mais est disponible en plusieurs versions.
On ne remplit donc pas son répertoire de travail de nouveaux fichiers de sauvegarde.
Les changements de noms seront expliqués plus loin.

### Le travail d’Alice

Alice a donc décidé de suivre l’évolution de son corpus, son cours de Nouveau Testament, dans un système de gestion de version.
Nous nous intéresseront plus tard à ce qu’elle a fait pour commencer le processus.
Rejoignons-la pour le moment à un «moment m» de son travail de rédaction.

Avant chaque cours qu’elle donnera devant ses étudiants, Alice relit le passage qu’elle présentera un jour donné.

Elle le corrige, le modifie, y ajoute des parties:

- Elle découvre un coquille dans une référence biblique dans la présentation du jour.
  Elle corrige donc donc la coquille, dans un seul fichier, et effectue un `commit`, avec un message «Correction verset X».
- Puis elle décide d’ajouter une référence bibliographique.
  Elle modifie donc deux fichiers: celui relatif au cours en question qui renvoie à une référence et le fichier de bibliographie dans lequel elle ajoute la référence complète.
  Elle effectue un seul `commit` (même s’il y a plusieurs fichiers), avec le message «Ajout référence Y».
- Enfin, elle décide d’inverser deux parties de sa présentation.
  Elle copie et colle les parties de texte et effectue un `commit`: «Nouvel ordre de présentation».

## Les différences: `diff`

`diff`, c’est la commande qui nous permet de comparer facilement les différences deux versions du corpus.

Nous avons vu dans le passage sur le `commit` que chaque photographie du corpus est identifiée par un code unique.
C’est lui qui nous servira à travailler ici.

À partir du moment où chaque `commit` est correctement effectué, nous pouvons facilement en retrouver la liste.
De manière antéchronologique, nous pouvons savoir qui a modifié le corpus, quand, et pourquoi (d’où l’importance des messages).

### `diff` entre deux commits

Une fois cette liste à ma disposition, je peux aisément lister tout ce
qui a été ajouté, et tout ce qui été supprimé, entre deux commits
quelconques.

Quels sont les intérêts de cet outil?

- Il n’est pas obligatoire de travailler entre deux versions successives du document.
  Donc, il est possible de comparer les version de mars 2012 avec octobre 2012, même si je suis en 2013 et qu’il y a eu beaucoup de modifications ensuite.
- La comparaison porte sur tous les fichiers modifiés du corpus.
  Donc, il n’est pas nécessaire de comparer fichier après fichier.
- Il est possible de comparer différentes version d’un seul
  fichier, s’il n’est pas souhaitable de s’intéresser à l’ensemble du
  corpus.

### `diff` avant le `commit`

Il est aussi possible de visualiser simplement toutes les modifications
sur tout le corpus (ou un seul fichier) avant d’effectuer un `commit`.

En en précisant pas sur quoi porte le `diff`, on liste:

- tout ce qui a été modifié depuis le dernier `commit`
- donc tout ce qui n’a pas encore commité

Cette fonction est très utile pour savoir exactement ce qui va entrer
dans le nouveau `commit`, et quel est le message le plus adapté pour décrire ces modifications.

**Note.**
Git, l’outil que nous utiliserons dans la suite de ce document, permet plus de finesses dans le choix de ce qui va être commité.
Il est pourtant trop tôt pour en parler ici et c’est par choix
que nous simplifions le propos.

### Le travail d’Alice

Comme Alice effectue un suivi de versions de son cours de Nouveau Testament, elle peut donc utiliser `diff` à l’envi.

Supposons qu’elle a distribué l’ensemble de son cours en version papier.
Elle peut, à chaque moment et de manière triviale, lister toutes les modifications entre sa version de travail et la version papier.

Comme elle donne ce cours chaque année, il lui est possible, en effectuant un `diff` sur sa bibliographie, de lister tous les livres ajoutés depuis l’année précédente.
Et demander au service de bibliothèque de s’assurer que tous les livres, et les nouvelles éditions, font bien partie du catalogue.

**Note.**
Nous verrons plus tard que pour identifier des version très précise du corpus, la notion de tag est encore plus efficace...
Patience!

## Cloner un dépôt avec... `clone`

Les deux passages précédents présentaient deux actions courantes.

On effectue un `commit` à chaque modification qui le mérite et un `diff` très souvent, pour voir ce qui a été modifié, ce qui sera commité, etc.

Avec clone, nous parlons d’une action beaucoup plus rare.
Elle
intervient en principe une seule fois en tout début de processus.

Pourtant, nous avons décidé d’en parler plus tard parce qu’elle est
incompréhensible sans avoir saisi ce qu’est un `commit`.

### Cloner quoi?

La fonction de `clone`, c’est de copier l’ensemble d’un projet ailleurs.
Mais c’est beaucoup plus qu’une simple copie de répertoire.

En clonant un dépôt, on copie:

- L’ensemble des répertoires et fichiers compris dans la racine.
C’est
  plus ou moins l’équivalent d’un copier-coller sur votre ordinateur.
- Mais aussi l’ensemble des commits (avec leurs messages, `SHA1`, date
  et auteur).
- Et aussi toutes les branches.
(Voir XXX)

Dit en langage courant, en clonant un dépôt, je copie le texte, l’histoire du texte et les commentaires à l’histoire du texte.

### Cloner pourquoi?

Il y a deux raisons pour cloner un dépôt:

- Pour le copier à un autre endroit: par exemple sur mon ordinateur fixe et mon ordinateur portable.
- Pour permettre à d’autres personnes de le posséder et le suivre.
  En d’autres termes, pour participer, passivement ou activement, au projet d’autrui.

Une fois le dépôt cloné à un nouvel endroit, cette commande ne sera plus utilisée.
On suivra les commits d’une autre manière.

### Et `init`, on n’en parle pas?

Sachez simplement que pour tout travail avec un système de suivi de versions, il faut amorcer la machine.
Tout projet aura, une fois, été initialisé avec `init`.

Si vous clonez un projet, vous n’utiliserez jamais `init`.
J’en parlerai si je rédige un tutoriel ou un guide à l’avenir.

### Le travail d’Alice

Alice travaille son cours de Nouveau Testament à coup de `commit` et de `diff`, comme nous l’avons vu plus tôt.
Comme elle est séduite par l’efficacité de cet outil, elle a décidé d’aller un peu plus loin.
Elle a donc placé l’ensemble de son projet sur un serveur.

Alice vient de s’acheter un nouvel ordinateur portable.
Elle clone sur son ordinateur le dépôt situé sur le serveur.

Elle dispose désormais de 3 copies de l’ensemble de son projet, comprenant tout le corpus et son histoire commentée:

- une sur son ordinateur de bureau
- une sur le serveur distant
- une sur son nouveau portable

Comme `clone` reprend l’ensemble des commits, les 3 versions sont absolument identiques.
La sécurité du projet est désormais (presque) assurée, puisque la survie d’un seul dépôt permet de le cloner ensuite vers d’autres machines.

**Note.**
Tous les dépôt clonés à partir d’un serveur se souviennent d’où ils viennent.
Un clone est donc très différent d’une simple copie, puisqu’il reste lié à son origine.
Ce sera très important pour la suite.

### Et Bob débarque

Bob, qui connaît les travaux d’Alice, vient d’apprendre qu’elle a (enfin) placé son cours sur un serveur distant.
Il va donc cloner le dépôt sur son propre ordinateur (avec une identification sécurisée ou un accès libre, selon ce qu’Alice a choisi).

Bob, à l’autre bout du monde, dispose maintenant du même dépôt qu’Alice sur son propre portable.
Il a l’occasion de voir l’évolution des différentes parties du cours dans la durée.
Et les messages de `commit` d’Alice lui permettent de comprendre le pourquoi de ces évolutions.

**Note.**
Si, pour une raison difficilement explicable, Alice perdait simultanément ses trois versions du projet, celle de Bob constituerait une sauvegarde supplémentaire!

## Rapatrier des nouveautés: `pull` & `fetch`

`pull` et `fetch` sont deux moyens de rapatrier les nouveautés d’un
dépôt qui a été préalablement cloné.

Il est trop tôt pour distinguer les deux; nous parlerons donc de `pull`
pour simplifier le discours.

### À quoi sert pull?

On utilise `pull` sur un dépôt préalablement cloné (qui se souvient de son origine):

- `pull` va vérifier tous les commits présent dans ce dépôt distant d’origine
- `pull` va comparer ces commits avec ceux présents sur mon ordinateur
- `pull` va télécharger tous les commits du serveur d’origine pas encore présents sur mon ordinateur

À la fin de l’opération, le dépôt de mon ordinateur sera donc identique
à celui du serveur d’origine.
La situation est analogue à celle qui suit
immédiatement `clone`, mais seules les nouveautés ont été téléchargés.
C’est beaucoup plus rapide et beaucoup moins gourmand en ressources, en particulier pour des dépôts avec des
historiques très longs ou beaucoup de fichiers.

### Le travail d’Alice

Alice a bien avancé sur son ordinateur portable.
Elle a envoyé tous ses
commits du jour sur le serveur distant (nous verrons comment plus tard).

Actuellement, elle dispose donc de dépôts à jour sur son portable et le
serveur distant.

Le lendemain matin, arrivant au bureau, Alice effectue un pull sur son
ordinateur et, en quelques secondes, elle dispose exactement du même
dépôt que sur son portable.
Elle peut continuer à travailler ainsi.

### Bob utilise pull

Bob, nous l’avons vu, a cloné le dépôt d’Alice.
Il a lu l’ensemble du
corpus et consulté une bonne partie des commits, notamment les messages
d’accompagnement.

Bob a décidé de suivre le travail d’Alice au plus près.
Il est certain
qu’Alice prépare les cours de la nouvelle année et il est curieux.

Dès qu’il en a le temps, il effectue un `pull`.
En quelques secondes, toutes les modifications effectuées par Alice sont chargées dans son ordinateur.
Il peut désormais lire les derniers messages des commits d’Alice ainsi qu’effectuer quelques diffs pour voir quelle sont les
dernières modifications qu’elle a apportée à son cours.

Pour Bob, pas besoin de relire le cours à chaque fois pour détecter les
changements (si tant est que ce soit possible); les messages des commits
et l’outil `diff` lui montrent instantanément les dernières changements.

En quelque sorte, Bob se synchronise au travail d’Alice avec `pull`!

## Appliquer des corrections avec `patch`

`patch` permet de créer un fichier spécial qui comprend une série de modifications à faire.

Au départ, cette procédure visait à appliquer des petites corrections pour corriger rapidement un bug.
Mais l’utilisation peut être élargie.

### Qu’est-ce qu’un patch?

Lorsque nous avons deux version différentes de notre corpus, référencées par deux commits distincts, nous pouvons faire un `diff` pour lister toutes les différentes entre ces versions.

Un patch se présente de manière très proche: il liste ce qui est modifié dans des fichiers, sous forme d’ajouts et de suppressions.
Remarque: une modification, au sens courant, n’est qu’une suppression suivie d’un
ajout.

Un patch, c’est donc un semble d’opérations qui permettent de reproduire le passage d’un état à un autre sur tout un corpus.

**Note.**
Nous verrons au cours de cette documentation que des outils beaucoup plus puissants que le patch existent.
Pourtant, il reste d’actualité pour deux raisons principales:

- parce qu’il permet de proposer des modifications sans n’avoir aucun droit d’écriture sur un dépôt (cf. Bob ci-dessous)
- Parce qu’il peut être envoyé par mail, par exemple dans une institution dans laquelle certains sites ou protocoles sont bloqués

### Quand Bob contacte Alice

Nous l’avons vu, Bob s’est mis à suivre le travail d’Alice en suivant tous les commits de son dépôt.
Bob est très heureux de cela, mais il aimerait maintenant essayer d’aider Alice dans son travail.

Bob va donc mettre son dépôt à jour.
Puis il va corriger un certain nombre de coquilles, modifier quelques passages, ajouter une référence bibliographique.

Une fois tout ce travail effectué, Bob est bien embarrassé.
Il souhaite en faire profiter Alice mais ne peut pas écrire dans le dépôt du serveur distant.

Il va donc créer un patch qu’il va envoyer par mail à Alice.
C’est pour eux l’occasion de faire connaissance.

Avec ce patch en sa possession, Alice peut voir rapidement ce que Bob propose comme modifications.
Tout est clair, elle n’a pas à relire des notes manuscrites ou essayer de comprendre ce qui est dit dans un mail.
Tout est parfaitement codé:

- quelle ligne disparaît?
- quelle ligne est remplacée par une autre?
- quelle ligne est ajoutée?

Si le patch de Bob est bien fait, Alice peut l’appliquer très simplement.
Toutes les modifications proposées par Bob sont ainsi faites, en quelques secondes, quel qu’en soit le nombre, et sur
plusieurs fichiers.

## Les branches (branch)

La branche est en ensemble de commits qui divergent d’une branche principale.
L’action `branch` permet de créer un nouvelle branche en lui donnant un nom.

### C’est quoi, une branche?

Dans un projet, chaque étape est validée par un `commit`, qui marque un nouvel état de l’ensemble du corpus.
Assez souvent, cela se passe bien ainsi: on ajoute du contenu, on corrige, on modifie, on supprime.
En principe, à chaque commit, le projet est dans un état cohérent.

La création d’une branche permet de créer un nouvel environnement parfaitement identique à celui de départ.
On y travaille ensuite comme dans notre projet habituel, avec des commits.

Mais, en tout temps, on peut passer d’une branche à l’autre posséder deux versions parallèles du projet.

### Exemples d’utilisation des branches

Mais à quoi bon se compliquer la vie? À créer un environnement de travail isolé dans lequel tous les essais sont permis.

Une fois que le travail a avancé dans la branche, il y a plusieurs
possibilités:

- garder cette branche distincte et continuer avec deux projets différents parce que c’est bien ainsi
- fusionner cette branche avec la branche principale parce que l’ensemble des  modifications faites sont intéressantes et elles sont reprises
- détruire la branche parce que l’essai était infructueux

### Alice et Bob créent des branches

Alice a compris le principe de branche et l’utilise beaucoup.

Elle a depuis longtemps l’idée de modifier la structure de son cours, en gardant les mêmes fichiers.
Pour se faire, elle a créé un branche dans laquelle elle expérimente des nouvelles structures qu’elle va soumettre à ses assistant·e·s.
Mais elle conserve la structure actuelle dans une autre branche, ne souhaitent pas tout perdre.

Après quelques jours, ses assistants font déchanter Alice, qui supprime sa branche.
Elle retrouve simplement son ancienne branche, comme s’il ne s’était rien passé.

Alice pourtant souhaite faire évoluer son cours sérieusement.
Au début du semestre suivant, elle décide de travailler avec deux branches:

- Une branche de maintenance, dans laquelle Alice continue de corriger
  les erreurs qu’elle découvre.
  Ce cours est toujours utilisable en
  l’état.
- Une branche de développement, dans laquelle Alice fait évoluer son   cours de manière beaucoup plus profonde.
  Elle sait que c’est le cours   qu’elle donnera l’année prochaine, mais le projet est encore trop chaotique pour être la référence.

Bob, de son côté, utilise les branches de manières plus modeste.
À chaque fois qu’il souhaite proposer un patch à Alice, il crée une nouvelle branche.
Il multiplie les commits et, à la fin de son travail, il regroupe tous les commits de la branche dans un patch.

Il envoie le patch à Alice et, dès qu’il voit qu’Alice a appliqué tout ou partie des modifications proposées, détruit cette branche.

## Fusionner: `merge`

`merge` est l’outil qui permet de fusionner deux éléments en un seul, plutôt que de remplacer l’un par l’autre.

### Que signifie fusionner?

Il existe deux types de fusions différentes qu’il faut bien comprendre avant d’aller plus loin.

Une fusion simple, qui survient par exemple lorsque l’on a créé une branche pour expérimenter quelque chose.
Dans cette branche, un certain nombre de modification ont été commitées et le résultat est acceptable.
Il est possible de rapatrier en une fois toutes les modifications faites (en un ou plusieurs commits) sur la branche de départ (appelée `main` par défaut).
Il se se passe alors deux choses:

- les fichiers qui restent identiques sur les deux branches ne changent simplement pas
- les fichiers qui ont été modifiés sur la branche de développement (appelée, par exemple, `dev`) remplacent ceux de l’ancienne branche (`main`).

Une fusion complexe, qui survient lorsque des mêmes fichiers ont été modifiés sur les deux branches.
Si merge était un remplacement, cette opération se déroulerait comme un merge simple, et les fichiers d’une branche seraient remplacés par ceux de l’autres.
Voici ce qui se passe:

- les fichiers non modifiés sur les deux branches ne changent simplement pas
- les fichiers modifiés uniquement sur la branche de développement `dev` remplacent ceux de l’ancienne branche `main`
- les fichiers modifiés sur l’ancienne branche mais pas sur la branche de développement ne sont pas remplacés
- les fichiers modifiés sur les deux branches:
  - sont fusionnés, avec les modifications des deux branches, si elles concernent des parties différentes du fichier
  - ne sont pas fusionnés si la même partie a été modifiée de deux manières différentes (il y a conflit)

Cette approche peut sembler complexe ou abrupte, mais au contraire, elle permet d’éviter les conflits.
Ils peuvent être résolus.

### Résoudre les conflits

L’outil merge permet donc d’éviter les conflits:

- en rendant le remplacement invisible lorsqu’il est logique
- en étant minutieux lorsque le remplacement n’est pas trivial
- en ne remplaçant rien et en avertissement l’utilisateur lorsqu’il y a conflit objectif

Dans ce dernier cas, l’utilisateur hérite d’un fichier qui comprend les deux version concurrentes (deux modifications incompatibles).
Il faut alors éditer le fichier et comparer les version en en supprimant une au profit de l’autre ou en proposant une troisième solution.
Ensuite, on termine l’opération de fusion merge.

Il est important de comprendre que deux branches peuvent avancer simultanément et que les modifications des deux branches seront reprises au moment de la fusion.
Soit de manière automatique, soit manuellement, tous les conflits seront réglés.
Personne n’aura travaillé pour rien.

### Alice a bien travaillé

Alice a bien travaillé dans sa branche de développement et son cours de
l’année prochaine est désormais présentable.
Alice va donc fusionner sa
branche de développement (le cours de l’année prochaine) dans la branche
courant (le cours de cette année).

Concrètement, il se passe les choses suivantes:

- toutes sa nouvelle organisation et ses nouveaux contenus sont repris dans la branche courante (= tout le travail d’Alice est bien fusionné   avec l’ancien)
- toutes les petites modifications qu’Alice avait apportées à sa branche de l’année sont conservées, même si elles n’étaient pas dans la  branche de développement (= des modifications compatibles sont reprises sans réserve).
- dans quelques cas, Alice règle un conflit en éditant un fichier à la main (= les modifications sur les deux branches s’opposent).

Ainsi, Alice a pu travailler durant plusieurs semaines sur deux versions différentes de son cours, en conservant l’ensemble de ses efforts.

### Et Bob était triste

Bob était un peu triste.
Il suivait régulièrement les avancées du travail d’Alice, mais il n’y avait plus que quelques modifications mineures.
Bob suivait la branche de maintenance d’Alice, sans savoir qu’elle travaillait à sa branche de développement.

Bob a donc décidé de modifier certaines choses sans en faire part à Alice, pour adapter ce cours à sa pratique.

Soudain, il découvre une quantité impressionnant de modifications et ne sait comment les gérer.
Dans le monde normal, Bob avait ces choix:

- abandonner tout son travail en se disant qu’Alice à mieux travaillé que lui
- ne pas tenir compte du travail d’Alice et continuer sur sa voie
- comparer chaque fichier pour reprendre le meilleur

Comme Bob et Alice travaillent dans un monde tel qu’il devrait être, Bob va merge toutes les modifications d’Alice avec les siennes.
Ainsi, il va capitaliser le travail de deux personnes, de manière presque magique.

## Envoyer ses modifications: `push`

## Proposer des modifications (pull resquest)

Charlie entre en jeu

## Réparer ses oublis avec `amend`

## Renommer un fichier: `mv`

## Réécrire l’histoire avec `rebase`

## Une clé unique: `SHA1`
