+++
title = "Fin du monitoring du protestantisme réformé francophone"
description = "90+ sites protestants réformés francophones testés chaque semaine durant 18 mois me permettent d’esquisser un bilan de performance global."
date = 2025-07-09
categories = ["web"]
tags = ["webperf"]
+++

Durant 18 mois, j’ai testé chaque semaine presque 100 sites protestants réformés francophones avec [speedlify](https://www.speedlify.dev/).
Cet outil permet d’automatiser des mesures de performances et d’accessibilité (A11Y) sur un ensemble de pages choisies.
Il utilise [Lighthouse](https://developer.chrome.com/docs/lighthouse/overview?hl=fr) et [Axe](https://www.deque.com/axe/).
Il propose un classement et un historique de toutes les mesures.

**Ce matin, le test a été fait pour la dernière fois.**
Je continuerai évidemment à monitorer mes propres sites.
Pour l’histoire, la [liste des sites testés](https://gist.github.com/nfriedli/9b24b0659cc98f1c195d93f5ce6ef8ec) est disponible en ligne.
Certains n’existent plus ou ont été redirigés, mais l’essentiel est toujours en ligne.

Les personnes qui recevaient des résultats pour leur(s) site(s) ont été averties de l’arrêt du service il y a quelques semaines.

## À propos de speedlify

C’est un outil qui fonctionne parfaitement et qui ne m’a jamais lâché dans la durée.
Je l’ai utilisé en local (sur mon ordinateur) pour avoir des résultats qui tiennent compte de ma localisation et de ma connexion Internet.

Les 2 grandes forces de speedlify sont:

- l’**automatisation** sans laquelle je n’aurais pas testé autant de sites
- l’**historique** qui permet de revenir dans le temps quand on détecte des changements importants

Je conseille l’utilisation de speedlify pour suivre votre présence web, par exemple en sélectionnant les pages les plus importantes de votre site.
C’est ce que fait son créateur Zach Leatherman pour [son site personnel](https://www.speedlify.dev/zachleat.com/).

## Résultats du test du jour

Il y a 10% des sites qui sont excellents.
Ils obtiennent un score vert (supérieur à 90%) dans les 4 catégories de Lighthouse.

Il y a au moins 25% des sites qui ont des lacunes très sérieuses en performance.
Ils obtiennent un score rouge (inférieur à 50%) dans cette catégorie.

Plus de 50% des sites transfèrent beaucoup trop de données.
Ils sollicitent trop la bande passante, sont peu écologiques et s’affichent probablement mal (voire pas du tout) sur des périphériques qui ont quelques années.

Sans surprise, l’accessibilité (A11Y) est problématique.
Un seul exemple: les contrastes insuffisants représentent un souci bien documenté depuis longtemps (voir [Color Contrast](https://almanac.httparchive.org/en/2024/accessibility#color-contrast) du Web Almanach 2024).

Il n’y a pas de différences sensibles entre des «petits sites personnels» et des «grands projets d’agences».
Dans les 2 catégories, il y a du (très) bon et du (très) mauvais.

Et WordPress, bien présent, rappelle qu’un outil n’est qu’un outil.
Bien utilisé, il permet d’excellents résulats; mal configuré, il est désastreux.

## Bilan dans la durée

Je l’ai dit, speedlify propose un classement.
J’en tire ceci:

> Dans la grande majorité des cas, quand un site améliore son classement, cela ne signifie pas qu’il s’améliore.
> Ses résultats restent souvent identiques.
> Mais cela signifie que ce sont ses «concurrents» qui dégringolent; leurs résultats empirent.

Dans l’absolu, je trouve cette notion de classement peu utile dans le monde du web protestant réformé francophone.
Les présences web sont rarement en concurrence directe et il importe peu de dépasser ses collègues.
De plus, les mauvais résultats ne semblent pas motiver les plus mauvais à s’améliorer (pour les internautes).
J’ai toujours rêvé d’une vigilance mutuelle sans compétition.

Je pourrais dire la même chose des refontes complètes de sites.
Les nouveaux sites, bien souvent, ne sont pas meilleurs que ceux qu’ils remplacent du point de vue de la performance.
La lecture de [JavaScript broke the web (and called it progress)](https://www.jonoalderson.com/conjecture/javascript-broke-the-web-and-called-it-progress/) de Jono Alderson donne quelques pistes.

Hors refonte, les modifications techniques semblent rares.
Quand un site diminue ou augmente la quantité de données transférée, c’est presque toujours une conséquence des contenus publiés.
C’est un gros problème, peut-être par manque de formation des personnes en charge de la gestion courante.

Je reste surpris par les discours que je trouve ça et là.
Un hebdomadaire français nous explique que son site est «rapide et intuitif» alors que les mesures sont médiocres.
De nombreux sites qui parlent de sauvegarde de la Création continuent de me décevoir par l’écart entre leurs injonctions et leurs sites.
J’en avais dit un mot dans [Écologie et cohérence sur le web](https://nicolasfriedli.ch/blog/ecologie-coherence/).
Enfin, je rappelle qu’une annonce dithyrambique n’est pas performative; elle ne fait pas un bon site.

## Besoin de conseils?

Mon suivi régulier s’arrête, mais les enjeux restent.

Il y a des lien vers des outils dans mon billet [Tester un site web](https://nicolasfriedli.ch/blog/tester-site/).

Si vos internautes vous intéressent (vraiment), je reste disponible pour l’amélioration de votre site.
Je vous conseille gratuitement pour vos sites personnels.
Je suis disponible comme consultant web indépendant pour des projets institutionnels et des sites marchands.
