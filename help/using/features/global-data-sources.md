---
description: Utilisez les sources de données globales pour importer des identifiants publicitaires d’appareils.
seo-description: Utilisez les sources de données globales pour importer des identifiants publicitaires d’appareils.
seo-title: Sources de données globales
solution: Audience Manager
title: Sources de données globales
feature: Sources de données
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 6%

---

# Sources de données globales {#global-data-sources}

## Présentation

Les sources de données globales sont accessibles à tous les clients d’Audience Manager et contiennent des identifiants publicitaires d’appareils générés par des fabricants tels que [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] et [!DNL Android] fabricants d’appareils. Ces identifiants sont mis à la disposition des constructeurs à des fins de publicité. Les clients Audience Manager peuvent utiliser des sources de données globales pour synchroniser les identifiants d’appareil et importer ou exporter des données masquées à partir de ces mappages.

Le tableau suivant décrit les sources de données globales prises en charge par Audience Manager.

| Identifiant de source de données | Description |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** -  **[!DNL GAID]** Les identifiants représentent les appareils qui exécutent le système d’ [!DNL Android] exploitation. |
| 20915 | **[!DNL Apple ID For Advertising]** -  **[!DNL IDFA]** Les identifiants représentent les appareils qui exécutent le système d’ [!DNL iOS] exploitation. |
| 121963 | **[!DNL Roku ID for Advertising]** -  **[!DNL RIDA]** Les identifiants représentent les appareils  [!DNL Roku] en flux continu. |
| 389146 | **[!DNL Microsoft Advertising ID]** -  **[!DNL MAID]** Les identifiants représentent les périphériques exécutant le système  [!DNL Windows 10] d’exploitation. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** -  **[!DNL TIFA]** Les identifiants représentent les téléviseurs  [!DNL Samsung] intelligents. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** représente les périphériques en cours d’exécution  [!DNL Amazon Fire OS] |

## Importation de données à partir de sources de données globales

Vous pouvez importer des identifiants d’appareil à partir de sources de données globales par le biais d’un [transfert de données en temps réel](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) et d’un [transfert de données par lots](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Lors de l’envoi de données à l’Audience Manager à l’aide d’un identifiant d’appareil global, veillez à utiliser la source de données correspondante pour l’identifiant d’appareil en question. Exemple : pour importer des données pour [!DNL Apple IDFA], utilisez l’ID de source de données 20915.

## Limites

Sur les appareils exécutant les systèmes d’exploitation [!DNL iOS] et [!DNL Android], seules les applications natives peuvent récupérer et utiliser les identifiants publicitaires d’appareils ([!UICONTROL DAID]s). Les applications web s’exécutant dans des navigateurs mobiles n’ont pas accès aux identifiants publicitaires d’appareils.

## Validation globale de l’ID de périphérique

Audience Manager valide les identifiants publicitaires d’appareils ([!UICONTROL DAID]) importés par les clients, en fonction de leur format, afin de s’assurer qu’ils correspondent au format standard défini par les fabricants d’appareils. Voir [Index des ID en Audience Manager](../reference/ids-in-aam.md) pour obtenir un mappage détaillé des ID publicitaires d’appareils aux sources de données globales et le format approprié pour chaque ID. Veillez à importer les identifiants d’appareil dans le format approprié, en fonction du type d’appareil. L’Audience Manager rejette les identifiants d’appareil qui ne respectent pas le format approprié et renvoie un message d’erreur pour indiquer que l’identifiant a été rejeté.

* Les messages d’erreur relatifs aux transferts de données par lots sont décrits ici : [Termes et définitions des rapports d’état de l’intégration](../reporting/onboarding-status-report.md#report-terms-conditions).
* La messagerie d’erreur pour les transferts de données en temps réel est décrite ici : [Codes d’erreur DCS, messages et exemples](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Stratégie d’expiration de l’identifiant de l’appareil

L’Audience Manager ignore automatiquement les identifiants publicitaires d’appareils après 120 jours d’inactivité, comme les [UUID AAM](../faq/faq-privacy.md)s.

## Demande de nouvelles sources de données globales

Pour demander l’ajout de nouvelles sources de données globales à Audience Manager, contactez Adobe Consulting ou l’Assistance clientèle d’Adobe et fournissez des informations détaillées sur les sources de données requises :

* Le nom de la plateforme demandée (par exemple, [!UICONTROL Apple IDFA]) ;
* Nom de la société/organisation qui gère la plateforme (par exemple, [!UICONTROL Apple Inc.]) ;
* Liens vers les spécifications techniques de l’espace de noms de l’identifiant publicitaire de l’appareil (par exemple, [Documentation AdSupport](https://developer.apple.com/documentation/adsupport)).
