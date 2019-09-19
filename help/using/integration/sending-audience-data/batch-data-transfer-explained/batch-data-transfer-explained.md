---
description: Présentation générale d’Audience Manager qui effectue un échange asynchrone de données par lot avec un fournisseur tiers.
seo-description: Présentation générale d’Audience Manager qui effectue un échange asynchrone de données par lot avec un fournisseur tiers.
seo-title: Description du processus de transfert de données par lot
solution: Audience Manager
title: Description du processus de transfert de données par lot
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Description du processus de transfert de données par lot {#batch-data-transfer-process-described}

Présentation générale d’Audience Manager qui effectue un échange asynchrone de données par lot avec un fournisseur tiers.

## Intégration des données par lot

<!-- c_async.xml -->

Le processus d’intégration des données par lot enregistre les informations sur les visiteurs sur nos serveurs et synchronise ce matériel avec les données envoyées par un fournisseur à intervalles réguliers. Le processus de transfert de données asynchrone est utile lorsque :

* Les transferts de données immédiats ne sont pas nécessaires.
* Collecte de données pour créer un grand groupe d’utilisateurs segmentés.
* Vous souhaitez réduire les incohérences de données et `HTTP` les appels du navigateur.

![](assets/s2s_70.png)

## Etapes d’intégration des données

1. Un utilisateur visite un site client.
1. Audience Manager et le fournisseur de données tiers attribuent au visiteur un identifiant unique (généralement avec un cookie).
1. Audience Manager appelle le fournisseur de données tiers pour qu’il corresponde aux identifiants des visiteurs.
1. Une requête planifiée, généralement sur un intervalle quotidien, échange des données de segmentation des visiteurs entre Audience Manager et votre fournisseur de données tiers.
1. Chaque fois qu’un [!UICONTROL Server-to-Server] fichier entrant est traité, un reçu est envoyé par courrier électronique aux solutions partenaires et, s’il est configuré, au partenaire. Pour plus d’informations, voir [Exemple de message aux partenaires après le traitement](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md)entrant.