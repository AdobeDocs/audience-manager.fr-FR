---
description: Ce document couvre les aspects techniques associés à la conformité des réglementations en matière de confidentialité des données pour Audience Manager.
seo-description: Ce document couvre les aspects techniques associés à la conformité des réglementations en matière de confidentialité des données pour Audience Manager.
seo-title: Requêtes de confidentialité des données
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Requêtes de confidentialité des données
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 62%

---


# Requêtes de confidentialité des données {#data-privacy-requests}

## Présentation {#overview}

This document provides an overview of managing individual data privacy and opt-out requests that you can send to [!DNL Audience Manager] through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send consumer data privacy requests made under [!DNL GDPR] and [!DNL CCPA].

Avant de lire cet article, nous vous recommandons de parcourir le [glossaire du RGPD](../data-security-and-privacy/aam-gdpr-glossary.md) et le [glossaire de la CCPA](aam-ccpa-glossary.md), afin de mieux comprendre la terminologie utilisée dans le présent document.

You can submit individual requests to access and delete consumer data from [!DNL Audience Manager], in two ways:

* Depuis l’[interface utilisateur de Privacy Service](https://privacyui.cloud.adobe.io/). Consultez la documentation [ici](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Depuis le **[!DNL Privacy Service API]**. See the documentation [here](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) and the [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending individual data privacy requests, you can submit any [!DNL Audience Manager] identifiers (IDs), as described in the **[Audience Manager Identifiers](data-privacy-ids.md)**section, along with their respective namespace IDs (data source IDs).

[Privacy Service](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html) prend en charge deux types de demandes : les demandes d’accès aux données et de suppression de données.

## Demandes d’accès aux données {#access-data}

Vous pouvez envoyer des demandes d’accès aux données individuelles depuis l’[interface utilisateur de Privacy Service](https://privacyui.cloud.adobe.io/) (documentation [ici](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) ou en appelant le [!DNL Privacy Service API] (documentation [ici](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html) et référence [!DNL API] [ici ](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

L’[interface utilisateur de Privacy Service](https://privacyui.cloud.adobe.io/) vous permet de créer de nouvelles requêtes de tâche, soit en utilisant le [!UICONTROL Request Builder] soit en chargeant un fichier [!DNL JSON].

Pour voir à quoi un fichier [!DNL JSON] valide ressemble, vous pouvez [ télécharger un exemple JSON](../data-security-and-privacy/assets/access_request.json).

Nous comprenons votre implication dans le respect des demandes de confidentialité des données pendant la période définie par la loi.

## Demandes de suppression de données {#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) (documentation [here](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the [!DNL Privacy Service API] (documentation [here](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

L’[interface utilisateur de Privacy Service](https://privacyui.cloud.adobe.io/) vous permet de créer de nouvelles requêtes de tâche, soit en utilisant le [!UICONTROL Request Builder] soit en chargeant un fichier [!DNL JSON].

Pour voir à quoi un fichier [!DNL JSON] valide ressemble, vous pouvez [ télécharger un exemple JSON](../data-security-and-privacy/assets/access_request.json).

Adobe comprend votre implication dans le respect des demandes de confidentialité des données des clients dans les 30 jours. For that reason, [!DNL Adobe] is committed to processing your data deletion request as soon as possible.

In response to your consumer data deletion requests, [!DNL Audience Manager] deletes traits and segments associated with the [!DNL Audience Manager] identifier included in the request. Additionally, the respective [!DNL Audience Manager] identifiers for the individual opted out of further data collection by [!DNL Audience Manager] and the respective ID mappings will be removed.

Lorsque vous envoyez des identifiants déclarés, comme des identifiants [!DNL CRM] multiterminaux ou des identifiants de , dans des demandes de confidentialité des données,  réalisera la suppression nécessaire sur tous les appareils associés (jusqu’à 100 appareils par identifiant déclaré).[!DNL cookie][!DNL Audience Manager]

[!DNL Audience Manager] essaiera de notifier les partenaires d’activation concernant les requêtes de suppression en leur envoyant des informations non segmentées pour les titulaires de données demandant la suppression de certaines données. En revanche, certains partenaires d’activation :

1. Cannot support unsegment (or remove segment) requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] with a frequency of less than 30 days. In those cases, [!DNL Audience Manager] customers are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

In those cases, you are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

Download our [Partner Excel sheet](assets/AAM-Partners-October2019.xlsx) to see which [!DNL Audience Manager] activation partners support unsegment.

## Demandes d’exclusion {#opt-out-requests}

[!DNL Audience Manager] soutient les normes à l&#39;échelle de l&#39;industrie en ce qui concerne la gestion des exclusions. Lisez la suite pour obtenir des informations complètes sur les types d’exclusion pris en charge par [!DNL Audience Manager].

While data access and deletion requests are handled through the [Privacy Service](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html), opt-out requests are currently supported through the [!DNL DCS API]. Read on to learn what the opt-out [!DNL API] calls should look like.

### Demandes d’exclusion globales

The global opt-out represents an opt-out across [!DNL Audience Manager] and other [!DNL Adobe Experience Cloud] solutions for all brands. Le tableau ci-dessous reprend les méthodes utilisées pour les exclusions globales :

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusion pour </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>La page <a href="https://www.adobe.com/fr/privacy/opt-out.html#customeruse" format="http" scope="external"> Vos choix en matière de confidentialité </a> propose des fonctionnalités en un clic qui permettent aux utilisateurs finaux de contrôler et d’exclure la collecte de données par les solutions publicitaires Adobe Experience Cloud (y compris Audience Manager). À ce titre, vous pouvez vous reporter à la <a href="https://www.adobe.com/fr/privacy/opt-out.html#customeruse" format="http" scope="external"> section client professionnel </a> de la page Vos choix en matière de confidentialité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Appels API directs vers Audience Manager </p> </td> 
   <td colname="col2"> <p>Vos utilisateurs peuvent se désabonner de la collecte des données de toutes les marques Audience Manager en effectuant un appel vers l’API DCS ci-dessous et en incluant l’<a href="../../reference/ids-in-aam.md">identifiant utilisateur Audience Manager </a> : </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Par conséquent, nous définirons les cookies <code>demdex=NOTARGET</code> et <code>dextp=NOTARGET</code> pour l’identifiant utilisateur Audience Manager soumis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Appareils mobiles </p> </td> 
   <td colname="col2"> <p>Reportez-vous aux paramètres d’exclusion et de confidentialité pour : </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/fr-FR/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Appareils Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/fr-FR/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> Appareils iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Vos utilisateurs peuvent également se désinscrire de la collecte de données globale en se rendant sur les sites web de nos partenaires en normes de l’industrie.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/) ;
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Suite aux demandes d’exclusion décrites ci-dessus :

* [!DNL Audience Manager] cessera la collecte, la segmentation ou l’activation de toutes les données, à condition que l’utilisateur n’efface pas les cookies de son navigateur.
* Les données historiques sont retirées du profil utilisateur au bout de 120 jours.

### Exclusion au niveau du partenaire par le biais d’appels d’identifiants déclarés

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. You can send partner-level opt-out requests for cross-device IDs, including [!DNL CRM] IDs and hashed email addresses.

Suite à une exclusion au niveau du partenaire avec un appel d’identifiant déclaré :

* L’[identifiant CRM](../../reference/ids-in-aam.md) est exclu de la collecte de données.
* Le dernier identifiant d’appareil ([l’identifiant utilisateur unique Audience Manager](../../reference/ids-in-aam.md)) associé à l’[identifiant CRM](../../reference/ids-in-aam.md) est exclu de la collecte de données.
* [!DNL Audience Manager] cessera toute collecte de données, segmentation ou activation à venir pour l’identifiant et le dernier identifiant d’appareil associé à l’identifiant .[!DNL CRM][!DNL CRM]
* [!DNL Audience Manager] dissocie l’identifiant [!DNL CRM] d’exclusion et le dernier ID de périphérique de tous les segments ;
* [!UICONTROL Destination]Les partenaires de reçoivent la requête de suppression de la segmentation pour l’identifiant et le dernier identifiant de l’appareil. [!DNL CRM] La suppression de la segmentation fonctionne pour les destinations en [temps réel](data-privacy-requests.md#aam-partners-with-unsegmentation) et par lots.
* Aucune donnée historique n’est supprimée.

When [!DNL Audience Manager] receives a partner-level opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the [!DNL Audience Manager] user ID.

Vous pouvez faire une demande d’exclusion d’identifiant déclaré avec les paires clé-valeur `d_cid` et `d_cid_ic`. Les paramètres hérités comme `d_dpid` et `d_dpuuid` fonctionnent toujours, mais sont considérés comme obsolètes. Voir [CID remplace DPID et DPUUID](../../reference/cid.md). Dans les exemples, le texte en *italique* indique un espace réservé de variable.

#### Exclusion avec [!DNL CID] et [!DNL CID_IC]

Pour obtenir une description et une syntaxe, consultez les [variables et la syntaxe d’URL pour les identifiants déclarés](../../features/declared-ids.md#variables-and-syntax).

| Exclusion à l’aide | Exemple de code |
|--- |--- |
| d’un identifiant de fournisseur de données et d’un identifiant utilisateur. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| d’un code d’intégration et d’un identifiant utilisateur. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Plusieurs paires `d_cid` et `d_cid_ic` clé-valeur. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Exclusion au niveau du partenaire avec des appels d’identifiants d’appareil

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. Vous pouvez exclure de la collecte de données un identifiant d’appareil donné pour une marque en effectuant les appels suivants sur l’[API DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) :

| Exclusion à l’aide | Exemple de code |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Découvrez-en plus sur `uuid`, `mid` et `imsOrgId` dans l’[index des identifiants dans Audience Manager](/help/using/reference/ids-in-aam.md).

Suite à une exclusion au niveau du partenaire avec un appel d’identifiant d’appareil :

* L’identifiant d’appareil est exclu de la collecte de données.
* [!DNL Audience Manager] cessera toute collecte de données, segmentation ou activation pour le partenaire à venir par l’identifiant d’appareil.
* [!DNL Audience Manager] dissocie l’ID de périphérique de tous les segments ;
* Les partenaires de destination reçoivent la requête de suppression de la segmentation de l’identifiant de l’appareil. La suppression de la segmentation fonctionne pour les destinations en [temps réel](data-privacy-requests.md#aam-partners-with-unsegmentation) et par lots.
* Aucune donnée historique n’est supprimée.

## [!DNL Audience Manager] Partenaires Disposant De Capacités De Désegmentation {#aam-partners-with-unsegmentation}

In order to help you automate your consumer data privacy requests, [!DNL Audience Manager] will attempt to notify activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

Cependant, certains de nos partenaires d’activation :

1. Cannot support unsegment requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] more frequently than once in 30 days.

In those cases, you are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

Consult the [list of device-based destinations](/help/using/features/destinations/device-based-destinations-list.md) to see which [!DNL Audience Manager] activation partners support unsegment.

## Demandes de correction de données {#correction}

Given that [!DNL Audience Manager] is not the source of the data, there is a limited role for data correction in [!DNL Audience Manager]. The correction could mean that the consumer has requested to either be disqualified from an incorrect [!UICONTROL trait]/[!UICONTROL segment] or qualified to the desired [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] les clients peuvent choisir de capturer les signaux/caractéristiques/segments pertinents par rapport aux profils d’utilisateur et d’envoyer ces informations par assimilation [de données](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) hors ligne à [!DNL Audience Manager]. Please note that the user will continue to get qualified to the original [!UICONTROL trait] and [!UICONTROL segments] if they repeat their behavior.
