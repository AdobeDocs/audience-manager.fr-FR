---
description: Reportez-vous à ce document pour obtenir la liste complète des ID d’Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Reportez-vous à ce document pour obtenir la liste complète des ID d’Adobe Audience Manager.
seo-title: Index des identifiants dans l’Audience Manager
solution: Audience Manager
title: Index des identifiants dans l’Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 3%

---


# Index des identifiants dans l’Audience Manager {#index-of-ids-in-audience-manager}

## Aperçu {#overview}

[!DNL Audience Manager] utilise plusieurs ID pour identifier et gérer les données que vous lui envoyez. Reportez-vous à cet article pour obtenir la liste complète des [!DNL Audience Manager] ID, ainsi que des exemples de préfixes que vous devez utiliser.

## Préfixe d’ID {#prefixing}

Bien que vous puissiez faire référence à la plupart de ces identifiants par leur nom autonome, la plupart d’entre eux sont destinés à être utilisés avec divers préfixes, lors de la transmission de données par le biais d’ [!DNL DCS] appels. Certains de ces identifiants sont utilisés par l’Audience Manager sans être exposés aux utilisateurs, tandis que d’autres sont également visibles dans l’interface utilisateur.

Pour comprendre les préfixes utilisés dans les exemples suivants, voir Attributs [pris en charge pour les appels](../api/dcs-intro/dcs-api-reference/dcs-keys.md)d’API DCS.

## Liste d’Audience Manager des identifiants {#id-list}

| ID | Nom et description | Utilisation et exemples | Emplacement de l’interface utilisateur |
|---|---|---|---|
| [!DNL AAM UUID] | ID utilisateur unique Adobe Audience Manager, également appelé [!UICONTROL Device ID]. Identifiant numérique à 38 chiffres associé [!DNL Audience Manager] à chaque périphérique avec lequel il interagit. Pensez à cet ID chaque fois que vous voyez une mention d’utilisateurs uniques dans l’ [!DNL Audience Manager] interface utilisateur. L’Audience Manager enregistre cet identifiant sous la forme d’un cookie dans le domaine `demdex.net` tiers. | Dans [!DNL DCS] les appels, `uuid` est précédé du `d_` préfixe. <br>Exemple : `d_uuid = 07955261652886032950143702505894272138` | Vous pouvez filtrer les caractéristiques en fonction [!UICONTROL Device ID] de la création de modèles [à l’](../features/algorithmic-models/create-model.md)apparence et de la [création de segments](../features/segments/segment-builder.md). Vous pouvez également filtrer les résultats en fonction [!UICONTROL Device ID] de l&#39;exécution des rapports [généraux pour les rapports Caractéristiques](../reporting/general-reports.md) et [Tendance pour les rapports Caractéristiques](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | ID d’organisation. Il s’agit de l’identifiant fourni par une société lors de la connexion à un [!DNL Experience Cloud] compte. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Invisible dans l’interface utilisateur de l’Audience Manager. Pour savoir comment trouver votre société, consultez la section [!DNL Organization ID]Rechercher votre ID [](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)d’organisation. |
| [!DNL PID] | ID de partenaire. Il [!DNL PID] s’agit d’un identifiant de société dans [!DNL Audience Manager]. L’Audience Manager associe un [!DNL imsOrgId] à un [!DNL PID]. | `1352` | Invisible dans l’interface utilisateur de l’Audience Manager. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. L’ [!DNL Experience Cloud] ID ([!DNL ECID]abréviations héritées [!DNL MID] ou [!DNL MCID]) est dérivé mathématiquement de l’ID d’organisation et du [!DNL Audience Manager][!UICONTROL Unique User ID]. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and [!DNL Audience Manager] [!DNL UUID] you get the same [!DNL ECID] value every time. Vous pouvez en savoir plus sur les [!DNL ECID] cookies dans la documentation des [cookies et des identifiants](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) d’Experience Cloud. | `mid = 08382830887934830189014177072406221371` | Invisible dans le [!DNL Audience Manager][!DNL UI]. |
| [!DNL SID] | [!UICONTROL Trait ID]. L&#39; [!UICONTROL Trait ID] identifiant identifie de manière unique les caractéristiques de l&#39; [!DNL Audience Manager] environnement. | Dans [!DNL DCS] les appels, `SID` est précédé du `d_` préfixe. <br>Exemple `d_sid=289983`. | Un [!UICONTROL Trait ID] est affecté à chaque caractéristique et visible dans l’interface utilisateur, dans la page [Caractéristiques](../features/traits/trait-details-page.md) . |
| [!DNL SID] | [!UICONTROL Segment ID]. L’ [!UICONTROL Segment ID] identifiant identifie de manière unique les segments dans l’ [!DNL Audience Manager] environnement. | Dans [!DNL DCS] les appels, `SID` est précédé du `d_` préfixe. <br>Exemple `d_sid=4798574`. | Un segment [!UICONTROL Segment ID] est affecté à chaque segment et visible dans l’interface utilisateur, dans la page [Segments](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Cet identifiant identifie de manière unique les segments de l’ [!DNL Audience Manager] environnement. | `741232` | Un segment [!UICONTROL Legacy Segment ID] est affecté à chaque segment et visible dans l’interface utilisateur, dans la page [Segments](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | [!UICONTROL Destination ID]. L’ [!UICONTROL Destination ID] identifiant identifie de manière unique les destinations dans l’ [!DNL Audience Manager] environnement. Un ID est affecté à chaque destination dans l’interface utilisateur. | `2523` | Un [!UICONTROL Destination ID] est affecté à chaque destination et visible dans l’interface utilisateur, dans la page [Destinations](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | [!UICONTROL Data Source ID] (également appelée [!UICONTROL Data Provider ID]). Il [!UICONTROL Data Source ID] s’agit d’un espace de nommage pour les identifiants ou les caractéristiques. Un identifiant est affecté à chaque source de données (fournisseur de données) dans l’interface utilisateur. | Dans [!DNL DCS] les appels, `dpid` est précédé du `d_` préfixe. <br>Exemple: `d_dpid=39217`. | Un [!UICONTROL Data Provider ID] est affecté à chaque source de données et visible dans l’interface utilisateur, dans la page Sources [de](../features/datasources-list-and-settings.md) données. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], également appelée [!DNL CRM ID] ou [!UICONTROL Cross-Device ID]. Identifiant tiers. Il s’agit de l’identifiant par lequel vous identifiez les utilisateurs finaux dans votre propre [!DNL CRM] système. Vous pouvez effectuer une synchronisation [!DNL DPUUIDs] avec [!DNL Audience Manager] [!DNL UUIDs] et vous pouvez la synchroniser [!DNL DPUUIDs] à partir de vos différents [!UICONTROL Data Sources] ([!DNL DPIDs]) éléments dans le processus de synchronisation des identifiants. | Dans [!DNL DCS] les appels, `dpuuid` est précédé du `d_` préfixe. <br> Exemple `d_dpuuid=2132-3423vn-343fds-3432r`. | Vous pouvez filtrer les caractéristiques en fonction [!UICONTROL Cross-Device ID] de la création de modèles [à l’](../features/algorithmic-models/create-model.md)apparence et de la [création de segments](../features/segments/segment-builder.md). Vous pouvez également filtrer les résultats en fonction [!UICONTROL Cross-Device ID] de l&#39;exécution des rapports [généraux pour les rapports Caractéristiques](../reporting/general-reports.md) et [Tendance pour les rapports Caractéristiques](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Voir `DPUUID`. | Voir `DPUUID`. | Voir `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. Les paires [!DNL CID] et [!DNL CID_IC] clé-valeur remplacent [!DNL DPID] et [!DNL DPUUID]. Ils offrent les mêmes fonctions que le [!DNL DPID] et [!DNL DPUUID], mais sont plus efficaces car ils incluent l’ID de fournisseur de données et l’ID d’utilisateur (ou le code d’intégration) dans une seule paire clé-valeur. | Dans [!DNL DCS] les appels, ces identifiants sont précédés du `d_` préfixe. <br>Exemple: `d_cid_ic=39217_myIntegrationCode`. | Voir `DPID` et `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Cet identifiant propre à chaque périphérique est utilisé à des fins de publicité. Généralement fourni par le fabricant du système d’exploitation du périphérique ou du périphérique. | Voir ID [](#global-device-ids)de dispositif global. |  |

## ID de périphérique global {#global-device-ids}

Les identifiants de périphérique globaux sont des identifiants publicitaires de périphérique, propres à chaque périphérique, fournis par le fabricant du périphérique ou le système d’exploitation. Le tableau ci-dessous décrit ces identifiants et leur format. Pour plus d’informations sur les ID de périphérique globaux et sur leur utilisation dans [!DNL Audience Manager], consultez la section Sources [de données](/help/using/features/global-data-sources.md)globales.

| ID | ID de source de données globale | Nom et description | Exemple |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Les identifiants sont des identifiants de périphérique mobile fournis par le fabricant du périphérique. Ces identifiants représentent les périphériques qui exécutent le système d’exploitation iOS. | Le format est strictement composé de 32 chiffres hexadécimaux majuscules, affichés en cinq groupes et séparés par des tirets, sous la forme 8-4-4-4-12, pour un total de 36 caractères.<br> Exemple: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s sont des identifiants de périphériques mobiles fournis par les fabricants de périphériques Android. Ces identifiants représentent les périphériques qui exécutent le système d’ [!DNL Android] exploitation. | Le format est strictement composé de 32 chiffres hexadécimaux minuscules, affichés en cinq groupes et séparés par des tirets, sous la forme 8-4-4-4-12, pour un total de 36 caractères. <br>Exemple: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] représentent les périphériques [!DNL Roku] de diffusion en continu. | Le format est strictement composé de 32 chiffres hexadécimaux minuscules, affichés en cinq groupes et séparés par des tirets, sous la forme 8-4-4-4-12, pour un total de 36 caractères. <br>Exemple: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sont des identifiants de périphérique générés par [!DNL Windows 10] chaque périphérique, par utilisateur. | [!DNL MAID]s sont formatées sous la forme de chaînes alphanumériques. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s sont des identifiants de périphérique fournis par les [!DNL Samsung] Smart TV. | [!DNL Samsung] [!DNL DUID]s sont formatées sous la forme de chaînes alphanumériques. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identifiants de périphérique représentant les périphériques exécutant le système d’ [!DNL Fire OS] exploitation. | Le format est strictement composé de 32 chiffres hexadécimaux minuscules, affichés en cinq groupes et séparés par des tirets, sous la forme 8-4-4-4-12, pour un total de 36 caractères. <br>Exemple : `df07c7dc-cea7-4a89-b328-810ff5acb15d` |

