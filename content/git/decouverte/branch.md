+++
title = "Les branches (branch)"
weight = 70
+++

La branche est en ensemble de commits qui divergent d’une branche
principale. L’action branch permet de créer un nouvelle branche.

## C’est quoi, une branche?

Dans un projet, chaque étape est validée par un commit, qui marque un
nouvel état de l’ensemble du corpus. Assez souvent, cela se passe bien
ainsi: on ajoute du contenu, on corrige, on modifie, on supprime. En
principe, à chaque commit, le projet est dans un état cohérent.

La création d’une branche permet de créer un nouvel environnement
parfaitement identique à ce lui de départ. On y travaille ensuite comme
dans notre projet habituel, avec des commits.

Mais, en tout temps, on peut passer d’une branche à l’autre posséder
deux versions parallèles du projet.

## Exemples d’utilisation des branches

Mais à quoi bon se compliquer la vie? Réponse: à créer un environnement
de travail isolé dans lequel tous les essais sont permis!

Une fois que le travail a avancé dans la branche, il y a plusieurs
possibilités:

-   Garder cette branche distincte: continuer avec deux projets
    différents parce que c’est mieux ainsi.
-   Fusionner cette branche avec la branche principal: l’ensemble des
    modifications faites sont intéressantes et elles sont reprises.
-   Détruire la branche: parce que l’essai était infructueux.

## Alice et Bob créent des branches

Alice a compris le principe de branche et l’utilise beaucoup.

Elle a depuis longtemps l’idée de modifier la structure de son cours,
en gardant les mêmes fichiers. Pour se faire, elle a créé un branche
dans laquelle elle expérimente des nouvelles structures qu’elle va
soumettre à ses assistants. Mais elle conserve la structure actuelle
dans une autre branche, ne souhaitent pas tout perdre.

Après quelques jours, ses assistants font déchanter Alice, qui supprime
sa branche. Elle retrouve simplement son ancienne branche, comme s’il
ne s’était rien passé.

Alice pourtant souhaite faire évoluer son cours sérieusement. Au début
du semestre suivant, elle décide de travailler avec deux branches:

-   Une branche de maintenance, dans laquelle Alice continue de corriger
    les erreurs qu’elle découvre. Ce cours est toujours utilisable en
    l’état.
-   Une branche de développement, dans laquelle Alice fait évoluer son
    cours de manière beaucoup plus profonde. Elle sait que c’est le
    cours qu’elle donnera l’année prochaine, mais le projet est encore
    trop chaotique pour être la référence.

Bob, de son côté, utilise les branches de manières plus modeste. À
chaque fois qu’il souhaite proposer un patch à Alice, il crée une
nouvelle branche. Il multiplie les commits et, à la fin de son travail,
il regroupe tous les commits de la branche dans un patch.

Il envoie le patch à Alice et, dès qu’il voit qu’Alice a appliqué tout
ou partie des modifications proposées, détruit cette branche.
