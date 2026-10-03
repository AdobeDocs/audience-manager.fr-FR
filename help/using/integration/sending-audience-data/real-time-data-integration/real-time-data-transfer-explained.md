---
description: Présentation générale de la manière dont Audience Manager effectue des transferts de données en temps réel avec un fournisseur de contenu tiers.
seo-description: A general overview of how Audience Manager performs real-time data transfers with a third-party content provider.
seo-title: Real-Time Data Transfer Process Described
solution: Audience Manager
title: Description Du Processus De Transfert De Données En Temps Réel
uuid: b68781b3-0b7a-442d-8e34-2db2474849a4
feature: Inbound Data Transfers
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
    internal-label: Audience Manager
feature_v2:
  - id: b82b475d-1e7d-46c6-9172-1f9c73004b11
    internal-label: Integrations
subfeature_v2:
  - id: a03b8192-8410-479f-a326-4cddf10757f6
    internal-label: Inbound data transfers
source-git-commit: f188b550f327b59bab9f26bdd5e95bda6c1c0be9
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 0%
---

# Description Du Processus De Transfert De Données En Temps Réel{#real-time-data-transfer-process-described}

Présentation générale de la manière dont Audience Manager effectue des transferts de données en temps réel avec un fournisseur de contenu tiers.

<!-- real-time-data-transfer-explained.xml -->

## Transferts De Données En Temps Réel

Les transferts de données en temps réel envoient et reçoivent des identifiants de segment lorsqu’un utilisateur visite votre site ou y effectue une action. En règle générale, les transferts de données synchrones sont utiles lorsque vous devez qualifier ou segmenter les utilisateurs immédiatement, lorsqu’ils parcourent votre inventaire.

## Étapes d’intégration des données

Le processus d’intégration des données en temps réel fonctionne comme suit :

1. Un utilisateur visite le site d’un client qui contient du code Audience Manager.
1. Audience Manager charge un iframe et effectue un appel à notre [!UICONTROL Data Collection Server] ( [!DNL DCS]).
1. Le [!DNL DCS] appelle le serveur tiers (en temps réel) pour vérifier si le fournisseur dispose d’informations sur les segments de l’utilisateur.
1. Le fournisseur de contenu renvoie à Audience Manager des informations sur le segment de cet utilisateur.
1. Audience Manager reçoit ces informations sur les segments et les met à disposition pour le ciblage et la création de nouvelles caractéristiques et de nouveaux segments.

![](assets/rt_reduce70.png)