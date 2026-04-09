---
description: Ce document explique la manière dont les données client sont gérées dans Audience Manager.
seo-description: TThis document explains how customer data is governed in Audience Manager.
seo-title: Data Governance
solution: Audience Manager
keywords: RGPD UI, RGPD API, CCPA, confidentialité, consentement, obscurcissement, gouvernance
title: Gouvernance des données
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
TQID: https://experienceleague.adobe.com/HVF-SxKO4mcE7YkiiwXLBPn2K3N5NIjpZHFWgZb0CoI
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a99472c1-6aae-4c7a-8aa0-f60636369620
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: a49258d4-867f-4130-b875-d72c001bdf6c
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: cc72dcf1-72e1-48cc-b434-e7c27d62d67c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 451
ht-degree: 90%

---

# Gouvernance des données

## Présentation {#overview}

La gouvernance des données dans Audience Manager renvoie au cycle de vie de vos données client dans Audience Manager et englobe la [collecte et l’obscurcissement des adresses IP](data-governance.md#collecting-ip-addresses), la [rétention des données](data-governance.md#data-retention) et les [transferts de données transfrontaliers](data-governance.md#data-transfers).

## Collecte des adresses IP et de l’obscurcissement des adresses IP {#collecting-ip-addresses}

L’adresse [!DNL IP] d’un visiteur sur le site web d’un client est transmise à un [!DNL Data Processing Center] Adobe ([!DNL DPC]) où l’adresse [!DNL IP] peut être stockée. Selon la configuration du réseau du visiteur, l’adresse [!DNL IP] collectée ne correspond pas nécessairement à l’adresse [!DNL IP] de son ordinateur. L’adresse [!DNL IP] peut par exemple correspondre à l’adresse [!DNL IP] externe d’un pare-feu NAT (traduction d’adresses réseau), d’un proxy [!DNL HTTP] ou d’une passerelle Internet.

**Méthodologie d’obscurcissement des adresses IP :** conformément aux principes du « respect de la vie privée dès la conception », Adobe Audience Manager permet aux clients d’activer l’obscurcissement des adresses [!DNL IP] à partir de l’interface utilisateur, et ce dans l’ensemble des zones géographiques ou pour certains pays. Lorsque vous activez ce paramètre, le dernier octet (la dernière partie) de l’adresse [!DNL IP] est immédiatement ignoré lorsque l’adresse [!DNL IP] est ingérée dans Audience Manager. Audience Manager ignore cette partie de l’adresse [!DNL IP] avant le traitement (y compris avant toute recherche géographique ou journalisation facultative de l’adresse [!DNL IP]). Par exemple :

* Avant : `255.255.255.255`
* Après : `255.255.255.0`

>[!NOTE]
>
>Consultez la section [&#x200B; Obscurcissement d’adresse IP &#x200B;](../../features/administration/ip-obfuscation.md) pour savoir comment activer l’obscurcissement d’adresse [!DNL IP] dans l’interface utilisateur d’Audience Manager.

Regardez la vidéo ci-dessous pour comprendre comment fonctionne l’obscurcissement des adresses [!DNL IP] dans Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/34978?captions=fre_fr)

**Segmentation géographique :** si vous activez l’obscurcissement des adresses [!DNL IP], les octets restants de l’adresse [!DNL IP] peuvent toujours être utilisés pour la géosegmentation et la création de rapports dans Audience Manager. Si vous n’activez pas l’obscurcissement des adresses [!DNL IP], Audience Manager utilise l’adresse [!DNL IP] complète. Vous pouvez dans les deux cas utiliser la fonctionnalité de segmentation géographique qui vous permet d’identifier un emplacement [!DNL IP] selon sa zone géographique, mais l’obscurcissement des adresses [!DNL IP] en diminuera la précision. L’obtention d’informations sur les villes sera considérablement entravée par l’obscurcissement des adresses [!DNL IP], tandis que l’obtention des informations sur les régions et les pays ne sera que légèrement entravée. Les données de segmentation géographique sont alors détaillées au niveau des villes ou des codes postaux uniquement, mais pas au niveau individuel. En savoir plus sur le [géociblage](../../features/traits/trait-geotarget-keys.md) et la configuration de caractéristiques avec des variables géographiques.

## Conservation des données dans Audience Manager {#data-retention}

L’application de stratégies appropriées, sécurisées et opportunes de rétention des données pour vos données est primordiale dans le respect des réglementations en matière de confidentialité des données. Les clients d’Audience Manager peuvent définir des périodes de rétention personnalisées sur les caractéristiques et les segments en définissant la durée de vie requise. Pour plus d’informations sur les périodes de rétention, reportez-vous à la [FAQ sur la rétention des données](../../faq/faq-privacy.md).

## Transferts Transfrontaliers De Données {#data-transfers}

Lorsqu’Audience Manager transfère des données personnelles des clients par-delà les frontières nationales, Audience Manager s’assure que ce transfert est conforme à la législation en vigueur. Consultez le [Centre de traitement des données personnelles Adobe](https://www.adobe.com/fr/privacy/eudatatransfers.html) pour en savoir plus.
