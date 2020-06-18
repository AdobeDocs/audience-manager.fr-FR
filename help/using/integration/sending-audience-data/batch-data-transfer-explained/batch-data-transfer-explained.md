---
description: Présentation générale de la manière dont l’Audience Manager effectue un échange de données par lot asynchrone avec un fournisseur tiers.
seo-description: Présentation générale de la manière dont l’Audience Manager effectue un échange de données par lot asynchrone avec un fournisseur tiers.
seo-title: Description du processus de transfert de données par lot
solution: Audience Manager
title: Description du processus de transfert de données par lot
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 0%

---


# Description du processus de transfert de données par lot {#batch-data-transfer-process-described}

Présentation générale de la manière dont [!DNL Audience Manager] effectue un échange de données par lot asynchrone avec un fournisseur tiers.

## Intégration des données par lot

<!-- c_async.xml -->

Le processus d&#39;intégration des données par lot enregistre les informations des visiteurs sur nos serveurs et synchronise ces informations avec les données envoyées par un fournisseur à intervalles réguliers. Le processus de transfert de données asynchrone est utile lorsque :

* Les transferts de données immédiats ne sont pas nécessaires.
* Collecte de données pour créer un grand groupe d’utilisateurs segmentés.
* Vous souhaitez réduire les incohérences de données et les `HTTP` appels du navigateur.

![](assets/s2s_70.png)

## Étapes d’intégration des données

1. Un utilisateur visite un site client.
1. L’Audience Manager et le fournisseur de données tiers attribuent au visiteur un identifiant unique (généralement avec un cookie).
1. L’Audience Manager appelle le fournisseur de données tiers pour qu’il corresponde aux ID de visiteur.
1. Une demande planifiée, généralement à intervalles quotidiens, échange des données de segment de visiteur entre l’Audience Manager et votre fournisseur de données tiers.
1. Chaque fois qu&#39;un [!UICONTROL Server-to-Server] fichier entrant est traité, un reçu est envoyé par courrier électronique aux solutions partenaires et, s&#39;il est configuré, au partenaire. Pour plus d’informations, voir [Exemple de message aux partenaires après le traitement](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)entrant.