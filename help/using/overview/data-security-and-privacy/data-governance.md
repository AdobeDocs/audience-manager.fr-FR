---
description: Ce document explique la manière dont les données client sont gérées dans Audience Manager.
seo-description: TThis document explains how customer data is governed in Audience Manager.
seo-title: Data Governance
solution: Audience Manager
keywords: Interface utilisateur du RGPD, API relative au RGPD, CCPA, confidentialité, consentement, obscurcissement, gouvernance
title: Gouvernance des données
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 90%

---

# Gouvernance des données

## Présentation {#overview}

La gouvernance des données dans Audience Manager renvoie au cycle de vie de vos données client dans Audience Manager et englobe la [collecte et l’obscurcissement des adresses IP](data-governance.md#collecting-ip-addresses), la [rétention des données](data-governance.md#data-retention) et les [transferts de données transfrontaliers](data-governance.md#data-transfers).

## Collecte et obscurcissement des adresses IP {#collecting-ip-addresses}

L’adresse [!DNL IP] d’un visiteur sur le site web d’un client est transmise à un [!DNL Data Processing Center] Adobe ([!DNL DPC]) où l’adresse [!DNL IP] peut être stockée. Selon la configuration du réseau du visiteur, l’adresse [!DNL IP] collectée ne correspond pas nécessairement à l’adresse [!DNL IP] de son ordinateur. L’adresse [!DNL IP] peut par exemple correspondre à l’adresse [!DNL IP] externe d’un pare-feu NAT (traduction d’adresses réseau), d’un proxy [!DNL HTTP] ou d’une passerelle Internet.

**Méthodologie d’obscurcissement des adresses IP :** conformément aux principes du « respect de la vie privée dès la conception », Adobe Audience Manager permet aux clients d’activer l’obscurcissement des adresses [!DNL IP] à partir de l’interface utilisateur, et ce dans l’ensemble des zones géographiques ou pour certains pays. Lorsque vous activez ce paramètre, le dernier octet (la dernière partie) de l’adresse [!DNL IP] est immédiatement ignoré lorsque l’adresse [!DNL IP] est ingérée dans Audience Manager. Audience Manager ignore cette partie de l’adresse [!DNL IP] avant le traitement (y compris avant toute recherche géographique ou journalisation facultative de l’adresse [!DNL IP]). Par exemple :

* Avant : `255.255.255.255`
* Après : `255.255.255.0`

>[!NOTE]
>
>Voir [ Obscurcissement des adresses IP ](../../features/administration/ip-obfuscation.md) pour apprendre à activer l’obscurcissement des adresses [!DNL IP] dans l’interface utilisateur de l’Audience Manager.

Regardez la vidéo ci-dessous pour comprendre comment fonctionne l’obscurcissement des adresses [!DNL IP] dans Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/34978?captions=fre_fr)

**Segmentation géographique :** si vous activez l’obscurcissement des adresses [!DNL IP], les octets restants de l’adresse [!DNL IP] peuvent toujours être utilisés pour la géosegmentation et la création de rapports dans Audience Manager. Si vous n’activez pas l’obscurcissement des adresses [!DNL IP], Audience Manager utilise l’adresse [!DNL IP] complète. Vous pouvez dans les deux cas utiliser la fonctionnalité de segmentation géographique qui vous permet d’identifier un emplacement [!DNL IP] selon sa zone géographique, mais l’obscurcissement des adresses [!DNL IP] en diminuera la précision. L’obtention d’informations sur les villes sera considérablement entravée par l’obscurcissement des adresses [!DNL IP], tandis que l’obtention des informations sur les régions et les pays ne sera que légèrement entravée. Les données de segmentation géographique sont alors détaillées au niveau des villes ou des codes postaux uniquement, mais pas au niveau individuel. En savoir plus sur le [géociblage](../../features/traits/trait-geotarget-keys.md) et la configuration de caractéristiques avec des variables géographiques.

## Rétention des données en Audience Manager {#data-retention}

L’application de stratégies appropriées, sécurisées et opportunes de rétention des données pour vos données est primordiale dans le respect des réglementations en matière de confidentialité des données. Les clients d’Audience Manager peuvent définir des périodes de rétention personnalisées sur les caractéristiques et les segments en définissant la durée de vie requise. Pour plus d’informations sur les périodes de rétention, reportez-vous à la [FAQ sur la rétention des données](../../faq/faq-privacy.md).

## Transferts de données transfrontaliers {#data-transfers}

Lorsqu’Audience Manager transfère des données personnelles des clients par-delà les frontières nationales, Audience Manager s’assure que ce transfert est conforme à la législation en vigueur. Consultez le [Centre de traitement des données personnelles Adobe](https://www.adobe.com/fr/privacy/eudatatransfers.html) pour en savoir plus.
