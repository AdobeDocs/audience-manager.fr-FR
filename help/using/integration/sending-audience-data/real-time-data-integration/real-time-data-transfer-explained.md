---
description: Présentation générale de la manière dont Audience Manager effectue des transferts de données en temps réel avec un fournisseur de contenu tiers.
seo-description: Présentation générale de la manière dont Audience Manager effectue des transferts de données en temps réel avec un fournisseur de contenu tiers.
seo-title: Real - Time Data Transfer Process décrit
solution: Audience Manager
title: Real - Time Data Transfer Process décrit
uuid: b 68781 b 3-0 b 7 a -442 d -8 e 34-2 db 2474849 a 4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Real-Time Data Transfer Process Described{#real-time-data-transfer-process-described}

Présentation générale de la manière dont Audience Manager effectue des transferts de données en temps réel avec un fournisseur de contenu tiers.

<!-- real-time-data-transfer-explained.xml -->

## Real - Time Data Transfer

Les données en temps réel permettent de transférer et de recevoir des ID de segment en tant qu'utilisateurs de visites ou d'actions sur votre site. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez qualifier ou segmenter les utilisateurs à droite, à mesure qu'ils naviguent dans votre inventaire.

## Étapes d'intégration des données

Le processus d'intégration des données en temps réel fonctionne comme suit :

1. Un utilisateur visite le site d'un client qui contient le code Audience Manager.
1. Audience Manager loads an iframe and makes a call to our [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]).
1. The [!UICONTROL DCS] calls the third-party server (in real time) to check if the vendor has any segment information about the user.
1. Le fournisseur de contenu renvoie les informations de segment relatives à cet utilisateur à Audience Manager.
1. Audience Manager reçoit ces informations de segment et les rend disponibles pour le ciblage et la création de nouvelles caractéristiques et de segments.

![](assets/rt_reduce70.png)