---
description: Audience Manager vous aide à collecter et à gérer des données de premier, de deuxième et de troisième niveau.
seo-description: Audience Manager vous aide à collecter et à gérer des données de premier, de deuxième et de troisième niveau.
seo-title: Types de données collectées
solution: Audience Manager
title: Types de données collectées
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: Présentation
exl-id: cfb587da-ceac-425f-8334-e961eba6fad2
translation-type: tm+mt
source-git-commit: 15e36d2847627b5e5ccef11f8073ce5124f14815
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 72%

---

# Types de données collectées {#types-of-data-collected}

[!DNL Audience Manager] vous aide à collecter et à gérer des données de premier, de deuxième et de troisième niveau.

Libérer les éléments d’informations client conservés dans différents silos est l’un des plus grands défis en matière de données auxquels sont actuellement confrontées les sociétés. De [!DNL CRM] bases de données, aux systèmes d&#39;enregistrement, aux serveurs d&#39;annonces, etc., les sociétés ont besoin d&#39;outils qui permettent de centraliser des données précieuses et de gérer les informations client/audience en tant qu&#39;actif de données stratégiques unique. [!DNL Audience Manager] vous aide à libérer les informations client isolées et à gérer la collecte de données depuis plusieurs sources. Les données collectées peuvent être gérées en fonction des valeurs de durée de vie ([!DNL TTL]) des éléments de données, ce qui permet à l’éditeur de contrôler l’expiration des données pour toutes les sources. [!DNL Audience Manager] est conçu de manière à vous aider à gérer les types de données suivants :

| Type de données | Provenance des données |
|---|---|
| **Premier niveau** | Clients. Les données sont collectées en ligne (à partir des interactions des consommateurs sur vos sites web) ou hors ligne. |
| **Second niveau** | Partenaires stratégiques et annonceurs. |
| **Troisième niveau** | Fournisseurs et/ou échanges de données. Les données peuvent inclure des informations comme l’intention, la démographie, des informations sociales ou sur le mode de vie, la psychographie, etc. |

## Collecte de données de premier niveau {#first-party-data}

La collecte de données propriétaires est une fonction principale [!DNL Audience Manager]. Cette compétence principale s’occupe des besoins de nos clients (éditeurs ou annonceurs) qui souhaitent utiliser des données propriétaires comme base de leurs programmes marketing ou pour le ciblage et la modélisation par rapport à d’autres sources de données.

[!DNL Audience Manager] travaille avec des clients pour comprendre leur stratégie de données, puis met en correspondance cette stratégie avec un plan de collecte des données personnalisé. Notre équipe Partner Solutions travaille avec vous pour évaluer les sites, les signaux de données bruts et d’autres interactions utilisateur sur vos sites web. Grâce à ces informations, nous vous aiderons à créer une stratégie de collecte des données sur mesure qui capture les signaux de données au niveau de l’utilisateur depuis différentes pages de votre inventaire. Les données capturées sont conservées et mises en correspondance avec une taxonomie prédéfinie qui peut être mise à jour à tout moment, à mesure que les besoins de votre entreprise changent.

L’exemple suivant illustre la manière dont les éléments de données peuvent potentiellement être capturés depuis un exemple de page d’achat.

![shopping-cart-data](assets/shopping-cart-data.png)

| Élément | Description |
|---|---|
| 1 | **Genre**. Le prénom d’un acheteur indique généralement son genre. Dans notre exemple, le prénom de l’acheteuse est Marie, nous savons donc qu’il s’agit d’une femme. Les noms de famille ne sont jamais conservés par Audience Manager. |
| 2 | **Centres d’intérêt**. Les articles du panier peuvent indiquer différents centres d’intérêt. Dans notre exemple, Marie dépense beaucoup en équipements de remise en forme. |
| 3 | **Type de logement**. En fonction de l’adresse d’expédition et/ou de facturation, vous pouvez déduire si Marie achète des équipements de remise en forme pour elle ou pour une entreprise. |
| 4 | **Emplacement**. [!DNL ZIP] les codes sont plus fiables que  [!DNL IP] les adresses lorsqu&#39;il s&#39;agit de localiser un emplacement. |
| 5 | **Affinité avec les promotions**. Si un acheteur utilise des codes promotionnels ou des cartes-cadeaux, il s’agit probablement d’un chasseur de remises à la recherche des meilleures offres. |
| 6 | **Pouvoir d’achat**. Les données de prix corrélées avec les codes [!DNL ZIP+4] indiquent le pouvoir de dépense d&#39;un emplacement donné. |

Une fois les données brutes collectées, elles sont mises en correspondance avec les caractéristiques définies par le client dans la plate-forme [!DNL Audience Manager]. Il est possible d’ajuster la taxonomie et les correspondances de données à tout moment sans apporter de modifications au code de collecte des données.

## Collecte de données de deuxième niveau {#second-party-data}

Les données de deuxième niveau proviennent d’un partenaire commercial stratégique (il ne s’agit pas de données d’éditeur). Ces informations sont collectées et gérées de la même manière que les données de premier niveau.

Dans un scénario de données de deuxième niveau, les annonceurs envoient leurs propres éléments de données aux éditeurs pour qu’ils puissent associer ces informations aux données de l’éditeur, puis exécuter un programme de publicité plus ciblé. En outre, les éditeurs peuvent élargir leur panel en s’associant à leurs annonceurs. Dans la plupart des cas, ces arrangements impliquent des relations contractuelles limitées à l&#39;insertion de la balise de conteneur [!DNL Audience Manager] sur le site partenaire afin de faciliter la collecte et le partage des données.

Par exemple, une collecte et un remarketing des données de deuxième niveau peuvent impliquer un détaillant de vêtements collectant des données sur ses produits et partageant ces informations avec des partenaires clés. Dans ce cas, le produit de vente au détail peut proposer différentes publicités sur un [!DNL Audience Manager] site partenaire pour les clients qui ont choisi différentes tailles et couleurs de veste.

![](assets/shopping-cart-traits.png)

## Collecte de données de troisième niveau {#third-party-data}

Les données tierces sont des informations collectées et partagées par les fournisseurs en dehors de [!DNL Audience Manager].

Les données tierces peuvent être utilisées pour qualifier les données existantes [!UICONTROL segments] (par exemple, l’âge, le revenu du ménage, etc.), fournir des données qui sont en demande mais qui ne sont pas disponibles d’une autre manière, ou être utilisées dans la modélisation ressemblante par rapport à une base d’utilisateurs connue à partir de données propriétaires et secondaires. [!DNL Audience Manager] travaille avec de nombreux fournisseurs de données tiers et vous aidera à comprendre le type de données que ces fournisseurs de données collectent afin que vous puissiez conclure les bons accords stratégiques avec chaque fournisseur.

>[!NOTE]
>
>Pour obtenir la liste complète des fournisseurs de données de troisième niveau pris en charge par [!DNL Audience Manager], consultez [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] s’intègre à d’autres fournisseurs de données en fonction de leurs jeux de données  [!DNL APIs] et de leurs disponibilités. La collecte de données fonctionne en temps réel à chaque fois qu’un utilisateur navigue sur votre site ou par des méthodologies hors plage dans lesquelles les identifiants sont synchronisés entre les partenaires et les données sont transférées entre les serveurs après qu’un utilisateur quitte votre site. Dans les deux cas, les clients [!DNL Audience Manager] bénéficient de la synchronisation de données tierces sur notre plateforme, ce qui signifie que chaque client, ou domaine, n&#39;a pas à effectuer sa propre synchronisation. Cela permet d’accroître la portée et réduit les appels au serveur depuis la page.

## Partenaires de mise en correspondance {#match-partners}

De nombreux clients choisissent de travailler avec des partenaires de mise en correspondance de données de troisième niveau. Ces entités entretiennent des relations avec des sites qui ont des critères d’enregistrement et peuvent traiter des fichiers de données client en les faisant correspondre (en temps réel) en fonction de leur réseau d’enregistrement.

![data-provider-match](assets/data-provider-match.png)
