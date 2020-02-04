---
description: Audience Manager vous aide à collecter et à gérer des données propriétaires, propriétaires et tiers.
seo-description: Audience Manager vous aide à collecter et à gérer des données propriétaires, propriétaires et tiers.
seo-title: Types de données collectées
solution: Audience Manager
title: Types de données collectées
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
translation-type: tm+mt
source-git-commit: cee17904aa5ece54d1df7ad482505515846349b5

---


# Types de données collectées{#types-of-data-collected}

Audience Manager vous aide à collecter et à gérer des données propriétaires, propriétaires et tiers.

Déverrouiller les ressources d’informations client stockées dans plusieurs silos est l’un des plus grands défis auxquels sont confrontées les entreprises aujourd’hui en matière de données. Des bases de données CRM aux systèmes d’enregistrement en passant par les serveurs d’annonces, etc., les entreprises ont besoin d’outils qui les aident à centraliser des données précieuses et à gérer les informations client/audience en tant qu’actif de données stratégiques unique. Audience Manager vous aide à déverrouiller des informations client isolées et à gérer la collecte de données à partir de plusieurs sources. Les données collectées peuvent être gérées en fonction des valeurs de durée de vie (TTL) des éléments de données, ce qui permet à l’éditeur de contrôler l’expiration des données sur toutes les sources. Audience Manager est conçu pour vous aider à gérer les types de données suivants :

| Type de données | D’où proviennent les données |
|---|---|
| **Propriétaire** | Clients. Les données sont collectées en ligne (à partir des interactions des consommateurs sur vos sites Web) ou hors ligne. |
| **Second-party** | Partenaires stratégiques et publicitaires. |
| **Tiers** | Fournisseurs de données et/ou échanges. Les données peuvent inclure des informations telles que l’intention, la démographie, le mode de vie ou social, la psychographie, etc. |

## First-Party Data Collection {#first-party-data}

La collecte de données propriétaires est une fonctionnalité principale d’Audience Manager. Cette compétence de base répond aux besoins de nos clients (éditeurs ou publicitaires) qui souhaitent utiliser les données propriétaires comme pierre angulaire de leurs programmes marketing ou pour cibler et modéliser d’autres sources de données.

<!-- 

c_1st_party_data.xml

 -->

Audience Manager travaille avec les clients pour comprendre leur stratégie de données, puis fait correspondre cette stratégie à un plan de collecte de données personnalisé. Notre équipe Solutions Partenaires travaille avec vous pour évaluer les sites, les signaux de données brutes et les autres interactions des utilisateurs sur vos sites Web. Grâce à ces informations, nous vous aiderons à créer une stratégie de collecte de données personnalisée qui capture les signaux de données au niveau de l&#39;utilisateur provenant de diverses pages de votre inventaire. Les données capturées sont stockées et mises en correspondance avec une taxonomie prédéfinie, qui peut être mise à jour à tout moment, en fonction des besoins de votre entreprise.

L’exemple suivant illustre la manière dont les éléments de données potentiels peuvent être capturés à partir d’un exemple de page d’achat.

![panier-données](assets/shopping-cart-data.png)

| Élément | Description |
|---|---|
| 1 | **Sexe**. Le prénom d&#39;un acheteur indique habituellement son sexe. Dans notre exemple, le prénom de l&#39;acheteur est Mary, donc nous savons que l&#39;acheteur est une femme. Les noms ne sont jamais stockés par Audience Manager. |
| 2 | **Intérêts**. Les articles du panier peuvent indiquer divers intérêts. Dans notre exemple, Mary dépense beaucoup pour l&#39;équipement de fitness. |
| 3 | **Type** de logement. Selon les adresses d&#39;expédition et/ou de facturation, vous pouvez déterminer si Mary achète de l&#39;équipement pour elle-même ou pour une entreprise. |
| 4 | **Emplacement**. Les codes postaux sont plus fiables que les adresses IP lorsqu’il s’agit de localiser un emplacement. |
| 5 | **Affinité** de promotion. Si un acheteur utilise des codes promotionnels ou des cartes-cadeaux, il est probablement un chasseur de bonnes affaires à la recherche des meilleures affaires. |
| 6 | **Dépenser le pouvoir**. Les données de prix corrélées avec les codes ZIP+4 indiquent le pouvoir de dépense d’un emplacement donné. |

Une fois les données brutes collectées, elles sont mises en correspondance avec les caractéristiques définies par le client dans la plate-forme Audience Manager. La taxonomie et les mappages de données peuvent être ajustés à tout moment sans apporter de modifications au code de collecte de données.

## Collecte de données propriétaires {#second-party-data}

Les données propriétaires proviennent d’un partenaire commercial stratégique (ce ne sont pas des données d’éditeur). Ces informations sont collectées et gérées comme les données propriétaires.

<!-- 

c_2nd_party_data.xml

 -->

Dans un scénario de données propriétaires, les publicitaires envoient leurs propres ressources de données aux éditeurs afin qu’ils puissent combiner ces informations avec les données de l’éditeur, puis exécuter un programme publicitaire plus ciblé. De plus, les éditeurs peuvent élargir leur public en s’associant avec leurs annonceurs. Dans la plupart des cas, ces arrangements impliquent des relations contractuelles limitées au placement de la balise conteneur Audience Manager sur le site partenaire afin de faciliter la collecte et le partage des données.

Un exemple de collecte et de remarketing de données de seconde partie peut impliquer la collecte de données sur ses produits par un distributeur de vêtements, puis le partage de ces informations avec des partenaires clés. Dans ce cas, le commerce de détail peut proposer différentes publicités sur un site partenaire d’Audience Manager pour les clients qui choisissent différentes couleurs et tailles de veste.

![](assets/shopping-cart-traits.png)

## Third-Party Data Collection {#third-party-data}

Les données tierces sont des informations collectées et partagées par les fournisseurs en dehors d’Audience Manager.

<!-- 

c_3rd_party_data.xml

 -->

Les données tierces peuvent être utilisées pour qualifier les segments de données existants (par exemple, âge, revenu du ménage, etc.), fournir des données qui sont en demande mais qui ne sont pas disponibles d’une autre manière, ou être utilisées dans la modélisation semblable à une base d’utilisateurs connue à partir de données propriétaires et secondaires. Audience Manager travaille avec de nombreux fournisseurs de données tiers et vous aidera à comprendre le type de données collectées par ces fournisseurs de données afin que vous puissiez conclure les bonnes transactions stratégiques avec chaque fournisseur.

>[!NOTE]
>
>Pour obtenir la liste complète des fournisseurs de données tiers pris en charge par [!DNL Audience Manager]Adobe Audience Finder [](https://www.adobe-audience-finder.com/).

Audience Manager s’intègre à d’autres fournisseurs de données en fonction de leurs API et ensembles de données disponibles. La collecte de données fonctionne en temps réel, lorsqu’un utilisateur navigue sur votre site ou au moyen de méthodologies hors bande dans lesquelles les identifiants sont synchronisés entre les partenaires et les données sont transférées entre les serveurs après qu’un utilisateur a quitté votre site. Dans les deux cas, les clients d’Audience Manager bénéficient de la synchronisation de données tierces sur notre plateforme, ce qui signifie que chaque client, ou domaine, n’a pas à effectuer sa propre synchronisation. Cela permet d’accroître la portée et de réduire les appels serveur à partir de la page.

## Correspondance avec les partenaires {#match-partners}

De nombreux clients choisissent de travailler avec des partenaires tiers de correspondance de données. Ces entités ont des relations avec les sites qui ont des exigences d’enregistrement et peuvent traiter les fichiers de données client en les faisant correspondre (en temps réel) en fonction de leur réseau d’enregistrement.

![data-provider-match](assets/data-provider-match.png)
