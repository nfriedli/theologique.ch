+++
title = "Recherche interne"
description = "Proposer une recherche propre à son site en utilisant la puissance de Google. 4 lignes de codes suffisent. Ce n’est pas parfait, mais c’est efficace."
date = 2025-10-06
+++

Comme je m’appuie souvent sur les règles Opquast, je me dis que je pourrais respecter [Opquast 168](https://checklists.opquast.com/fr/qualite-numerique/le-site-propose-un-moteur-de-recherche-interne):

> Un moteur de recherche interne est proposé.

Toutefois, le moteur de recherche de theologique.ch ne sera pas interne, mais utilisera Google.
Mais il pourra être utilisé exactement comme un moteur propre au site.

## Résultat

Quand vous utilisez ce moteur de recherche, vous arrivez chez Google.
Si vous souhaitez absolument éviter ce géant du web, vous pouvez effectuer une recherche similaire dans le moteur de recherche de votre choix.

{{< search >}}

## Pourquoi une recherche externe

J’utilise un générateur de site statique (Hugo).
Ce qui signifie qu’il ne dispose pas par défaut de toute l’artillerie pour la recherche.

Bien entendu, on peut développer quelque chose de spécifique.
C’est ce que j’ai fait pour [Trouver ma paroisse](https://ma-paroisse.ch/) par exemple, avec [Fuse.js](https://www.fusejs.io/).
Et pour la [recherche de nicolasfriedli.ch](https://nicolasfriedli.ch/search/), j’utilsie [PageFind](https://pagefind.app/).

Mais je souhaite quelque chose de simple à mettre en œuvre pour theologique.ch.
C’est pourquoi je me repose sur Google.
Ce qui signifie:

- qu’il faut que les pages soient indexées pour être trouvées
- qu’il faut éviter de garder dans l’index des pages qui n’existent plus

Cette double contrainte me pousse à gérer l’indexation dans [Google Search Console](https://search.google.com/search-console/about).
Je trouve cela très bien.

Ainsi, je profite des performances de Google en 4 lignes de code.

## Code

Cette méthode est en principe utilisable sur tout site, statique comme dynamique.
N’hésitez pas à réutiliser ce code en n’oubliant pas de préciser votre nom de domaine (il faut remplacer `theologique.ch`).

```html
<form method="get" id="search-google" action="https://www.google.com/search" target="_blank">
    <input type="hidden" name="sitesearch" value="theologique.ch">
    <input type="text" name="q" maxlength="255" value="" placeholder="Recherche Google" class="form-control">
</form>
```

## Recherches avancées

Pour aller plus loin dans vos recherche, sur n’importe quel site indexé dans Google, je vous invite à consulter mon billet [Recherches Google avancées](https://nicolasfriedli.ch/blog/recherche-google-avancee/).

C’est très utile quand le moteur de recherche interne est défaillant, quand il gère mal les coquilles (*fuzzy search*) ou quand on veut affiner son travail.
Vous remarquerez que la recherche qui a lieu en utilisant le formulaire de cette page utilise tout simplement `+theologique.ch`.

Le même type de recherche est possible avec d’autres moteurs, mais leur indexation n’est, hélas, pas toujours aussi bonne que celle de Google.
Je concède que si j’optimise mon indexation chez l’orgre de la recherche, c’est aussi un peu de ma faute.
Mais je reste pragmatique, à défaut d’être complètement cohérent.
