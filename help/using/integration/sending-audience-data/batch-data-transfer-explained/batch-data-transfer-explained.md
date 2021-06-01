---
description: Présentation générale de la manière dont l’Audience Manager effectue un échange de données par lots asynchrone avec un fournisseur tiers.
seo-description: Présentation générale de la manière dont l’Audience Manager effectue un échange de données par lots asynchrone avec un fournisseur tiers.
seo-title: Description du processus de transfert de données par lots
solution: Audience Manager
title: Description du processus de transfert de données par lots
uuid: a9eee940-151c-44f8-9fe9-8ab47d8fa45c
feature: Transferts des données entrantes
exl-id: e02dcc9a-4010-4c01-bd6b-ad04b8029f18
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# Description du processus de transfert de données par lots {#batch-data-transfer-process-described}

Présentation générale de la manière dont [!DNL Audience Manager] effectue un échange de données par lots asynchrone avec un fournisseur tiers.

## Intégration de données par lots

<!-- c_async.xml -->

Le processus d’intégration des données par lots enregistre les informations sur les visiteurs sur nos serveurs et synchronise ce matériel avec les données envoyées par un fournisseur à intervalles réguliers. Le processus de transfert de données asynchrone est utile dans les cas suivants :

* Les transferts de données immédiats ne sont pas requis.
* Collecte de données pour créer un grand groupe d’utilisateurs segmentés.
* Vous souhaitez réduire les incohérences de données et les appels `HTTP` du navigateur.

![](assets/s2s_70.png)

## Étapes d’intégration des données

1. Un utilisateur visite un site client.
1. [!DNL Audience Manager] et le fournisseur de données tiers affecte au visiteur un identifiant unique (généralement avec un cookie).
1. [!DNL Audience Manager] appelle le fournisseur de données tiers pour qu’il corresponde aux identifiants visiteur.
1. Une requête planifiée, généralement sur un intervalle quotidien, échange les données de segment des visiteurs entre [!DNL Audience Manager] et votre fournisseur de données tiers.
1. Chaque fois qu&#39;un fichier [!UICONTROL Server-to-Server] entrant est traité, un reçu est envoyé par email aux solutions partenaires et, s&#39;il est configuré, au partenaire. Pour plus d’informations, voir [Exemple de message aux partenaires après le traitement entrant](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-receipt-message.md).
