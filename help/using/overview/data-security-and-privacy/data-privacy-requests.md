---
description: Ce document couvre les aspects techniques associés à la conformité des réglementations en matière de confidentialité des données pour Audience Manager.
seo-description: Ce document couvre les aspects techniques associés à la conformité des réglementations en matière de confidentialité des données pour Audience Manager.
seo-title: Requêtes de confidentialité des données
solution: Audience Manager
keywords: Interface utilisateur GDPR, API GDPR, CCPA, confidentialité
title: Requêtes de confidentialité des données
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 60%

---

# Requêtes de confidentialité des données {#data-privacy-requests}

## Présentation {#overview}

Ce document fournit un aperçu de la gestion de la confidentialité des données individuelles et des demandes d’exclusion que vous pouvez envoyer à [!DNL Audience Manager] par l’intermédiaire de l’[interface utilisateur Privacy Service](https://privacyui.cloud.adobe.io/) et de **[!DNL Privacy Service API]**.

Ces outils vous permettent d&#39;envoyer des demandes de confidentialité de données de consommation effectuées sous [!DNL GDPR] et [!DNL CCPA].

Avant de lire cet article, nous vous recommandons de parcourir le [glossaire du RGPD](../data-security-and-privacy/aam-gdpr-glossary.md) et le [glossaire de la CCPA](aam-ccpa-glossary.md), afin de mieux comprendre la terminologie utilisée dans le présent document.

Vous pouvez envoyer des requêtes individuelles pour accéder aux données des consommateurs et les supprimer de [!DNL Audience Manager], de deux manières :

* Depuis l’[interface utilisateur de Privacy Service](https://privacyui.cloud.adobe.io/). Consultez la documentation [ici](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Depuis le **[!DNL Privacy Service API]**. Voir la documentation [ici](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) et la référence [!DNL API] [ici](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Lors de l&#39;envoi de demandes de confidentialité de données individuelles, vous pouvez envoyer n&#39;importe quel [!DNL Audience Manager] identifiant (ID), comme décrit dans la section **[Identifiants d&#39;Audience Manager](data-privacy-ids.md)**, ainsi que leurs identifiants d&#39;espace de nommage respectifs (ID de source de données).

[Privacy Service](https://docs.adobe.com/content/help/fr-FR/experience-platform/privacy/home.html) prend en charge deux types de demandes : les demandes d’accès aux données et de suppression de données.

## Demandes d’accès aux données {#access-data}

Vous pouvez envoyer des requêtes d&#39;accès aux données individuelles par l&#39;[interface utilisateur du Privacy Service](https://privacyui.cloud.adobe.io) (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) ou en appelant l&#39;API du Privacy Service (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) et [!DNL API] référence [ici](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

L’[interface utilisateur de Privacy Service](https://privacyui.cloud.adobe.io/) vous permet de créer de nouvelles requêtes de tâche, soit en utilisant le [!UICONTROL Request Builder] soit en chargeant un fichier [!DNL JSON].

Pour voir à quoi un fichier [!DNL JSON] valide ressemble, vous pouvez [ télécharger un exemple JSON](../data-security-and-privacy/assets/access_request.json).

Nous comprenons votre implication dans le respect des demandes de confidentialité des données pendant la période définie par la loi.

## Demandes de suppression de données {#delete-data}

Vous pouvez envoyer des demandes de suppression de données par l&#39;[interface utilisateur Privacy Service](https://privacyui.cloud.adobe.io) (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) ou en appelant l&#39;API Privacy Service (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) et [!DNL API] référence [ici](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

L’[interface utilisateur de Privacy Service](https://privacyui.cloud.adobe.io/) vous permet de créer de nouvelles requêtes de tâche, soit en utilisant le [!UICONTROL Request Builder] soit en chargeant un fichier [!DNL JSON].

Pour voir à quoi un fichier [!DNL JSON] valide ressemble, vous pouvez [ télécharger un exemple JSON](../data-security-and-privacy/assets/access_request.json).

Adobe comprend votre implication dans le respect des demandes de confidentialité des données des clients dans les 30 jours. Pour cette raison, [!DNL Adobe] s&#39;engage à traiter votre demande de suppression de données le plus rapidement possible.

En réponse à vos demandes de suppression de données de consommateurs, [!DNL Audience Manager] supprime les caractéristiques et les segments associés à l&#39;identifiant [!DNL Audience Manager] inclus dans la demande. En outre, les identifiants [!DNL Audience Manager] respectifs pour la personne choisie pour la collecte de données ultérieure par [!DNL Audience Manager] et les mappages d&#39;ID correspondants seront supprimés.

Lorsque vous envoyez des identifiants déclarés, comme des identifiants [!DNL CRM] multiterminaux ou des identifiants de , dans des demandes de confidentialité des données,  réalisera la suppression nécessaire sur tous les appareils associés (jusqu’à 100 appareils par identifiant déclaré).[!DNL cookie][!DNL Audience Manager]

[!DNL Audience Manager] essaiera de notifier les partenaires d’activation concernant les requêtes de suppression en leur envoyant des informations non segmentées pour les titulaires de données demandant la suppression de certaines données. En revanche, certains partenaires d’activation :

1. Impossible de prendre en charge les requêtes de segments non segmentés (ou de supprimer des segments) de [!DNL Audience Manager] et/ou
2. Ne peuvent pas recevoir de mises à jour de [!DNL Audience Manager] avec une fréquence inférieure à 30 jours. Dans ces cas, les clients [!DNL Audience Manager] ne peuvent pas envoyer de demandes de suppression à leurs partenaires d&#39;activation de manière automatisée via [!DNL Audience Manager].

Dans ces cas, vous ne pouvez pas envoyer de requêtes de suppression à des partenaires d&#39;activation de manière automatisée via [!DNL Audience Manager].

Téléchargez notre [fiche Excel de partenaire](assets/AAM-Partners-October2019.xlsx) pour savoir quels [!DNL Audience Manager] partenaires d&#39;activation prennent en charge le non-segmentation.

## Demandes d’exclusion {#opt-out-requests}

[!DNL Audience Manager] soutient les normes à l&#39;échelle de l&#39;industrie en ce qui concerne la gestion des exclusions. Lisez la suite pour obtenir des informations complètes sur les types d’exclusion pris en charge par [!DNL Audience Manager].

Bien que les demandes d’accès aux données et de suppression soient traitées par le [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), les demandes d’exclusion sont actuellement prises en charge par le biais du [!DNL DCS API]. Lisez la suite pour savoir à quoi les appels d&#39;exclusion [!DNL API] doivent ressembler.

### Demandes d’exclusion globales

L’exclusion globale représente une exclusion pour [!DNL Audience Manager] et d’autres solutions [!DNL Adobe Experience Cloud] pour toutes les marques. Le tableau ci-dessous reprend les méthodes utilisées pour les exclusions globales :

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
   <td colname="col2"> <p>La page <a href="https://www.adobe.com/fr/privacy/opt-out.html#customeruse" format="http" scope="external"> Vos choix en matière de confidentialité </a> propose des fonctionnalités en un clic qui permettent aux utilisateurs finaux de contrôler et d’exclure la collecte de données par les solutions publicitaires Adobe Experience Cloud (y compris Audience Manager). À ce titre, vous pouvez vous reporter à la <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> section client professionnel </a> de la page Vos choix en matière de confidentialité. </p> </td> 
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

L’exclusion au niveau du partenaire vous permet d’exclure vos utilisateurs de la collecte de données par des partenaires [!DNL Audience Manager] spécifiques. Vous pouvez envoyer des demandes d’exclusion au niveau du partenaire pour les identifiants entre périphériques, y compris les [!DNL CRM] identifiants et les adresses électroniques hachées.

Suite à une exclusion au niveau du partenaire avec un appel d’identifiant déclaré :

* L’[identifiant CRM](../../reference/ids-in-aam.md) est exclu de la collecte de données.
* Le dernier identifiant d’appareil ([l’identifiant utilisateur unique Audience Manager](../../reference/ids-in-aam.md)) associé à l’[identifiant CRM](../../reference/ids-in-aam.md) est exclu de la collecte de données.
* [!DNL Audience Manager] cessera toute collecte de données, segmentation ou activation à venir pour l’identifiant et le dernier identifiant d’appareil associé à l’identifiant .[!DNL CRM][!DNL CRM]
* [!DNL Audience Manager] dissocie l’ [!DNL CRM] ID de désabonnement et le dernier ID de périphérique de tous les segments ;
* [!UICONTROL Destination]Les partenaires de reçoivent la requête de suppression de la segmentation pour l’identifiant et le dernier identifiant de l’appareil. [!DNL CRM] La suppression de la segmentation fonctionne pour les destinations en [temps réel](data-privacy-requests.md#aam-partners-with-unsegmentation) et par lots.
* Aucune donnée historique n’est supprimée.

Lorsque [!DNL Audience Manager] reçoit une demande d&#39;exclusion au niveau du partenaire, [!DNL JSON] renvoyée par [!DNL DCS] contient le [code d&#39;erreur 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), avec le message [!UICONTROL "Encountered opt out tag"], au lieu de l&#39;[!DNL Audience Manager] ID utilisateur.

Vous pouvez faire une demande d’exclusion d’identifiant déclaré avec les paires clé-valeur `d_cid` et `d_cid_ic`. Les paramètres hérités comme `d_dpid` et `d_dpuuid` fonctionnent toujours, mais sont considérés comme obsolètes. Voir [CID remplace DPID et DPUUID](../../reference/cid.md). Dans les exemples, le texte en *italique* indique un espace réservé de variable.

#### Exclusion avec [!DNL CID] et [!DNL CID_IC]

Pour obtenir une description et une syntaxe, consultez les [variables et la syntaxe d’URL pour les identifiants déclarés](../../features/declared-ids.md#variables-and-syntax).

| Exclusion à l’aide | Exemple de code |
|--- |--- |
| d’un identifiant de fournisseur de données et d’un identifiant utilisateur. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| d’un code d’intégration et d’un identifiant utilisateur. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Plusieurs paires `d_cid` et `d_cid_ic` clé-valeur. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Exclusion au niveau du partenaire avec des appels d’identifiants d’appareil

L’exclusion au niveau du partenaire vous permet d’exclure vos utilisateurs de la collecte de données par des partenaires [!DNL Audience Manager] spécifiques. Vous pouvez exclure de la collecte de données un identifiant d’appareil donné pour une marque en effectuant les appels suivants sur l’[API DCS](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md) :

| Exclusion à l’aide | Exemple de code |
|--- |--- |
| Un [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un ID [!DNL Experience Cloud] (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Découvrez-en plus sur `uuid`, `mid` et `imsOrgId` dans l’[index des identifiants dans Audience Manager](/help/using/reference/ids-in-aam.md).

Suite à une exclusion au niveau du partenaire avec un appel d’identifiant d’appareil :

* L’identifiant d’appareil est exclu de la collecte de données.
* [!DNL Audience Manager] cessera toute collecte de données, segmentation ou activation pour le partenaire à venir par l’identifiant d’appareil.
* [!DNL Audience Manager] dissocie l’ID de périphérique de tous les segments ;
* Les partenaires de destination reçoivent la requête de suppression de la segmentation de l’identifiant de l’appareil. La suppression de la segmentation fonctionne pour les destinations en [temps réel](data-privacy-requests.md#aam-partners-with-unsegmentation) et par lots.
* Aucune donnée historique n’est supprimée.

## [!DNL Audience Manager] Partenaires Disposant De Capacités De Désegmentation  {#aam-partners-with-unsegmentation}

Afin de vous aider à automatiser vos requêtes de confidentialité des données des consommateurs, [!DNL Audience Manager] tentera d&#39;avertir les partenaires d&#39;activation des demandes de suppression des objets de données en les envoyant des informations de non-segmentation (ou de suppression de segment).

Cependant, certains de nos partenaires d’activation :

1. Impossible de prendre en charge les requêtes non segmentées de [!DNL Audience Manager] et/ou
2. Ne peuvent pas recevoir les mises à jour de [!DNL Audience Manager] plus d&#39;une fois par 30 jours.

Dans ces cas, vous ne pouvez pas envoyer de requêtes de suppression à des partenaires d&#39;activation de manière automatisée via [!DNL Audience Manager].

Consultez la [liste des destinations basées sur un périphérique](/help/using/features/destinations/device-based-destinations-list.md) pour savoir quels partenaires d&#39;activation [!DNL Audience Manager] prennent en charge le non-segmentation.

## Demandes de correction de données {#correction}

Étant donné que [!DNL Audience Manager] n&#39;est pas la source des données, il existe un rôle limité pour la correction des données dans [!DNL Audience Manager]. La correction peut signifier que le consommateur a demandé soit d&#39;être disqualifié d&#39;un [!UICONTROL trait]/[!UICONTROL segment] incorrect, soit de se qualifier à [!UICONTROL trait]/[!UICONTROL segment] souhaité.

[!DNL Audience Manager] les clients peuvent choisir de capturer les signaux/caractéristiques/segments pertinents par rapport aux profils d’utilisateurs et d’envoyer ces informations par le biais d’une  [analyse des données ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) hors ligne sur  [!DNL Audience Manager]le site. Veuillez noter que l&#39;utilisateur continuera à être qualifié pour les [!UICONTROL trait] et [!UICONTROL segments] d&#39;origine s&#39;il répète son comportement.
