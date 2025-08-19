---
description: 'Découvrez les avantages, les types et les utilisations des destinations : tout système tiers, tel qu’un serveur de publicités ou un DSP, où vous partagez des données. Utilisez Destination Builder pour créer et gérer des destinations de cookie, d’URL ou de serveur à serveur.'
keywords: code d’intégration, destination, présentation de la destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
landing-page-description: 'Découvrez les avantages, les types et les utilisations des destinations : tout système tiers, tel qu’un serveur de publicités ou un DSP, où vous partagez des données. Utilisez Destination Builder pour créer et gérer des destinations de cookie, d’URL ou de serveur à serveur.'
short-description: 'Découvrez les avantages, les types et les utilisations des destinations : tout système tiers, tel qu’un serveur de publicités ou un DSP, où vous partagez des données. Utilisez Destination Builder pour créer et gérer des destinations de cookie, d’URL ou de serveur à serveur.'
seo-title: Destinations
solution: Audience Manager
title: Destinations
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 19%

---

# Présentation de [!UICONTROL Destinations] {#destinations}

Dans Audience Manager, un [!UICONTROL destination] correspond à tout système tiers (serveur de publicités, [!DNL DSP], réseau de publicités, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] est l’outil que vous utilisez pour créer et gérer des [!UICONTROL cookie], des [!DNL URL] ou des [!UICONTROL server-to-server destinations].

## Objectif et avantages {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] et [!UICONTROL Destination Builder] vous permettent de créer des [!UICONTROL destinations] et d’envoyer des informations sur les utilisateurs segmentés à votre partenaire de données. Cela vous aide à :

* **Protéger la valeur des données :** plutôt que d’envoyer toutes les données utilisateur à un [!UICONTROL destination], [!UICONTROL Destination Builder] vous permet de partager uniquement des informations spécifiques sur les utilisateurs qualifiés.
* **Agissez sur vos données :** l’envoi de données à un partenaire [!UICONTROL destination] l’aide à développer et cibler rapidement des segments d’audience qualifiés.
* **Réduction des frais techniques :** utilisateurs professionnels peuvent configurer des [!UICONTROL destinations] en toute sécurité dans l’interface [!UICONTROL Destination Builder]. Cela permet de réduire le temps nécessaire aux tests de prédéploiement. Grâce à [!UICONTROL Destination Builder], vous pouvez créer, gérer et supprimer des [!UICONTROL destinations] à mesure que les besoins de votre entreprise évoluent, le tout sans avoir à passer par un long cycle de développement.

## Considérations techniques {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La diffusion des données dépend de la manière dont votre partenaire de données souhaite ou peut recevoir des informations [!UICONTROL destination]. Des contraintes techniques ou d’ingénierie peuvent empêcher un [!UICONTROL destination] de recevoir des données par le biais de processus [!DNL URL], [!UICONTROL cookie] ou [!UICONTROL server-to-server]. Collaborez avec votre partenaire tiers pour déterminer la méthode qu’il peut utiliser.

## Considérations commerciales {#business-considerations}

Les décisions commerciales relatives au choix d’une méthode de diffusion plutôt qu’une autre dépendent des capacités techniques de votre partenaire [!UICONTROL destination] et de ce que vous souhaitez faire avec les informations d’utilisateur qualifiées. Par exemple, des contraintes techniques peuvent limiter vos options si un [!UICONTROL destination] ne peut pas recevoir de données par une méthode de diffusion particulière. Cependant, en l’absence de problèmes techniques, vous pouvez envoyer des informations en fonction de la manière dont vous souhaitez agir sur ces données. Par exemple :

* Les [!DNL URL] et les [!UICONTROL cookie-based destinations] fonctionnent presque de manière synchrone avec les actions des utilisateurs sur une page.
* Les méthodes [!UICONTROL Server-to-server] sont adaptées à la création de segments d’audience profonds au fil du temps.

## Types de [!UICONTROL Destination] et utilisations standard {#destination-types}

Les exemples du tableau suivant peuvent vous aider à comprendre quand utiliser un [!UICONTROL destination] particulier et les différences entre chaque type.

| Type de [!UICONTROL Destination] | Généralement Utilisé Lorsque | Exemple | Considérations |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Vous devez envoyer des données à d’autres solutions Adobe Experience Cloud. | Envoi de données à Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Vous devez envoyer des segments d’audience à des environnements basés sur des personnes, tels que Facebook. | Diffuser des offres personnalisées aux clients existants en fonction de leur historique d’achats | Le ciblage des audiences est effectué au moyen d’identifiants hachés. Voir [Destinations Basées Sur Les Personnes](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**serveur à serveur**) | <ul><li>Le transfert immédiat des données n’est pas requis.</li><li>Collecter des données pour créer un grand pool d’audiences d’utilisateurs qualifiés.</li></ul> | Collecter des données au fil du temps (heures ou jours) pour les utiliser dans une campagne définie pour s’exécuter à une date ultérieure | <ul><li>Transfère des données sur les nouveaux et les anciens visiteurs du site. </li><li>Les visiteurs n’ont pas besoin d’être revus pour se qualifier pour d’autres segments.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** ou **Cookie**) | Vous devez transférer les données immédiatement afin qu’une destination puisse agir immédiatement sur un utilisateur qualifié. | Envoi de données à partir d’un site d’achat de billets. Utilisez un [!UICONTROL URL] ou un [!UICONTROL cookie destination] pour qualifier l’utilisateur et le recibler immédiatement. | <ul><li>Transfère uniquement les données sur les nouveaux visiteurs. </li><li>Les visiteurs doivent être revus pour se qualifier pour le segment.</li></ul> |
