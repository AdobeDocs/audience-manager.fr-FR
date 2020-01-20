---
description: Dans Audience Manager, une destination correspond à tout système tiers (serveur d’annonces, fournisseur de services de distribution de données, réseau publicitaire, etc.). que vous souhaitez partager avec. Le créateur de destinations est l’outil utilisé pour créer et gérer des destinations de cookie, d’URL ou de serveur à serveur.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: Dans Audience Manager, une destination correspond à tout système tiers (serveur d’annonces, fournisseur de services de distribution de données, réseau publicitaire, etc.). que vous souhaitez partager avec. Le créateur de destinations est l’outil utilisé pour créer et gérer des destinations de cookie, d’URL ou de serveur à serveur.
seo-title: Destinations
solution: Audience Manager
title: Destinations
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
translation-type: tm+mt
source-git-commit: e141d04201b94bac30cdbe97818cb8eb91ebbaea

---


# Présentation des destinations {#destinations}

Dans Audience Manager, une destination est tout système tiers (serveur d’annonces, [!DNL DSP]réseau d’annonces, etc.) que vous souhaitez partager avec. [!UICONTROL Destination Builder] est l’outil que vous avez utilisé pour créer et gérer des destinations de cookie [!DNL URL]ou de serveur à serveur.

## Objectif et avantages {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] et vous [!UICONTROL Destination Builder] permet de créer des destinations et d’envoyer des informations sur les utilisateurs segmentés à votre partenaire de données. Cela vous aide à :

* **** Protéger la valeur des données : Plutôt que d’envoyer toutes les données utilisateur à une destination, [!UICONTROL Destination Builder] vous laissez partager des informations spécifiques sur les utilisateurs qualifiés uniquement.
* **** Agissez sur vos données : L’envoi de données à un partenaire de destination permet de développer et de cibler rapidement des segments d’audience qualifiés.
* **** Réduction des frais techniques : Les utilisateurs professionnels peuvent configurer des destinations en toute sécurité dans l’ [!UICONTROL Destination Builder] interface. Cela permet de réduire le temps requis pour les tests préalables au déploiement. Avec [!UICONTROL Destination Builder], vous créez, gérez et supprimez des destinations à mesure que vos besoins changent, le tout sans passer par un cycle de développement long.

## Considérations techniques {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La remise des données dépend de la manière dont votre partenaire de données souhaite ou peut recevoir les informations de destination. Des contraintes techniques ou techniques peuvent empêcher une destination de recevoir des données par le biais de processus [!DNL URL], de cookies ou de serveur à serveur. Consultez votre partenaire tiers pour déterminer la méthode qu’il peut utiliser.

## Considérations commerciales {#business-considerations}

Les décisions d&#39;entreprise concernant la sélection d&#39;un mode de livraison par rapport à un autre dépendent des capacités techniques de votre partenaire de destination et de ce que vous souhaitez faire avec les informations utilisateur qualifiées. Par exemple, des contraintes techniques peuvent limiter vos options si une destination ne peut pas recevoir de données par un mode de livraison particulier. Toutefois, s’il n’y a aucun problème technique, vous pouvez envoyer des informations en fonction de la manière dont vous souhaitez agir sur ces données. Par exemple :

* [!DNL URL]Les destinations basées sur les cookies et les destinations basées sur les cookies fonctionnent presque de manière synchrone avec les actions des utilisateurs sur une page.
* Les méthodes serveur à serveur sont utiles pour créer des segments d’audience profonds au fil du temps.

## Types de destination et utilisations types {#destination-types}

Les exemples du tableau suivant peuvent vous aider à comprendre quand utiliser une destination particulière et les différences entre chaque type.

| Type de destination | Généralement utilisé lorsque | Exemple | Considérations |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | Vous devez envoyer des données à d’autres solutions Adobe Experience Cloud. | Envoi de données à Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | Vous devez envoyer des segments d’audience à des environnements basés sur des personnes, tels que Facebook. | Proposer des offres personnalisées aux clients existants, en fonction de leur historique d’achat | Le ciblage de l’audience s’effectue par le biais d’identifiants hachés. Voir Destinations [basées sur les personnes](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]**(** Serveur à Serveur **) | <ul><li>Le transfert immédiat des données n’est pas nécessaire.</li><li>Collecte de données afin de créer un grand groupe d’audiences composé d’utilisateurs qualifiés.</li></ul> | Collecte de données au fil du temps (heures ou jours) pour les utiliser dans un jeu de campagnes à exécuter ultérieurement. | <ul><li>Transfère des données sur les visiteurs du site nouveaux et précédents. </li><li>Les visiteurs n’ont pas besoin d’être de nouveau affichés pour être admissibles à d’autres segments.</li></ul> |
| **[!UICONTROL Custom Destinations]**(** URL **ou** cookie **) | Vous devez transférer les données immédiatement afin qu’une destination puisse agir immédiatement sur un utilisateur qualifié. | Envoi de données à partir d’un site d’achat de billets. Utilisez une URL ou une destination de cookie pour qualifier l’utilisateur et le recibler immédiatement. | <ul><li>Transfère uniquement les données sur les nouveaux visiteurs. </li><li>Les visiteurs doivent être de nouveau affichés pour être admissibles au segment.</li></ul> |
