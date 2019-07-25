---
description: Présentation générale de la manière dont Audience Manager effectue un échange asynchrone de données par lots avec un fournisseur tiers.
seo-description: Présentation générale de la manière dont Audience Manager effectue un échange asynchrone de données par lots avec un fournisseur tiers.
seo-title: Processus de transfert des données par lots décrit
solution: Audience Manager
title: Processus de transfert des données par lots décrit
uuid: a 9 eee 940-151 c -44 f 8-9 fe 9-8 ab 47 d 8 fa 45 c
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Batch Data Transfer Process Described {#batch-data-transfer-process-described}

Présentation générale de la manière dont Audience Manager effectue un échange asynchrone de données par lots avec un fournisseur tiers.

## Intégration de données par lots

<!-- c_async.xml -->

Le processus d'intégration des données par lots enregistre les informations des visiteurs sur nos serveurs et synchronise ce matériel avec les données envoyées par un fournisseur à intervalles réguliers. Le processus asynchrone de transfert des données est utile lorsque :

* Les transferts de données immédiats ne sont pas requis.
* Collecte de données pour créer un grand pool d'utilisateurs segmentés.
* You want to reduce data discrepancies and `HTTP` calls from the browser.

![](assets/s2s_70.png)

## Étapes d'intégration des données

1. Un utilisateur visite un site client.
1. Audience Manager et le fournisseur de données tiers attribuent au visiteur un identifiant unique (généralement avec un cookie).
1. Audience Manager appelle le fournisseur de données tiers pour correspondre aux identifiants des visiteurs.
1. Une requête planifiée, généralement sur une fréquence quotidienne, échange les données de segmentation des visiteurs entre Audience Manager et votre fournisseur de données tiers.
1. Whenever an inbound [!UICONTROL Server-to-Server] file is processed, a receipt is sent via email to partner solutions and, if configured, to the partner. For more information, see [Sample Message to Partners after Inbound Processing](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).