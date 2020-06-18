---
description: Ce document explique comment les données du client sont gérées dans l’Audience Manager.
seo-description: Ce document explique comment les données du client sont gérées en Audience Manager.
seo-title: Gouvernance des données
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: Gouvernance des données
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 1%

---


# Gouvernance des données

## Aperçu {#overview}

La gouvernance des données en Audience Manager fait référence au cycle de vie des données de vos clients en Audience Manager et englobe la [collecte et l’obscurcissement des adresses](data-governance.md#collecting-ip-addresses)IP, la rétention [des](data-governance.md#data-retention)données et les transferts [de données](data-governance.md#data-transfers)transfrontaliers.

## Collecte des adresses IP et obscurcissement des adresses IP {#collecting-ip-addresses}

The [!DNL IP] address of a visitor to a customer’s website is transmitted to an Adobe [!DNL Data Processing Center] ([!DNL DPC]) where the [!DNL IP] address may be stored. Depending on the network configuration for the visitor, the [!DNL IP] address may not necessarily represent the [!DNL IP] address of the visitor’s computer. For example, the [!DNL IP] address could be the external [!DNL IP] address of a Network Address Translation (NAT) firewall, [!DNL HTTP] proxy, or Internet gateway.

**Méthodologie d’obscurcissement d’IP :** Suivant les principes de &quot;Confidentialité par conception&quot;, l&#39;Adobe Audience Manager permet aux clients d&#39;activer l&#39; [!DNL IP] obscurcissement depuis l&#39;interface utilisateur, soit dans l&#39;ensemble des régions géographiques, soit pour des pays spécifiques. Lorsque vous activez ce paramètre, le dernier octet (dernière partie) de l’ [!DNL IP] adresse est immédiatement ignoré lorsque l’ [!DNL IP] adresse est assimilée à une Audience Manager. L&#39;Audience Manager ignore cette partie de l&#39; [!DNL IP] adresse avant le traitement (y compris avant toute recherche géographique ou consignation facultative de l&#39; [!DNL IP] adresse). Par exemple :

* Avant que les valeurs de: `255.255.255.255`
* Après: `255.255.255.0`

>[!NOTE]
>
>Voir Obscurcissement [d’adresse](../../features/administration/ip-obfuscation.md) IP pour savoir comment activer l’obscurcissement d’ [!DNL IP] adresse dans l’interface utilisateur de l’Audience Manager.

Regardez la vidéo ci-dessous pour comprendre comment l&#39;obscurcissement des [!DNL IP] adresses fonctionne en Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Segmentation géographique :** Si vous activez l’obscurcissement des [!DNL IP] adresses, les valeurs restantes de l’ [!DNL IP] adresse peuvent toujours être utilisées pour la géosegmentation et le rapports en Audience Manager. Si vous n’activez pas l’obscurcissement [!DNL IP] d’adresse, l’Audience Manager utilise l’adresse complète [!DNL IP] . Vous pouvez utiliser la fonction de segmentation géographique qui vous permet d&#39;identifier un [!DNL IP] emplacement par zone géographique dans les deux cas, mais avec une légère perte de précision en cas d&#39; [!DNL IP] obscurcissement. Obtaining city-level information will likely be significantly impacted by the obfuscation of the [!DNL IP] address. L&#39;obtention d&#39;informations au niveau des régions et des pays ne devrait être que légèrement entravée. Les données de segmentation géographique sont granulaires uniquement au niveau de la ville ou du code postal, et non au niveau individuel. En savoir plus sur le [ciblage](../../features/traits/trait-geotarget-keys.md) géographique et sur la manière de configurer des caractéristiques avec des variables géographiques.

## Conservation des données dans l&#39;Audience Manager {#data-retention}

L&#39;application de politiques appropriées, sécurisées et opportunes de rétention des données à vos données est un élément important du respect des règles de confidentialité des données. Audience Manager Les clients peuvent définir des périodes de rétention personnalisées sur les caractéristiques et les segments en définissant la durée de vie requise (TTL). Voir FAQ [sur la rétention des](../../faq/faq-privacy.md) données pour en savoir plus sur les périodes de rétention.

## Transferts de données transfrontaliers {#data-transfers}

Lorsque l&#39;Audience Manager transfère des données à caractère personnel des clients par-delà les frontières nationales, l&#39;Audience Manager le fait conformément à la législation en vigueur. Visitez le Centre [](https://www.adobe.com/privacy/eudatatransfers.html) de Confidentialité d&#39;Adobe pour en savoir plus.