+++
title = "Rapatrier des nouveautés: pull & fetch"
weight = 50
+++

pull et fetch sont deux moyens de rapatrier les nouveautés d’un dépôt
qui a été préalablement cloné.

Il est trop tôt pour distinguer les deux; nous parlerons donc de pull
pour simplifier le discours.

## À quoi sert pull?

On utilise pull sur un dépôt préalablement cloné (qui se *souvient de
son origine*):

-   pull va vérifier tous les commits préesent dans ce dépôt distant
    d’origine
-   pull va comparer ces commits avec ceux présents sur mon ordinateur
-   pull va télécharger tous les commits du serveur d’origine (mais pas
    encore sur mon ordinateur) sur mon ordinateur

À la fin de l’opération, le dépôt de mon ordinateur sera donc identique
à celui du serveur d’origine. La situation est analogue à celle qui
suit immédiatement clone, mais seules les nouveautés ont été
téléchargés; c’est beaucoup plus rapide, en particulier pour des dépôts
avec des historiques très longs ou beaucoup de fichiers.

## Le travail d’Alice

Alice a bien avancé sur son ordinateur portable. Elle a envoyé tous ses
commits du jour sur le serveur distant (nous verrons comment plus tard).

Actuellement, elle dispose donc de dépôts à jour sur son portable et le
serveur distant.

Le lendemain matin, arrivant au bureau, Alice effectue un pull sur son
ordinateur et, en quelques secondes, elle dispose exactement du même
dépôt que sur son portable. Elle peut continuer à travailler ainsi.

## Bob utilise pull

Bob, nous l’avons vu, a cloné le dépôt d’Alice. Il a lu l’ensemble du
corpus et consulté une bonne partie des commits, notamment les messages
d’accompagnement.

Bob a décidé de suivre le travail d’Alice au plus près. Il est certain
qu’Alice prépare les cours de la nouvelle année et il est curieux.

Dès qu’il en a le temps, il effectue un pull. En quelques secondes,
toutes les modifications effectuées par Alice sont chargées dans son
ordinateur. Il peur désormais lire les derniers messages des commits
d’Alice ainsi qu’effectuer quelques diffs pour voir quelle sont les
dernières modifications qu’elle a apportée à son cours.

Pour Bob, pas besoin de relire le cours à chaque fois pour détecter les
changements (si tant est que ce soit possible); les messages des commit
et l’outil diff lui montrent instantanément les dernières changements.

En quelque sorte, Bob se synchronise au travail d’Alice avec pull!
