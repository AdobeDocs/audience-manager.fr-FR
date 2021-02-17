---
description: Dans Audience Manager, une destination est un système tiers (serveur publicitaire, DSP, réseau publicitaire, etc.) avec lequel vous souhaitez partager des données. Destination Builder est l’outil utilisé pour créer et gérer des destinations de cookie, d’URL ou de serveur à serveur.
keywords: code d’intégration, destination, aperçu de la destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
landing-page-description: Une destination désigne tout système tiers avec lequel partager des données, par exemple un serveur de publicités ou un DSP. Utilisez Destination Builder pour créer et gérer des destinations de cookie, d’URL ou de serveur à serveur.
seo-title: 'Destinations '
solution: Audience Manager
title: 'Destinations '
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e6348c85e7df6428802d54b2c90385ce95f50e1a
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 15%

---


# [!UICONTROL Destinations] Présentation {#destinations}

En Audience Manager, un [!UICONTROL destination] correspond à tout système tiers (serveur publicitaire, [!DNL DSP], réseau publicitaire, etc.) avec lequel vous souhaitez partager des données. [!UICONTROL Destination Builder] est l’outil que vous avez utilisé pour créer et gérer  [!UICONTROL cookie],  [!DNL URL] ou  [!UICONTROL server-to-server destinations].

## Objectif et avantages {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] et vous  [!UICONTROL Destination Builder] permettent de créer  [!UICONTROL destinations] et d’envoyer des informations sur les utilisateurs segmentés à votre partenaire de données. Cela vous aide à :

* **Valeur de données Protect :** Plutôt que d’envoyer toutes les données utilisateur à un  [!UICONTROL destination]utilisateur, vous  [!UICONTROL Destination Builder] permet de partager des informations spécifiques sur les utilisateurs qualifiés uniquement.
* **Agissez sur vos données :** L’envoi de données à un  [!UICONTROL destination] partenaire permet de développer et de cible rapidement des segments d’audience qualifiés.
* **Réduction des frais techniques : les utilisateurs** professionnels peuvent configurer  [!UICONTROL destinations] en toute sécurité dans l’ [!UICONTROL Destination Builder] interface. Cela permet de réduire le temps nécessaire aux tests de pré-déploiement. Avec [!UICONTROL Destination Builder], vous créez, gérez et supprimez [!UICONTROL destinations] à mesure que vos besoins changent, le tout sans passer par un cycle de développement long.

## Considérations techniques {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La diffusion des données dépend de la manière dont votre partenaire de données souhaite recevoir ou peut recevoir des informations [!UICONTROL destination]. Des contraintes techniques ou techniques peuvent empêcher un [!UICONTROL destination] de recevoir des données par le biais de [!DNL URL], [!UICONTROL cookie] ou de [!UICONTROL server-to-server] processus. Contactez votre partenaire tiers pour déterminer la méthode qu’il peut utiliser.

## Considérations commerciales {#business-considerations}

Les décisions d&#39;entreprise concernant la sélection d&#39;une méthode de diffusion par rapport à une autre dépendent des capacités techniques de votre partenaire [!UICONTROL destination] et de ce que vous souhaitez faire avec les informations utilisateur qualifiées. Par exemple, des contraintes techniques peuvent limiter vos options si un [!UICONTROL destination] ne peut pas recevoir de données par une méthode de diffusion particulière. Toutefois, s’il n’y a aucun problème technique, vous pouvez envoyer des informations en fonction de la manière dont vous souhaitez agir sur ces données. Par exemple :

* [!DNL URL]s et  [!UICONTROL cookie-based destinations] fonctionnent presque de manière synchrone avec les actions de l’utilisateur sur une page.
* [!UICONTROL Server-to-server] sont utiles pour créer des segments d’audience profonds au fil du temps.

## [!UICONTROL Destination] Types et utilisations types  {#destination-types}

Les exemples du tableau suivant peuvent vous aider à comprendre quand utiliser un [!UICONTROL destination] particulier et les différences entre chaque type.

| [!UICONTROL Destination] Tapez | Généralement utilisé lorsque | Exemple | Considérations |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Vous devez envoyer des données à d’autres solutions Adobe Experience Cloud. | Envoi de données à Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Vous devez envoyer des segments d’audience à des environnements basés sur des personnes, tels que Facebook. | Fourniture d&#39;offres personnalisées aux clients existants, en fonction de leur historique d&#39;achat | Le ciblage des Audiences s’effectue par le biais d’identifiants hachés. Voir [Destinations basées sur les personnes](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Serveur à Serveur**) | <ul><li>Le transfert immédiat des données n’est pas nécessaire.</li><li>Collecte de données pour créer un grand pool d’audiences d’utilisateurs qualifiés.</li></ul> | Collecte de données au fil du temps (heures ou jours) pour les utiliser dans un jeu de campagnes à exécuter ultérieurement. | <ul><li>Transfère les données sur les nouveaux visiteurs et les anciens  du site. </li><li>Les visiteurs n&#39;ont pas besoin d&#39;être revus pour être inclus dans d&#39;autres segments.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**** URLou  **cookie**) | Vous devez transférer les données immédiatement afin qu’une destination puisse agir immédiatement sur un utilisateur qualifié. | Envoi de données à partir d’un site d’achat de tickets. Utilisez [!UICONTROL URL] ou [!UICONTROL cookie destination] pour qualifier l’utilisateur et effectuer une nouvelle cible immédiatement. | <ul><li>Transfère uniquement les données sur les nouveaux visiteurs. </li><li>Les visiteurs doivent être de nouveau vus pour être inclus dans le segment.</li></ul> |
