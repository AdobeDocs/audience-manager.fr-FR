---
description: Audience Manager vous aide à collecter et à gérer des données de premier, de deuxième et de troisième niveau.
seo-description: Audience Manager vous aide à collecter et à gérer des données de premier, de deuxième et de troisième niveau.
seo-title: Types de données collectées
solution: Audience Manager
title: Types de données collectées
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: overview
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Types de données collectées {#types-of-data-collected}

[!DNL Audience Manager] vous aide à collecter et à gérer des données de premier, de deuxième et de troisième niveau.

Libérer les éléments d’informations client conservés dans différents silos est l’un des plus grands défis en matière de données auxquels sont actuellement confrontées les sociétés. From [!DNL CRM] databases, to registration systems, to ad servers, and so forth, companies require tools that help centralize valuable data and manage customer/audience information as a single strategic data asset. [!DNL Audience Manager] vous aide à libérer les informations client isolées et à gérer la collecte de données depuis plusieurs sources. Collected data can be managed based on data element time-to-live ([!DNL TTL]) values, which helps the publisher control data expiration across all sources. [!DNL Audience Manager] est conçu de manière à vous aider à gérer les types de données suivants :

| Type de données | Provenance des données |
|---|---|
| **Premier niveau** | Clients. Les données sont collectées en ligne (à partir des interactions des consommateurs sur vos sites web) ou hors ligne. |
| **Second niveau** | Partenaires stratégiques et annonceurs. |
| **Troisième niveau** | Fournisseurs et/ou échanges de données. Les données peuvent inclure des informations comme l’intention, la démographie, des informations sociales ou sur le mode de vie, la psychographie, etc. |

## Collecte de données de premier niveau {#first-party-data}

First-party data collection is a main [!DNL Audience Manager] feature. Cette compétence principale s’occupe des besoins de nos clients (éditeurs ou annonceurs) qui souhaitent utiliser des données propriétaires comme base de leurs programmes marketing ou pour le ciblage et la modélisation par rapport à d’autres sources de données.

[!DNL Audience Manager] travaille avec des clients pour comprendre leur stratégie de données, puis met en correspondance cette stratégie avec un plan de collecte des données personnalisé. Notre équipe Partner Solutions travaille avec vous pour évaluer les sites, les signaux de données bruts et d’autres interactions utilisateur sur vos sites web. Grâce à ces informations, nous vous aiderons à créer une stratégie de collecte des données sur mesure qui capture les signaux de données au niveau de l’utilisateur depuis différentes pages de votre inventaire. Les données capturées sont conservées et mises en correspondance avec une taxonomie prédéfinie qui peut être mise à jour à tout moment, à mesure que les besoins de votre entreprise changent.

L’exemple suivant illustre la manière dont les éléments de données peuvent potentiellement être capturés depuis un exemple de page d’achat.

![shopping-cart-data](assets/shopping-cart-data.png)

| Élément | Description |
|---|---|
| 1 | **Genre**. Le prénom d’un acheteur indique généralement son genre. Dans notre exemple, le prénom de l’acheteuse est Marie, nous savons donc qu’il s’agit d’une femme. Les noms de famille ne sont jamais conservés par Audience Manager. |
| 2 | **Centres d’intérêt**. Les articles du panier peuvent indiquer différents centres d’intérêt. Dans notre exemple, Marie dépense beaucoup en équipements de remise en forme. |
| 3 | **Type de logement**. En fonction de l’adresse d’expédition et/ou de facturation, vous pouvez déduire si Marie achète des équipements de remise en forme pour elle ou pour une entreprise. |
| 4 | **Emplacement**. [!DNL ZIP] les codes sont plus fiables que [!DNL IP] les adresses lorsqu&#39;il s&#39;agit de localiser un emplacement. |
| 5 | **Affinité avec les promotions**. Si un acheteur utilise des codes promotionnels ou des cartes-cadeaux, il s’agit probablement d’un chasseur de remises à la recherche des meilleures offres. |
| 6 | **Pouvoir d’achat**. Price data correlated with [!DNL ZIP+4] codes indicate spending power of a given location. |

After the raw data is collected, it gets mapped back to customer-defined traits within the [!DNL Audience Manager] platform. Il est possible d’ajuster la taxonomie et les correspondances de données à tout moment sans apporter de modifications au code de collecte des données.

## Collecte de données de deuxième niveau {#second-party-data}

Les données de deuxième niveau proviennent d’un partenaire commercial stratégique (il ne s’agit pas de données d’éditeur). Ces informations sont collectées et gérées de la même manière que les données de premier niveau.

Dans un scénario de données de deuxième niveau, les annonceurs envoient leurs propres éléments de données aux éditeurs pour qu’ils puissent associer ces informations aux données de l’éditeur, puis exécuter un programme de publicité plus ciblé. En outre, les éditeurs peuvent élargir leur panel en s’associant à leurs annonceurs. In most cases, these arrangements involve contractual relationships limited to putting the [!DNL Audience Manager] container tag on the partner site to facilitate data collection and sharing.

Par exemple, une collecte et un remarketing des données de deuxième niveau peuvent impliquer un détaillant de vêtements collectant des données sur ses produits et partageant ces informations avec des partenaires clés. In this case, the retailed could serve different ads across an [!DNL Audience Manager] partner site for consumers who chose various jacket colors and sizes.

![](assets/shopping-cart-traits.png)

## Collecte de données de troisième niveau {#third-party-data}

Third-party data is information collected and shared by vendors outside of [!DNL Audience Manager].

Third-party data can be used to qualify existing data [!UICONTROL segments] (for example, age, household income, and so forth), provide data that is in demand but not otherwise available, or be used in lookalike modeling against a known user base from first-party and second-party data. [!DNL Audience Manager] travaille avec de nombreux fournisseurs de données tiers et vous aidera à comprendre le type de données que ces fournisseurs de données collectent afin que vous puissiez conclure les bons accords stratégiques avec chaque fournisseur.

>[!NOTE]
>
>Pour obtenir la liste complète des fournisseurs de données de troisième niveau pris en charge par [!DNL Audience Manager], consultez [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] s’intègre à d’autres fournisseurs de données en fonction de leurs jeux de données [!DNL APIs] et de leurs disponibilités. La collecte de données fonctionne en temps réel à chaque fois qu’un utilisateur navigue sur votre site ou par des méthodologies hors plage dans lesquelles les identifiants sont synchronisés entre les partenaires et les données sont transférées entre les serveurs après qu’un utilisateur quitte votre site. In either case, [!DNL Audience Manager] clients get the benefit of having third-party data synchronized on our platform, which means each client, or domain, does not have to perform its own synchronization. Cela permet d’accroître la portée et réduit les appels au serveur depuis la page.

## Partenaires de mise en correspondance {#match-partners}

De nombreux clients choisissent de travailler avec des partenaires de mise en correspondance de données de troisième niveau. Ces entités entretiennent des relations avec des sites qui ont des critères d’enregistrement et peuvent traiter des fichiers de données client en les faisant correspondre (en temps réel) en fonction de leur réseau d’enregistrement.

![data-provider-match](assets/data-provider-match.png)
