---
description: Présentation générale de la manière dont l’Audience Manager effectue des transferts de données en temps réel avec un fournisseur de contenu tiers.
seo-description: Présentation générale de la manière dont l’Audience Manager effectue des transferts de données en temps réel avec un fournisseur de contenu tiers.
seo-title: Description du processus de transfert de données en temps réel
solution: Audience Manager
title: Description du processus de transfert de données en temps réel
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---


# Processus de transfert de données en temps réel décrit{#real-time-data-transfer-process-described}

Présentation générale de la manière dont l’Audience Manager effectue des transferts de données en temps réel avec un fournisseur de contenu tiers.

<!-- real-time-data-transfer-explained.xml -->

## Transferts de données en temps réel

Les transferts de données en temps réel envoient et reçoivent des ID de segment lors de la visite d’un utilisateur ou d’une action sur votre site. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez qualifier ou segmenter immédiatement les utilisateurs lorsqu’ils naviguent dans votre inventaire.

## Étapes d’intégration des données

Le processus d’intégration des données en temps réel fonctionne comme suit :

1. Un utilisateur visite le site d’un client qui contient le code d’Audience Manager.
1. Audience Manager charge un iframe et appelle notre [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. [!DNL DCS] appelle le serveur tiers (en temps réel) pour vérifier si le fournisseur dispose d&#39;informations de segment sur l&#39;utilisateur.
1. Le fournisseur de contenu renvoie à l’Audience Manager les informations de segment concernant cet utilisateur.
1. L’Audience Manager reçoit ces informations de segment et les rend disponibles pour le ciblage et la création de nouvelles caractéristiques et de nouveaux segments.

![](assets/rt_reduce70.png)