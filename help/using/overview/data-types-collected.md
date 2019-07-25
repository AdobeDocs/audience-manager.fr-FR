---
description: Audience Manager permet de collecter et de gérer des données propriétaires, tierces et tierces.
seo-description: Audience Manager permet de collecter et de gérer des données propriétaires, tierces et tierces.
seo-title: Types de données collectés
solution: Audience Manager
title: Types de données collectés
uuid: a 2 ddf 470-32 e 6-41 ec-a 1 d 7-a 6232 ef 084 b 9
translation-type: tm+mt
source-git-commit: f87a6f6c79a01c23608e4f5be24d017894e1c541

---


# Types of Data Collected{#types-of-data-collected}

Audience Manager permet de collecter et de gérer des données propriétaires, tierces et tierces.

Le déverrouillage des ressources d'informations client stockées dans plusieurs clolos est l'un des plus grands défis de données auxquels les entreprises sont confrontées aujourd'hui. Grâce aux bases de données de gestion de la relation client, aux systèmes d'enregistrement, aux serveurs d'annonces, etc., les entreprises ont besoin d'outils qui permettent de centraliser les données précieuses et de gérer les informations client/audience sous la forme d'un seul fichier de données stratégiques. Audience Manager permet de déverrouiller des informations client isolées et de gérer la collecte de données à partir de plusieurs sources. Les données collectées peuvent être gérées en fonction des valeurs de durée de vie de l'élément de données (TTL), ce qui aide l'éditeur à contrôler l'expiration des données sur toutes les sources. Audience Manager est conçu pour vous aider à gérer les types de données suivants :

| Type de données | Emplacement des données |
|---|---|
| **Propriétaires** | Clients. Les données sont collectées en ligne (à partir des interactions des utilisateurs sur vos sites Web) ou hors ligne. |
| **Deuxième partie** | Partenaires stratégiques et annonceurs. |
| **Tiers** | Fournisseurs de données et/ou échanges. Les données peuvent inclure des informations telles que l'intention, la démographie, les réseaux sociaux, le mode psychographique, etc. |

## First-Party Data Collection {#first-party-data}

La collecte de données propriétaires est une fonctionnalité principale d'Audience Manager. Cette compétence de base répond aux besoins de nos clients (éditeurs ou annonceurs) qui souhaitent utiliser des données propriétaires comme pierre angulaire de leurs programmes marketing ou pour le ciblage et la modélisation par rapport à d'autres sources de données.

<!-- 

c_1st_party_data.xml

 -->

Audience Manager collabore avec les clients pour comprendre leur stratégie de données, puis mappe cette stratégie à un plan de collecte de données personnalisé. Notre équipe de solutions partenaires collabore avec vous pour évaluer les sites, les signaux de données brutes et d'autres interactions de l'utilisateur sur vos sites Web. Grâce à ces informations, nous vous aiderons à créer une stratégie personnalisée de collecte de données qui capture les signaux de données de niveau utilisateur à partir de diverses pages de votre inventaire. Les données capturées sont stockées et mappées à une taxonomie prédéfinie, qui peut être mise à jour à tout moment, à mesure que les besoins de votre entreprise changent.

L'exemple suivant illustre comment les éléments de données potentiels peuvent être capturés à partir d'un exemple de page de shopping.

![](assets/1st_party_800px.png)

Une fois les données brutes collectées, elles sont associées à des caractéristiques définies par le client dans la plate-forme Audience Manager. La taxonomie et les mappages de données peuvent à tout moment être ajustés sans apporter de modifications au code de collecte de données.

## Second-Party Data Collection {#second-party-data}

Les données tierces proviennent d'un partenaire stratégique stratégique (il ne s'agit pas des données de l'éditeur). Ces informations sont collectées et gérées tout comme les données propriétaires.

<!-- 

c_2nd_party_data.xml

 -->

Dans un scénario de données propriétaires, les publicitaires envoient leurs propres ressources de données aux éditeurs afin qu'ils puissent combiner ces informations avec les données de l'éditeur, puis exécuter un programme de publicité plus ciblé. De plus, les éditeurs peuvent élargir leur pool d'audiences en partenariat avec leurs annonceurs. Dans la plupart des cas, ces dispositions impliquent des relations contractuelles limitées à l'insertion de la balise de conteneur Audience Manager sur le site partenaire pour faciliter la collecte et le partage de données.

Un exemple de collecte de données et de marketing de relance tiers peut impliquer un fabricant automobile qui collecte des données sur ses pages de configuration de voitures, puis le partage avec ses partenaires clés. Dans ce cas, le fabricant de l'automobile peut proposer différentes publicités sur un site partenaire d'Audience Manager pour les consommateurs qui ont configuré différents types d'options de véhicule (couleur, modèle, etc.).

![](assets/2nd_party_700px.png)

## Third-Party Data Collection {#third-party-data}

Les données tierces sont des informations collectées et partagées par les fournisseurs en dehors d'Audience Manager.

<!-- 

c_3rd_party_data.xml

 -->

Les données tierces peuvent être utilisées pour qualifier des segments de données existants (par exemple, âge, revenu domestique, etc.), fournir des données à la demande mais pas autrement disponibles, ou être utilisées dans la modélisation de recherche par rapport à une base utilisateur connue provenant de données propriétaires et de données propriétaires. Audience Manager fonctionne avec de nombreux fournisseurs de données tiers et vous aidera à comprendre le type de données collectées par ces fournisseurs de données afin que vous puissiez conclure des bonnes affaires stratégiques avec chaque fournisseur.

>[!NOTE]
>
>For a full list of third-party data providers supported by [!DNL Audience Manager], see the [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

Audience Manager s'intègre à d'autres fournisseurs de données en fonction de leurs API et jeux de données disponibles. La collecte de données fonctionne en temps réel lorsqu'un utilisateur navigue sur votre site ou par des méthodologies hors bande dans lesquelles les ID sont synchronisés entre les partenaires et les données sont transférées entre les serveurs une fois qu'un utilisateur a quitté votre site. Dans tous les cas, les clients Audience Manager tirent avantage de la synchronisation des données tierces sur notre plateforme, ce qui signifie que chaque client ou domaine n'a pas besoin d'effectuer sa propre synchronisation. Cela permet d'augmenter la portée et de réduire les appels serveur à partir de la page.

## Match Partners {#match-partners}

De nombreux clients choisissent de travailler avec des partenaires de correspondance de données tiers. Ces entités entretiennent des relations avec les sites dont les conditions d'inscription sont requises et qui peuvent traiter les fichiers de données client en les faisant correspondre (en temps réel) en fonction de leur réseau d'inscription.

![](assets/data_provider_match_700px.png)

