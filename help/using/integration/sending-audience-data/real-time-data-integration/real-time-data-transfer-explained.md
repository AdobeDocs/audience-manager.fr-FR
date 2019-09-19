---
description: Présentation générale de la manière dont Audience Manager effectue les transferts de données en temps réel avec un fournisseur de contenu tiers.
seo-description: Présentation générale de la manière dont Audience Manager effectue les transferts de données en temps réel avec un fournisseur de contenu tiers.
seo-title: Description du processus de transfert de données en temps réel
solution: Audience Manager
title: Description du processus de transfert de données en temps réel
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
translation-type: tm+mt
source-git-commit: ea95df8531c00c183f22b09a4a78fc6b35ee279d

---


# Description du processus de transfert de données en temps réel{#real-time-data-transfer-process-described}

Présentation générale de la manière dont Audience Manager effectue les transferts de données en temps réel avec un fournisseur de contenu tiers.

<!-- real-time-data-transfer-explained.xml -->

## Transferts de données en temps réel

Les transferts de données en temps réel envoient et reçoivent des ID de segment lorsqu’un utilisateur visite votre site ou agit sur votre site. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez immédiatement qualifier ou segmenter les utilisateurs, lorsqu’ils naviguent dans votre inventaire.

## Etapes d’intégration des données

Le processus d’intégration des données en temps réel fonctionne comme suit :

1. Un utilisateur visite le site d’un client qui contient le code Audience Manager.
1. Audience Manager charge un iframe et appelle notre [!UICONTROL Data Collection Server] ( [!UICONTROL DCS]).
1. L’ [!UICONTROL DCS] opérateur appelle le serveur tiers (en temps réel) pour vérifier si le fournisseur dispose d’informations de segment sur l’utilisateur.
1. Le fournisseur de contenu renvoie les informations de segment concernant cet utilisateur à Audience Manager.
1. Audience Manager reçoit ces informations sur les segments et les rend disponibles pour le ciblage et la création de nouvelles caractéristiques et de nouveaux segments.

![](assets/rt_reduce70.png)