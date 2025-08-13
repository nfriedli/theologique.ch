+++
title = "URL courtes et simples"
description = "Les adresses courtes peuvent être lisibles, faciles à mémoriser, simples à transmettre, jolies à l’impression, créatives dans le choix des lettres. Elles permettent aussi des codes QR plus petits pour les représenter en images."
date = 2025-08-07
draft = true

+++

Un des choix importants lors de la création d'un nouveau site, c'est la gestion des URL (Uniform Resource Locator) ou adresses web.
Pour ce site, je les souhaite courtes et simples.

J'utilise le terme «URL» au féminin, mais on rencontre parfois le masculin.

En principe, les adresses ne changent plus une fois «figées».
Et, quand elles sont modifiées pour de bonnes raisons, elles devraient être redirigées.
En 1998 déjà, le créateur du web Tim Berners-Lee nous disait que les bonnes adresses ne changent pas: [Cool URIs don't change](https://www.w3.org/Provider/Style/URI).

Schématiquement, il existe 3 types d'adresses de pages:

- celles qui sont conformes à la hiérarchie des pages sur le serveur, c'est ce que j'utilise pour [Trouver ma paroisse](https://ma-paroisse.ch/).
Par exemple <https://ma-paroisse.ch/neuchatel/barc/> qui se situe bien au même endroit dans les sources: <https://github.com/nfriedli/ma-paroisse.ch/blob/main/content/neuchatel/barc.md>
- celles qui sont utilisées par ces CMS (Content Management System ou système de gestion de contenu) comme WordPress et qui ne dépendent pas de la présence réelle d'un fichier (logique, tous les contenus se trouvent dans une base de données), par exemple: <https://dianefriedli.ch/ce-blog-a-10-ans/>
- celles qui sont une suite aléatoire de caractères, par exemple <https://sebsauvage.net/links/?MZ9hOg> dans le Shaarli de son créateur Sebastien Sauvage

Il existe aussi des adresses courtes, souvent créées par des systèmes externes, sur lesquels nous n'avons pas la gestion.
Je ne traite pas du sujet ici.

Derek Sivers a choisi d'utiliser des URL à la fois courtes et simple.
Ce qui signifie que la longueur ne doit pas déranger la lisibilité.
Il en parle très bien dans [Short URLs: why and how](https://sive.rs/su).

Ces adresses peuvent être à la fois simplement mémorisées,  transmises oralement, et être jolies.
J'ajouterais qu'elles permettent une certaine créativité.
Et que des URL pas trop longues sont plus faciles à insérer dans des textes imprimés.

Pour cette page, SPIP (le CMS utilisé ici) a choisi une URL en fonction du titre: <https://theologique.ch/url-courtes-et-simples> C'est correct, mais le `-et-` est inutile, tant pour la lisibilité que pour l'hypothétique apport au référencement.
J'ai modifié l'adresse pour choisir, simplement: <https://theologique.ch/url>

Tout n'est pas rose avec des adresses très courtes, qui ne reflètent pas la hiérarchie du site.
Par exemple, il est impossible d'obtenir des statistiques par répertoire ou sous-répertoire.
Dans certains cas, c'est très handicapant.
Pour un blog, c'est généralement anecdotique.

Un avantage des adresse courtes est la plus petite taille des codes QR pour les représenter:

<doc3|center>

Alors qu'une URL plus longue (celle proposée par défaut par SPIP):

<doc2|center>

Ou une URL plus longue (mais encore limitée par rapport à ce que l'on rencontre sur le web):

<doc4|center>

Pas mal de CMS proposent des facilement URL très courtes (pas toujours visibles).
Par exemple en utilisant le numéro d'article en base de données chez SPIP ou WordPress.
C'est pourquoi je vous recommande d'éviter des outils de réduction d'adresses tiers, qui sont de bons candidats à la [merdification](/blog/merdification/).

Pour des adresse vraiment très courtes, il est toujours bon de disposer d'un nom de domaine lui aussi court.
Intéressant, de nombreuses institutions en possèdent des réduits, sous forme de sigles ou d'acronymes.
Une chance à saisir.

Qu'elles soient longues ou courtes, hiérarchiques ou non, des URL bien construites sont synonymes de clarté.
Ainsi que la marque bienvenue du soin accordé aux détails.
