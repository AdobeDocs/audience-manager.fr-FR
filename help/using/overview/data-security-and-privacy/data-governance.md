---
description: Ce document explique comment les données client sont gérées dans Audience Manager.
seo-description: Ce document explique comment les données client sont gérées dans Audience Manager.
seo-title: Gouvernance des données
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: Gouvernance des données
translation-type: tm+mt
source-git-commit: b47819d5e6394e78d744ada1bb7090d337938983

---


# Gouvernance des données

## Aperçu {#overview}

La gouvernance des données dans Audience Manager fait référence au cycle de vie des données de vos clients dans Audience Manager et englobe la [collecte et l’obscurcissement des adresses](data-governance.md#collecting-ip-addresses)IP, la rétention [des](data-governance.md#data-retention)données et les transferts [](data-governance.md#data-transfers)de données transfrontaliers.

## Collecte des adresses IP et obscurcissement des adresses IP {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**** Méthodologie d’obscurcissement d’IP : Conformément aux principes de "Confidentialité par conception", Adobe Audience Manager permet aux clients d’activer l’ [!DNL IP] obscurcissement à partir de l’interface utilisateur, que ce soit globalement dans toutes les régions géographiques ou pour des pays spécifiques. Lorsque vous activez ce paramètre, le dernier octet (dernière partie) de l’ [!DNL IP] adresse est immédiatement ignoré lorsque l’ [!DNL IP] adresse est assimilée à Audience Manager. Audience Manager ignore cette partie de l’ [!DNL IP] adresse avant le traitement (y compris avant toute recherche géographique ou journalisation facultative de l’ [!DNL IP] adresse). Par exemple :

* Avant que les valeurs de: `255.255.255.255`
* Après: `255.255.255.0`

>[!NOTE]
>
>Voir Obscurcissement d’adresse [IP](../../features/administration/ip-obfuscation.md) pour savoir comment activer l’obscurcissement d’ [!DNL IP] adresse dans l’interface utilisateur d’Audience Manager.

Regardez la vidéo ci-dessous pour comprendre le fonctionnement de l’obscurcissement des [!DNL IP] adresses dans Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/?captions=fre_fr)

**** Segmentation géographique : Si vous activez l’obscurcissement des [!DNL IP] adresses, les octets restants de l’ [!DNL IP] adresse peuvent toujours être utilisés pour la géosegmentation et la création de rapports dans Audience Manager. Si vous n’activez pas l’obscurcissement d’ [!DNL IP] adresse, Audience Manager utilise l’adresse [!DNL IP] complète. Vous pouvez utiliser la fonction de segmentation géographique qui vous permet d’identifier un [!DNL IP] [!DNL IP] emplacement par zone géographique dans les deux cas, mais avec une légère perte de précision lors de l’utilisation de l’obscurcissement. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. L'obtention d'informations au niveau de la région et du pays ne devrait être que légèrement affectée. Les données de segmentation géographique sont granulaires uniquement au niveau de la ville ou du code postal, et non au niveau individuel. En savoir plus sur le [ciblage](../../features/traits/trait-geotarget-keys.md) géographique et sur la configuration de caractéristiques avec des variables géographiques.

## Rétention des données dans Audience Manager {#data-retention}

L'application de politiques appropriées, sécurisées et opportunes de conservation des données à vos données est un élément important du respect des règles de confidentialité des données. Les clients d’Audience Manager peuvent définir des périodes de rétention personnalisées sur les caractéristiques et les segments en définissant le TTL (durée de vie) requis. Voir FAQ [sur la rétention des](../../faq/faq-privacy.md) données pour plus d’informations sur les périodes de rétention.

## Transferts de données transfrontaliers {#data-transfers}

Le RDPC n’interdit pas le transfert de données en dehors de l’Europe. Elle exige que les protections de la vie privée sur les données européennes persistent partout où les données sont transférées. Consultez le Centre [de confidentialité](https://www.adobe.com/privacy/eudatatransfers.html) Adobe pour en savoir plus. L'ACCP n'a pas de restrictions au transfert transfrontalier de données.
