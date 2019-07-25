---
description: Dans Audience Manager, une destination est un système tiers (serveur d'annonces, DSP, réseau publicitaire, etc.) dont vous souhaitez partager les données. Le créateur de destinations est l'outil que vous avez utilisé pour créer et gérer les destinations de cookie, d'URL ou de serveur à serveur.
keywords: code d'intégration, destination, aperçu de destination
seo-description: Dans Audience Manager, une destination est un système tiers (serveur d'annonces, DSP, réseau publicitaire, etc.) dont vous souhaitez partager les données. Le créateur de destinations est l'outil que vous avez utilisé pour créer et gérer les destinations de cookie, d'URL ou de serveur à serveur.
seo-title: Destinations
solution: Audience Manager
title: Destinations
uuid: 5 c 7 dbdec-f 73 f -46 fe -9 f 12-7685 e 8 d 7334 f
translation-type: tm+mt
source-git-commit: 157e70906b80bd0a23ba6e7721d2c456d378ffb5

---


# Destinations {#destinations}

In Audience Manager, a destination is any third-party system (ad server, [!DNL DSP], ad network, etc.) dont vous souhaitez partager les données. [!UICONTROL Destination Builder] est l'outil que vous avez utilisé pour créer et gérer [!DNL URL]les destinations de serveur à serveur.

## Purpose and Advantages {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] et [!UICONTROL Destination Builder] vous permet de créer des destinations et d'envoyer des informations sur les utilisateurs segmentés à votre partenaire de données. Cela vous aide à :

* **Protégez la valeur de données :** Plutôt que d'envoyer toutes les données utilisateur à une destination, [!UICONTROL Destination Builder] vous pouvez partager des informations spécifiques sur les utilisateurs qualifiés uniquement.
* **Agir sur vos données :** L'envoi de données à un partenaire de destination les aide à développer et cibler rapidement des segments d'audience qualifiés.
* **Réduire les frais de surcharge technique :** Les utilisateurs professionnels peuvent configurer les destinations en toute sécurité dans [!UICONTROL Destination Builder] l'interface. Cela permet de réduire le temps nécessaire aux tests préalables au déploiement. With [!UICONTROL Destination Builder], you create, manage, and delete destinations as your business needs change, all without working through a long development cycle.

## Considérations techniques {#technical-considerations}

<!-- destination-delivery-methods.xml -->

La remise des données dépend de la manière dont votre partenaire de données souhaite ou peut recevoir les informations de destination. Technical or engineering constraints may prevent a destination from receiving data via [!DNL URL], cookie, or server-to-server processes. Collaborez avec votre partenaire tiers pour déterminer la méthode qu'ils peuvent utiliser.

## Considérations commerciales {#business-considerations}

Les décisions entreprises pour la sélection d'une méthode de livraison par rapport à une autre dépendent des fonctionnalités techniques de votre partenaire de destination et de ce que vous souhaitez faire avec les informations des utilisateurs qualifiés. Par exemple, les contraintes techniques peuvent limiter les options si une destination ne peut pas recevoir de données par une méthode de remise particulière. En revanche, en l'absence de problèmes techniques, vous pouvez envoyer des informations basées sur la manière dont vous souhaitez agir sur ces données. Par exemple :

* [!DNL URL]s et les destinations basées sur cookie fonctionnent de manière presque synchrone avec les actions de l'utilisateur sur une page.
* Les méthodes serveur à serveur sont utiles pour créer des segments d'audience profonds au fil du temps.

## Destination Types and Typical Uses {#destination-types}

Les exemples du tableau ci-dessous peuvent vous aider à comprendre quand utiliser une destination spécifique et les différences entre chaque type.

| Type de destination | Généralement utilisé lorsque | Exemple | Considérations |
|--- |--- |--- |--- |
| **URL** ou **cookie** | Vous devez transférer les données immédiatement afin qu'une destination puisse agir sur un utilisateur qualifié à droite. | Envoi de données à partir d'un site d'achat de billets. Utilisez une URL ou une destination de cookie pour qualifier l'utilisateur et recibler immédiatement. | <ul><li>Transfert des données sur les nouveaux visiteurs uniquement. </li><li>Les visiteurs doivent être reconnectés pour qu'ils remplissent les critères du segment.</li></ul> |
| **Serveur à serveur** | <ul><li>Le transfert de données immédiat n'est pas obligatoire.</li><li>Collecte de données pour créer un large groupe d'utilisateurs qualifiés.</li></ul> | Collecte de données au fil du temps (heures ou jours) pour l'utiliser dans une campagne définie pour une exécution ultérieure. | <ul><li>Transfère les données sur les nouveaux visiteurs et les visiteurs précédents. </li><li>Les visiteurs n'ont pas besoin d'être reconnectés pour les autres segments.</li></ul> |
