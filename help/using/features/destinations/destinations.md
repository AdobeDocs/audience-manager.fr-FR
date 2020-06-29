---
description: En Audience Manager, une destination est tout système tiers (serveur publicitaire, DSP, réseau publicitaire, etc.) que vous souhaitez partager avec. Le créateur de destinations est l’outil utilisé pour créer et gérer des destinations de cookie, d’URL ou de serveur à serveur.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: En Audience Manager, une destination est tout système tiers (serveur publicitaire, DSP, réseau publicitaire, etc.) que vous souhaitez partager avec. Le créateur de destinations est l’outil utilisé pour créer et gérer des destinations de cookie, d’URL ou de serveur à serveur.
seo-title: 'Destinations '
solution: Audience Manager
title: 'Destinations '
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 2%

---


# [!UICONTROL Destinations] Aperçu {#destinations}

En Audience Manager, un [!UICONTROL destination] est un système tiers (serveur publicitaire, [!DNL DSP]réseau publicitaire, etc.) que vous souhaitez partager avec. [!UICONTROL Destination Builder] est l’outil que vous avez utilisé pour créer et gérer [!UICONTROL cookie], [!DNL URL]ou [!UICONTROL server-to-server destinations].

## Objectif et avantages {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] et [!UICONTROL Destination Builder] vous permettent de créer [!UICONTROL destinations] et d’envoyer des informations sur les utilisateurs segmentés à votre partenaire de données. Cela vous aide à :

* **Protéger la valeur des données :** Plutôt que d’envoyer toutes les données utilisateur à un [!UICONTROL destination]utilisateur, [!UICONTROL Destination Builder] vous permet de partager uniquement des informations spécifiques sur les utilisateurs qualifiés.
* **Agissez sur vos données :** L’envoi de données à un [!UICONTROL destination] partenaire les aide à développer et à cible rapidement des segments d’audience qualifiés.
* **Réduire les frais techniques :** Les utilisateurs professionnels peuvent configurer [!UICONTROL destinations] en toute sécurité dans l’ [!UICONTROL Destination Builder] interface. Cela permet de réduire le temps nécessaire aux tests de pré-déploiement. Avec [!UICONTROL Destination Builder], vous créez, gérez et supprimez [!UICONTROL destinations] à mesure que vos besoins changent, le tout sans passer par un long cycle de développement.

## Considérations techniques {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La diffusion des données dépend de la manière dont votre partenaire de données souhaite recevoir ou peut recevoir [!UICONTROL destination] des informations. Des contraintes techniques ou techniques peuvent empêcher un utilisateur [!UICONTROL destination] de recevoir des données par le biais [!DNL URL][!UICONTROL cookie], ou de [!UICONTROL server-to-server] processus. Contactez votre partenaire tiers pour déterminer la méthode qu’il peut utiliser.

## Considérations commerciales {#business-considerations}

Les décisions d&#39;entreprise concernant la sélection d&#39;une méthode de diffusion par rapport à une autre dépendent des capacités techniques de votre [!UICONTROL destination] partenaire et de ce que vous souhaitez faire avec des informations d&#39;utilisateur qualifiées. Par exemple, des contraintes techniques peuvent limiter vos options si une [!UICONTROL destination] personne ne peut pas recevoir de données selon une méthode de diffusion particulière. Toutefois, s’il n’y a aucun problème technique, vous pouvez envoyer des informations en fonction de la manière dont vous souhaitez agir sur ces données. Par exemple :

* [!DNL URL]s et [!UICONTROL cookie-based destinations] fonctionnent presque de manière synchrone avec les actions de l’utilisateur sur une page.
* [!UICONTROL Server-to-server] sont utiles pour créer des segments d’audience profonds au fil du temps.

## [!UICONTROL Destination] Types et utilisations types {#destination-types}

Les exemples du tableau suivant peuvent vous aider à comprendre quand utiliser un type particulier [!UICONTROL destination] et les différences entre chaque type.

| [!UICONTROL Destination] Tapez | Généralement utilisé lorsque | Exemple | Considérations |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Vous devez envoyer des données à d’autres solutions Adobe Experience Cloud. | Envoi de données à Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Vous devez envoyer des segments d’audience à des environnements basés sur des personnes, tels que Facebook. | Fourniture d&#39;offres personnalisées aux clients existants, en fonction de leur historique d&#39;achat | Le ciblage des Audiences s’effectue par le biais d’identifiants hachés. Voir Destinations [basées sur](people-based-destinations-overview.md)les personnes. |
| **[!UICONTROL Device-Based Destinations]** (**Serveur à Serveur**) | <ul><li>Le transfert immédiat des données n’est pas nécessaire.</li><li>Collecte de données pour créer un grand pool d’audiences d’utilisateurs qualifiés.</li></ul> | Collecte de données au fil du temps (heures ou jours) pour les utiliser dans un jeu de campagnes à exécuter ultérieurement. | <ul><li>Transfère les données sur les nouveaux visiteurs et les anciens  du site. </li><li>Les Visiteurs n&#39;ont pas besoin d&#39;être revus pour être inclus dans d&#39;autres segments.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** ou **cookie**) | Vous devez transférer les données immédiatement afin qu’une destination puisse agir immédiatement sur un utilisateur qualifié. | Envoi de données à partir d’un site d’achat de tickets. Utilisez un [!UICONTROL URL] ou [!UICONTROL cookie destination] pour qualifier l’utilisateur et redéfinissez immédiatement la cible. | <ul><li>Transfère uniquement les données sur les nouveaux visiteurs. </li><li>Les Visiteurs doivent être de nouveau vus pour être inclus dans le segment.</li></ul> |
