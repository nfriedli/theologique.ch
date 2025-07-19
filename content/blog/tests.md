+++
title = "Enjeux théologiques des tests techniques"
description = ""
date = 2025-07-13
categories = ["web"]
tags = ["performance", "a11y"]
draft = true
+++

À chaque fois que je mets un site en ligne, j’effectue une série de tests pour m’assurer de tout va bien.
J’en dis quelque chose d’un point de vue technique dans [Tester un site web](https://nicolasfriedli.ch/blog/tester-site/).

Toutefois, ce billet souhaite parler des enjeux théologiques de ces vérifications.
Mon objectif est de montrer les conséquences ecclésiologiques, sociales, sociétales, etc. de mauvais résultats.

Je teste toujours la page d’accueil de ce site dans les outils proposés.
Je vous invite à suivre la démarche et à effectuer les mêmes tests avec votre propre site ou un site de votre choix.

## Version mobile

Il vaut toujours la peine de naviguer sur son propre site avec un smartphone ou une tablette.
C’est quelque chose que les responsables de contenu font peu, trop habitué·e·s à le faire à partir d’un ordinateur.
Le mieux, c’est de tester sur plusieurs téléphones, par forcément récents.
Et à partir de plusieurs lieux où le réseau n’est pas toujours bon.
J’ai bien dit **naviguer** (et lire, cliquer, rechercher, etc.), pas seulement «admirer».
Si l’expérience n’est pas bonne, vous avez un gros souci.

L’absence de bonne version mobile est rédhibitoire.

Le trafic mobile sur le web a dépassé depuis longtemps celui des postes fixes et portables.
Autrement dit, plus de 50% des personnes qui naviguent en ce moment n’auront simplement pas accès à votre site.
Par chance, Google va déclasser vos pages et ne pas les afficher dans ses résultats de recherche.

Ne pas proposer de bon site mobile, c’est donc:

- limiter drastiquement les jeunes et ados sur son site
- rendre la consultation impossible à une majorité des migrant·e·s
- exclure une grande majorité de personnes précaires
- ne pas permettre sa consultation dans des contextes particuliers (pendulaires, touristes, etc.)

Comme je n’ai pas envie de dire que mon site est réservé aux nantis, avec leur poste fixe récent et leur connexion fibre, j’ai fait en sorte qu’il fonctionne parfaitement sur mobile.

Je passe aux tests techniques détaillés en entrant l’adresse de mon site (page d’acceuil) dans [PageSpeed Insights](https://pagespeed.web.dev/).
J’obtiens 4 résultats (performance, acessibilité, bonnes pratiques & SEO) dans 2 onglets (bureau & mobile).

## Performance

En première approche, on pourrait dire que performant signifie rapide.
La rapidité d’affichage est importante, notamment pour le commerce en ligne avec sa forte concurrence.

La bonne nouvelle, c’est que pour être rapide, il faut respecter un certain nombre de règles techniques et faire les bons choix tactiques.
Donc, un site performant est, vu sous cet angle, un site bien réalisé.

Ce qui est important, c’est de ne jamais obtenir de résultat rouge (inférieur à 50%) dans cette catégorie comme dans les autres.
Un mauvais résultat, c’est l’assurance que le site d’affichera mal, voir pas du tout, si les conditions de consultation sont  «dégradées».

Cette mesure est globale.
Elle prend en compte la qualité du serveur, la taille des images, le configuration du cache, le chargement des polices, la complexité de la page, etc.

Les sites protestants, théologiques, ecclésiaux, etc. en français reçoivent une proportion importantes de visites du monde entier.
L’Afrique francophone, en particulier, est friande de contenus spirituels et cultuels réformés.
Mais, en Afrique, comme ailleurs, le matériel et les connexions se sont pas les mêmes qu’en Suisse...

Alex Russel, dans sa série [The Performance Inequality Gap](https://infrequently.org/series/performance-inequality/) montre que ce que nous construisons ne fonctionne simplement pas!
Je ne souhaite pas un site réservé aux riches, à l’Europe, aux villes, etc.
C’est pourquoi je veux un site performant.

Avec ses 100%, theologique.ch s’affiche en vert (suprérieur à 80%) à ce test.

## Accessibilité (A11Y)

Un site accessible n’exclut personne de sa consultation et son utilisation.
C’est une thématique beaucoup trop large pour être traitée de manière automatisée.
Mais les outils automatiques donnent déjà un premier indice d’accesibilité.

En plus du test de PageSpeed Insights, je soumets la page d’accueil à [WAVE Web Accessibility Evaluation Tools](https://wave.webaim.org/).
Pour les 2 tests, j’obtiens les meilleurs résultats possibles (100% et aucune erreur ni alerte).

Quand on se satisfait d’un site non accessible, cela signifie que l’on assume d’exclure les personnes en situation de handicap.
Par exemple, celles et ceux qui ont:

- des problèmes de vision (daltonisme, cataracte, DMLA, cécité, etc.)
- des problèmes moteurs (impossibilité d’utiliser une souris, tremblements, paraplégie, etc.)
- des problèmes auditifs (par exemple pour passer un antispam audio)
- des problèmes cognitifs ou neurologiques
- ou tout «handicap» temporaire ou situationnel (lunettes perdues, bras cassé, soleil sur l’écran, etc.)

Le monde protestant réformé romand s’affiche volontiers égalitaire et inclusif.
Mais si c’est affirmé sur un site qui exclut, beaucoup le sauront jamais...
Ou alor

## Bilan carbone

theologique.ch obtient un résultat parfait sur [Website Carbon Calculator](https://www.websitecarbon.com/website/theologique-ch/) et [Ecograder](https://ecograder.com/report/HDK7cngeYUhFszDFtXDPSI6r).

Je ne développe pas ce sujet sur lequel je me suis exprimé par exemple dans [Écologie et cohérence sur le web](https://nicolasfriedli.ch/blog/ecologie-coherence/) ou [Site web écoconçu (ou pas) pour l’UNIL](https://nicolasfriedli.ch/blog/ecologie-unil/).
J’en ai marre du ~~bullshit~~ verbiage généralisé sur le sujet.

De nombreux discours d’institutions, ecclésiales ou non, sont aussi peu suivis de faits que ceux des pires entreprises.
Bonne nouvelle, le paravent de la bien-pensance ne résiste pas aux mesures des sites de tests proposés ci-dessus.

## Validité du code

## Contrôle des liens

## Règles de qualité Opquast