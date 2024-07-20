---
description: Présentation générale de la manière dont l’Audience Manager effectue des transferts de données en temps réel avec un fournisseur de contenu tiers.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Description du processus de transfert de données en temps réel
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---


# Description du processus de transfert de données en temps réel{#real-time-data-transfer-process-described}

Présentation générale de la manière dont l’Audience Manager effectue des transferts de données en temps réel avec un fournisseur de contenu tiers.

<!-- real-time-data-transfer-explained.xml -->

## Transferts de données en temps réel

Les transferts de données en temps réel envoient et reçoivent des identifiants de segment lorsqu’un utilisateur visite votre site ou effectue une action sur celui-ci. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez qualifier ou segmenter immédiatement les utilisateurs lorsqu’ils parcourent votre inventaire.

## Étapes d’intégration des données

Le processus d’intégration des données en temps réel fonctionne comme suit :

1. Un utilisateur visite le site d’un client qui contient le code d’Audience Manager.
1. Audience Manager charge un iframe et appelle notre [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. [!DNL DCS] appelle le serveur tiers (en temps réel) pour vérifier si le fournisseur dispose d’informations sur le segment de l’utilisateur.
1. Le fournisseur de contenu renvoie à l’Audience Manager des informations de segment sur cet utilisateur.
1. L’Audience Manager reçoit ces informations sur les segments et les met à disposition pour le ciblage et la création de nouvelles caractéristiques et de nouveaux segments.

![](assets/rt_reduce70.png)