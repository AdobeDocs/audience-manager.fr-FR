---
description: Dans Audience Manager, une destination est un système tiers (serveur publicitaire, DSP, réseau publicitaire, etc.) avec lequel vous souhaitez partager des données. Destination Builder est l’outil utilisé pour créer et gérer des destinations de cookie, d’URL ou de serveur à serveur.
keywords: code d’intégration, destination, présentation de destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
landing-page-description: Une destination désigne tout système tiers avec lequel partager des données, par exemple un serveur de publicités ou un DSP. Utilisez Destination Builder pour créer et gérer des destinations de cookie, d’URL ou de serveur à serveur.
seo-title: 'Destinations '
solution: Audience Manager
title: Destinations
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Concepts de base des destinations
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---

# [!UICONTROL Destinations] Présentation {#destinations}

En Audience Manager, un [!UICONTROL destination] est un système tiers (serveur de publicités, [!DNL DSP], réseau publicitaire, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] est l’outil utilisé pour créer et gérer  [!UICONTROL cookie],  [!DNL URL] ou  [!UICONTROL server-to-server destinations].

## Objectif et avantages {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] et vous  [!UICONTROL Destination Builder] permettent de créer  [!UICONTROL destinations] et d’envoyer des informations sur les utilisateurs segmentés à votre partenaire de données. Vous pouvez ainsi :

* **Valeur de données Protect :** au lieu d’envoyer toutes les données utilisateur à un  [!UICONTROL destination],  [!UICONTROL Destination Builder] vous permet de partager uniquement des informations spécifiques sur les utilisateurs qualifiés.
* **Agir sur vos données :** l’envoi de données à un  [!UICONTROL destination] partenaire les aide à développer et à cibler rapidement les segments d’audience qualifiés.
* **Réduction des frais techniques :** les utilisateurs professionnels peuvent configurer  [!UICONTROL destinations] en toute sécurité dans l’ [!UICONTROL Destination Builder] interface. Cela permet de réduire le temps nécessaire aux tests de pré-déploiement. Avec [!UICONTROL Destination Builder], vous créez, gérez et supprimez [!UICONTROL destinations] à mesure que les besoins de votre entreprise changent, le tout sans passer par un cycle de développement long.

## Considérations techniques {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La remise des données dépend de la manière dont votre partenaire de données souhaite recevoir ou peut recevoir des [!UICONTROL destination] informations. Des contraintes techniques ou techniques peuvent empêcher un [!UICONTROL destination] de recevoir des données par l’intermédiaire de processus [!DNL URL], [!UICONTROL cookie] ou [!UICONTROL server-to-server]. Collaborez avec votre partenaire tiers pour déterminer la méthode qu’il peut utiliser.

## Considérations commerciales {#business-considerations}

Les décisions commerciales relatives à la sélection d’un mode de diffusion plutôt que d’un autre dépendent des capacités techniques de votre partenaire [!UICONTROL destination] et de ce que vous souhaitez faire avec des informations utilisateur qualifiées. Par exemple, des contraintes techniques peuvent limiter vos options si une [!UICONTROL destination] ne peut pas recevoir de données par une méthode de diffusion particulière. Cependant, s’il n’y a aucun problème technique, vous pouvez envoyer des informations en fonction de la manière dont vous souhaitez agir sur ces données. Par exemple :

* [!DNL URL]et  [!UICONTROL cookie-based destinations] fonctionnent presque de manière synchrone avec les actions de l’utilisateur sur une page.
* [!UICONTROL Server-to-server] est utile pour créer des segments d’audience profonds au fil du temps.

## [!UICONTROL Destination] Types et utilisations standard  {#destination-types}

Les exemples du tableau suivant peuvent vous aider à comprendre quand utiliser une [!UICONTROL destination] spécifique et les différences entre chaque type.

| [!UICONTROL Destination] Tapez | Généralement utilisé lorsque | Exemple | Considérations |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Vous devez envoyer des données à d’autres solutions Adobe Experience Cloud. | Envoi de données à Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Vous devez envoyer des segments d’audience à des environnements basés sur des personnes, tels que Facebook. | Diffuser des offres personnalisées aux clients existants, en fonction de leur historique d&#39;achat | Le ciblage des audiences s’effectue par le biais d’identifiants hachés. Voir [Destinations basées sur les personnes](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Serveur à serveur**) | <ul><li>Le transfert de données immédiat n’est pas obligatoire.</li><li>Collecte de données pour créer un grand groupe d’audiences d’utilisateurs qualifiés.</li></ul> | Collecter les données au fil du temps (heures ou jours) pour les utiliser dans un ensemble de campagnes afin qu’elles s’exécutent à une date ultérieure. | <ul><li>Transfère des données sur les nouveaux visiteurs et les visiteurs précédents du site. </li><li>Il n’est pas nécessaire que les visiteurs soient de nouveau visibles pour d’autres segments.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URLou  **cookie**) | Vous devez transférer des données immédiatement afin qu’une destination puisse agir immédiatement sur un utilisateur qualifié. | Envoi de données à partir d’un site d’achat de tickets. Utilisez une balise [!UICONTROL URL] ou [!UICONTROL cookie destination] pour qualifier l’utilisateur et le recibler immédiatement. | <ul><li>Transfère des données sur les nouveaux visiteurs uniquement. </li><li>Les visiteurs doivent être de nouveau affichés pour être admissibles au segment.</li></ul> |
