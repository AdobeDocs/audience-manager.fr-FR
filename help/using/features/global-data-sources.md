---
description: Utilisez les sources de données globales pour importer des identifiants publicitaires d’appareils.
seo-description: Use Global Data Sources to import device advertising IDs.
seo-title: Global Data Sources
solution: Audience Manager
title: Sources de données globales
feature: Data Sources
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 77daa5bd6545914f65e3e0f19b12c750535244e8
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Sources de données globales {#global-data-sources}

## Présentation

Les sources de données globales sont accessibles à tous les clients d’Audience Manager et contiennent des identifiants publicitaires d’appareils générés par des fabricants d’appareils tels que [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku] et [!DNL Android] fabricants d’appareils. Ces identifiants sont mis à la disposition des constructeurs à des fins de publicité. Les clients Audience Manager peuvent utiliser des sources de données globales pour synchroniser les identifiants d’appareil et importer ou exporter des données masquées à partir de ces mappages.

Le tableau suivant décrit les sources de données globales prises en charge par Audience Manager.

| Data Source ID | Description |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** Les identifiants représentent les appareils qui exécutent le système d’exploitation [!DNL Android]. |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** Les identifiants représentent les appareils qui exécutent le système d’exploitation [!DNL iOS]. |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]** Les identifiants représentent [!DNL Roku] appareils de diffusion en continu. |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** Les identifiants représentent les périphériques exécutant le système d’exploitation [!DNL Windows 10]. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** Les identifiants représentent [!DNL Samsung] téléviseurs intelligents. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** représente les périphériques exécutant [!DNL Amazon Fire OS] |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]** représentent les périphériques exécutant le système d’exploitation [!DNL LG webOS]. |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]** représente les périphériques exécutant les systèmes d’exploitation Vizio smart TV. |

## Importation de données à partir de sources de données globales

Vous pouvez importer des identifiants d’appareil à partir de sources de données globales par le biais du [transfert de données en temps réel](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) et du [ transfert de données par lots](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Lors de l’envoi de données à l’Audience Manager à l’aide d’un identifiant d’appareil global, veillez à utiliser la source de données correspondante pour l’identifiant d’appareil en question. Exemple : pour importer des données pour [!DNL Apple IDFA], utilisez l’ID de source de données 20915.

## Limites

Sur les appareils exécutant les systèmes d’exploitation [!DNL iOS] et [!DNL Android], seules les applications natives peuvent récupérer et utiliser des identifiants publicitaires d’appareils ([!UICONTROL DAID]). Les applications web s’exécutant dans des navigateurs mobiles n’ont pas accès aux identifiants publicitaires d’appareils.

## Validation globale de l’ID de périphérique

Audience Manager valide les identifiants publicitaires d’appareils ([!UICONTROL DAID]) importés par les clients, en fonction de leur format, afin de s’assurer qu’ils correspondent au format standard défini par les fabricants d’appareils. Voir [Index des identifiants dans l’Audience Manager](../reference/ids-in-aam.md) pour obtenir un mappage détaillé des identifiants publicitaires d’appareils aux sources de données globales et le format approprié pour chaque identifiant. Veillez à importer les identifiants d’appareil dans le format approprié, en fonction du type d’appareil. L’Audience Manager rejette les identifiants d’appareil qui ne respectent pas le format approprié et renvoie un message d’erreur pour indiquer que l’identifiant a été rejeté.

* La messagerie d’erreur pour les transferts de données par lots est décrite ici : [Conditions et définitions des rapports d’état d’intégration](../reporting/onboarding-status-report.md#report-terms-conditions).
* La messagerie d’erreur pour les transferts de données en temps réel est décrite ici : [Codes d’erreur DCS, messages et exemples](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Stratégie d’expiration de l’identifiant de l’appareil

L’Audience Manager ignore automatiquement les identifiants publicitaires d’appareils après 120 jours d’inactivité, comme les [AAM UUID](../faq/faq-privacy.md).

## Demande de nouvelles sources de données globales

Pour demander l’ajout de nouvelles sources de données globales à Audience Manager, contactez Adobe Consulting ou l’Assistance clientèle d’Adobe et fournissez des informations détaillées sur les sources de données requises :

* Le nom de la plateforme demandée (par exemple, [!UICONTROL Apple IDFA]) ;
* Nom de la société/organisation qui gère la plateforme (par exemple, [!UICONTROL Apple Inc.]) ;
* Liens vers les spécifications techniques de l’espace de noms de l’identifiant publicitaire de l’appareil (par exemple, [Documentation du support AdSupport](https://developer.apple.com/documentation/adsupport)).
