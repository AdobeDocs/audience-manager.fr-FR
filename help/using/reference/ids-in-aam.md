---
description: Consultez ce document pour obtenir la liste complète des ID Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Consultez ce document pour obtenir la liste complète des ID Adobe Audience Manager.
seo-title: Index des ID dans Audience Manager
solution: Audience Manager
title: Index des ID dans Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: f8916812a31513d3d8401a0598f37dae02a3fd02

---


# Index des ID dans Audience Manager{#index-of-ids-in-audience-manager}

## Aperçu {#overview}

Audience Manager utilise plusieurs ID pour identifier et gérer les données que vous lui envoyez. Reportez-vous à cet article pour obtenir la liste complète des ID Adobe Audience Manager, ainsi que des exemples des préfixes que vous devez utiliser.

## Préfixe d’ID {#prefixing}

Bien que vous puissiez faire référence à la plupart de ces identifiants par leur nom autonome, la plupart d’entre eux sont destinés à être utilisés avec divers préfixes lors de la transmission de données par le biais d’appels DCS. Certains de ces identifiants sont utilisés par Audience Manager sans être exposés aux utilisateurs, tandis que d’autres sont également visibles dans l’interface utilisateur.

Pour comprendre les préfixes utilisés dans les exemples suivants, voir Attributs [pris en charge pour les appels](../api/dcs-intro/dcs-api-reference/dcs-keys.md)d’API DCS.

## Liste des identifiants d’Audience Manager {#id-list}

| ID | Nom et description | Utilisation et exemples | Emplacement de l’interface utilisateur |
|---|---|---|---|
| [!DNL AAM UUID] | ID utilisateur unique d’Audience Manager. ID numérique de périphérique à 38 chiffres associé par Audience Manager à chaque périphérique avec lequel il interagit. Pensez à cet identifiant chaque fois que vous voyez une mention d’utilisateurs uniques dans l’interface utilisateur d’Audience Manager. Audience Manager enregistre cet identifiant sous forme de cookie dans le domaine `demdex.net` tiers. | Dans [!DNL DCS] les appels, `uuid` est précédé du `d_` préfixe. <br>Exemple : `d_uuid = 07955261652886032950143702505894272138` | Invisible dans l’interface utilisateur d’Audience Manager. |
| [!DNL ImsOrgId] | ID d’organisation. Il s’agit de l’identifiant fourni à une entreprise lors de sa connexion à un compte Experience Cloud. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Invisible dans l’interface utilisateur d’Audience Manager. Pour savoir comment trouver l’ID d’organisation de votre entreprise, consultez [Rechercher votre ID](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255)d’organisation. |
| PID | ID de partenaire. Le PID est l’identifiant d’une société dans Audience Manager. Audience Manager associe un [!DNL imsOrgId] à un [!DNL PID]. | `1352` | Invisible dans l’interface utilisateur d’Audience Manager. |
| [!DNL ECID], [!DNL MID] | Experience Cloud ID. L’ID Experience Cloud ([!DNL ECID], abréviations héritées [!DNL MID] ou [!DNL MCID]) est dérivé mathématiquement de votre ID d’organisation et de l’ID utilisateur unique d’Audience Manager. As long as these IDs remain constant, generating the right [!DNL ECID] for a specific user is simply a math problem. With the same organization ID and Audience Manager [!DNL UUID] you get the same [!DNL ECID] value every time. Vous pouvez en savoir plus sur l’ECID dans la documentation [Cookies et Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | Invisible dans l’interface utilisateur d’Audience Manager. |
| [!DNL SID] | ID de caractéristique. L’ID de caractéristique identifie de manière unique les caractéristiques de l’environnement Audience Manager. | Dans [!DNL DCS] les appels, `SID` est précédé du `d_` préfixe. <br>Exemple `d_sid=289983`. | Un ID de caractéristique est affecté à chaque caractéristique et visible dans l’interface utilisateur, dans la page [Caractéristiques](../features/traits/trait-details-page.md) . |
| [!DNL SID] | ID de segment. L’ID de segment identifie de manière unique les segments dans l’environnement Audience Manager. | Dans [!DNL DCS] les appels, `SID` est précédé du `d_` préfixe. <br>Exemple `d_sid=4798574`. | Un ID de segment est affecté à chaque segment et visible dans l’interface utilisateur de la page [Segments](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | Identifiant de segment hérité. Cet identifiant identifie de manière unique les segments dans l’environnement Audience Manager. | `741232` | Un ID de segment hérité est affecté à chaque segment et visible dans l’interface utilisateur, dans la page [Segments](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | ID de destination. L’ID de destination identifie de manière unique les destinations dans l’environnement Audience Manager. Un ID est affecté à chaque destination dans l’interface utilisateur. | `2523` | Un ID de destination est affecté à chaque destination et visible dans l’interface utilisateur, dans la page [Destinations](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | ID de source de données (également appelé ID de fournisseur de données). L’ID de source de données est un espace de noms pour les ID ou les caractéristiques. Un ID est affecté à chaque source de données (fournisseur de données) dans l’interface utilisateur. | Dans [!DNL DCS] les appels, `dpid` est précédé du `d_` préfixe. <br>Exemple: `d_dpid=39217`. | Un ID de fournisseur de données est affecté à chaque source de données et visible dans l’interface utilisateur, dans la page Sources [de](../features/datasources-list-and-settings.md) données. |
| [!DNL DPUUID] | ID utilisateur unique du fournisseur de données (également appelé [!DNL CRM ID]). Identifiant tiers. Il s’agit de l’identifiant par lequel vous identifiez les utilisateurs finaux dans votre propre [!DNL CRM] système. Vous pouvez synchroniser [!DNL DPUUIDs] Audience Manager [!DNL UUIDs] et vous pouvez synchroniser [!DNL DPUUIDs] à partir de vos différentes sources de données ([!DNL DPIDs]) dans le processus de synchronisation des identifiants. | Dans les appels DCS, `dpuuid` est précédé du `d_` préfixe. <br> Exemple `d_dpuuid=2132-3423vn-343fds-3432r`. | Invisible dans l’interface utilisateur d’Audience Manager. |
| [!DNL CRM ID] | Voir `DPUUID`. | Voir `DPUUID`. | Voir `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | ID client, code d’intégration d’ID client. Les paires [!DNL CID] et [!DNL CID_IC] clé-valeur remplacent [!DNL DPID] et [!DNL DPUUID]. Ils fournissent les mêmes fonctions que le [!DNL DPID] et [!DNL DPUUID], mais sont plus efficaces car ils incluent l’ID du fournisseur de données et l’ID utilisateur (ou le code d’intégration) dans une seule paire clé-valeur. | Dans les appels DCS, ces identifiants sont précédés du `d_` préfixe. <br>Exemple: `d_cid_ic=39217_myIntegrationCode`. | Voir `DPID` et `DPUUID`. |
| [!DNL DAID] | ID de publicité du périphérique. Cet identifiant propre à chaque périphérique est utilisé à des fins de publicité. Généralement fourni par le fabricant du système d’exploitation du périphérique ou du périphérique. | Voir ID de périphérique [global](#global-device-ids). |  |

## ID de périphérique global {#global-device-ids}

Les identifiants de périphérique globaux sont des identifiants publicitaires de périphérique, propres à chaque périphérique, fournis par le fabricant du périphérique ou le système d’exploitation. Le tableau ci-dessous décrit ces identifiants et leur format. Pour plus d’informations sur les ID de périphérique globaux et leur utilisation dans Audience Manager, consultez Sources [de données](/help/using/features/global-data-sources.md)globales.

| ID | ID de source de données globale | Nom et description | Exemple |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Les identifiants sont des identifiants de périphérique mobile fournis par le fabricant du périphérique. Ces identifiants représentent les périphériques qui exécutent le système d’exploitation iOS. | Le format est strictement composé de 32 chiffres hexadécimaux majuscules, affichés en cinq groupes et séparés par des tirets, au format 8-4-4-4-12, pour un total de 36 caractères.<br> Exemple: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s sont des identifiants de périphériques mobiles fournis par les fabricants de périphériques Android. Ces identifiants représentent les périphériques qui exécutent le système d’ [!DNL Android] exploitation. | Le format est strictement composé de 32 chiffres hexadécimaux minuscules, affichés en cinq groupes et séparés par des tirets, au format 8-4-4-4-12, pour un total de 36 caractères. <br>Exemple: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] représentent les périphériques [!DNL Roku] de diffusion en continu. | Le format est strictement composé de 32 chiffres hexadécimaux minuscules, affichés en cinq groupes et séparés par des tirets, au format 8-4-4-4-12, pour un total de 36 caractères. <br>Exemple: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s sont des identifiants de périphérique générés par [!DNL Windows 10] chaque périphérique, par utilisateur. | [!DNL MAID]s sont formatées sous la forme de chaînes alphanumériques. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s sont des identifiants de périphériques fournis par les téléviseurs Samsung Smart. | Les [!DNL DUID]Samsung sont formatés sous la forme de chaînes alphanumériques. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Identifiants de périphérique représentant les périphériques exécutant le système [!DNL Fire OS] d’exploitation. | Le format est strictement composé de 32 chiffres hexadécimaux minuscules, affichés en cinq groupes et séparés par des tirets, au format 8-4-4-4-12, pour un total de 36 caractères. <br>Exemple : `df07c7dc-cea7-4a89-b328-810ff5acb15d` |

