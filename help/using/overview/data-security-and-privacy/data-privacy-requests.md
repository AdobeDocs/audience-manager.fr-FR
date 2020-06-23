---
description: Ce document couvre les aspects techniques liés à la conformité aux règlements sur la confidentialité des données pour l'Audience Manager.
seo-description: Ce document couvre les aspects techniques liés à la conformité aux règlements sur la confidentialité des données pour l'Audience Manager.
seo-title: Requêtes de confidentialité des données
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Requêtes de confidentialité des données
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 1%

---


# Requêtes de confidentialité des données {#data-privacy-requests}

## Aperçu {#overview}

Ce document présente une vue d’ensemble de la gestion de la confidentialité des données individuelles et des demandes d’exclusion que vous pouvez envoyer [!DNL Audience Manager] par le biais de l’interface utilisateur [](https://privacyui.cloud.adobe.io/) Privacy Service et de la **[!DNL Privacy Service API]** boîte de dialogue.

Ces outils vous permettent d’envoyer des demandes de confidentialité de données de consommation effectuées sous [!DNL GDPR] et [!DNL CCPA].

Avant de lire le présent article, nous recommandons de consulter le glossaire [du](../data-security-and-privacy/aam-gdpr-glossary.md) RGMD et le glossaire [de l&#39;](aam-ccpa-glossary.md)ACCP, afin de mieux comprendre la terminologie utilisée ici.

Vous pouvez envoyer des requêtes individuelles pour accéder aux données des consommateurs et les supprimer de [!DNL Audience Manager]deux manières :

* Par le biais de l’interface utilisateur [](https://privacyui.cloud.adobe.io/)Privacy Service. Consultez la documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Par le **[!DNL Privacy Service API]**. Voir la documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) et la [!DNL API] référence [ici](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Lors de l’envoi de requêtes de confidentialité de données individuelles, vous pouvez envoyer des [!DNL Audience Manager] identifiants (identifiants), comme décrit dans la section Identifiants **[d’](data-privacy-ids.md)**Audience Manager, ainsi que leurs identifiants d’espace de nommage respectifs (identifiants de source de données).

Le [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) prend en charge deux types de requêtes : demandes d’accès aux données et de suppression de données.

## Demandes d’accès aux données {#access-data}

Vous pouvez envoyer des requêtes d’accès aux données individuelles par l’intermédiaire de l’interface [du](https://privacyui.cloud.adobe.io/) Privacy Service (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) ou en appelant le [!DNL Privacy Service API] (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) et  référence ici).[!DNL API][](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)

L’interface utilisateur [du](https://privacyui.cloud.adobe.io/) Privacy Service vous permet de créer de nouvelles demandes de travaux à l’aide du [!UICONTROL Request Builder] ou en téléchargeant un [!DNL JSON] fichier.

Pour voir à quoi ressemble un [!DNL JSON] fichier valide, vous pouvez [télécharger un exemple de fichier JSON](../data-security-and-privacy/assets/access_request.json).

Nous comprenons votre engagement à respecter vos demandes de confidentialité dans le délai fixé par la loi.

## Demandes de suppression de données {#delete-data}

Vous pouvez envoyer des demandes de suppression de données par l’intermédiaire de l’interface [](https://privacyui.cloud.adobe.io/) Privacy Service (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) ou en appelant le [!DNL Privacy Service API] (documentation [ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) et  référence ici).[!DNL API][](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)

L’interface utilisateur [du](https://privacyui.cloud.adobe.io/) Privacy Service vous permet de créer de nouvelles demandes de travaux à l’aide du [!UICONTROL Request Builder] ou en téléchargeant un [!DNL JSON] fichier.

Pour voir à quoi ressemble un [!DNL JSON] fichier valide, vous pouvez [télécharger un exemple de fichier JSON](../data-security-and-privacy/assets/access_request.json).

Adobe comprend votre engagement à respecter vos demandes de confidentialité de données dans les 30 jours. C&#39;est pourquoi [!DNL Adobe] nous nous engageons à traiter votre demande de suppression de données dans les plus brefs délais.

En réponse à vos demandes de suppression de données de consommateurs, [!DNL Audience Manager] supprime les caractéristiques et les segments associés à l’ [!DNL Audience Manager] identifiant inclus dans la demande. En outre, les [!DNL Audience Manager] identifiants respectifs des individus qui ont choisi de ne pas collecter d’autres données par [!DNL Audience Manager] et les mappages d’ID respectifs seront supprimés.

Lorsque vous envoyez des identifiants déclarés, tels que [!DNL CRM] des identifiants ou [!DNL cookie] des identifiants inter-périphériques, dans les demandes de confidentialité des données, [!DNL Audience Manager] la suppression nécessaire est effectuée sur tous les périphériques liés (jusqu’à 100 périphériques par identifiant déclaré).

[!DNL Audience Manager] essaiera d&#39;informer les partenaires d&#39;activation des demandes de suppression en leur envoyant des informations non segmentées pour les sujets de données demandant la suppression de certaines données. Cependant, certains partenaires d&#39;activation :

1. Impossible de prendre en charge les requêtes non segmentées (ou de supprimer des segments) de [!DNL Audience Manager] et/ou
2. Ne peuvent pas recevoir de mises à jour [!DNL Audience Manager] avec une fréquence inférieure à 30 jours. Dans ces cas, [!DNL Audience Manager] les clients ne peuvent pas envoyer de demandes de suppression à leurs partenaires d&#39;activation de manière automatisée [!DNL Audience Manager].

Dans ces cas, vous ne pouvez pas envoyer de requêtes de suppression aux partenaires d&#39;activation de manière automatisée [!DNL Audience Manager].

Téléchargez notre fiche [Excel](assets/AAM-Partners-October2019.xlsx) Partenaires pour identifier les partenaires [!DNL Audience Manager] d&#39;activation qui prennent en charge le non-segmentation.

## Demandes d’exclusion {#opt-out-requests}

[!DNL Audience Manager] soutient les normes à l&#39;échelle de l&#39;industrie en ce qui concerne la gestion des exclusions. Lisez la suite pour obtenir des informations complètes sur les types d’exclusion pris en charge par [!DNL Audience Manager].

Bien que les demandes d’accès aux données et de suppression soient traitées par le [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html), les demandes d’exclusion sont actuellement prises en charge par le biais du [!DNL DCS API]. Lisez la suite pour en savoir plus sur les [!DNL API] appels d’exclusion.

### Demandes d’exclusion globales

L’exclusion globale représente une exclusion pour toutes les marques [!DNL Audience Manager] et d’autres [!DNL Adobe Experience Cloud] solutions. Le tableau ci-dessous liste les méthodes utilisées pour l’exclusion globale :

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
   <td colname="col2"> <p>La page <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Vos choix en matière de confidentialité </a> propose des fonctionnalités d’un clic qui permettent aux utilisateurs finaux de contrôler la collecte de données et de s’en désabonner grâce aux solutions publicitaires Adobe Experience Cloud (y compris les Audiences Manager). En particulier, consultez la section réservée aux <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> clients professionnels </a> de la page Choix de confidentialité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Appels d'API directs à l'Audience Manager </p> </td> 
   <td colname="col2"> <p>Vos utilisateurs peuvent se désabonner de la collecte de données par toutes les marques d’Audience Manager en appelant l’API DCS ci-dessous et en incluant l’ID utilisateur <a href="../../reference/ids-in-aam.md"> Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Par conséquent, nous définirons <code>demdex=NOTARGET</code> et <code>dextp=NOTARGET</code> cookies pour l’ID utilisateur d’Audience Manager envoyé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Appareils mobiles </p> </td> 
   <td colname="col2"> <p>Consultez les paramètres d’exclusion et de confidentialité pour : </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Périphériques Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> Appareils iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Vos utilisateurs finaux peuvent également opt-out de la collecte de données globale en visitant les sites Web de nos partenaires de normalisation du secteur.

* [La Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Suite aux demandes d’exclusion décrites ci-dessus :

* [!DNL Audience Manager] cessera la collecte, la segmentation ou l’activation de toutes les données tant que l’utilisateur n’efface pas les cookies de son navigateur.
* Les données historiques sont supprimées du profil utilisateur après 120 jours.

### Exclusion au niveau du partenaire avec appels d’ID déclarés

L’exclusion au niveau du partenaire vous permet d’exclure vos utilisateurs de la collecte de données par des [!DNL Audience Manager] partenaires spécifiques. Vous pouvez envoyer des demandes d’exclusion au niveau du partenaire pour les identifiants entre périphériques, y compris [!DNL CRM] les identifiants et les adresses électroniques hachées.

Suite à une exclusion au niveau du partenaire avec un appel d’ID déclaré :

* L’ID [](../../reference/ids-in-aam.md) CRM est retiré de la collecte de données ;
* Le dernier ID de périphérique (ID[d’utilisateur](../../reference/ids-in-aam.md)unique de l’ [Audience Manager) lié à l’ID](../../reference/ids-in-aam.md) degestion de la relation client est retiré de la collecte de données.
* [!DNL Audience Manager] mettra fin à la collecte, à la segmentation ou à l&#39;activation des données pour l&#39; [!DNL CRM] identifiant et le dernier ID de dispositif lié à l&#39; [!DNL CRM] identifiant ;
* [!DNL Audience Manager] dissocie l’identifiant [!DNL CRM] d’exclusion et le dernier ID de périphérique de tous les segments ;
* [!UICONTROL Destination] les partenaires reçoivent la demande de non-segmentation pour l&#39; [!DNL CRM] ID et le dernier ID de périphérique. La non-segmentation fonctionne à la fois pour les destinations [en temps](data-privacy-requests.md#aam-partners-with-unsegmentation) réel et par lot.
* Aucune donnée historique n&#39;est supprimée.

Lorsque [!DNL Audience Manager] reçoit une demande d’exclusion au niveau du partenaire, la [!DNL JSON] valeur renvoyée par le [!DNL DCS] contient le code d’ [erreur 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), avec le message [!UICONTROL "Encountered opt out tag"], au lieu de l’identifiant [!DNL Audience Manager] utilisateur.

Vous pouvez faire une demande d’exclusion d’ID déclarée avec les paires `d_cid` et `d_cid_ic` clé-valeur. Les paramètres hérités, tels que `d_dpid` et `d_dpuuid` fonctionnent toujours, sont considérés comme obsolètes. Voir [CID remplace DPID et DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

#### Exclusion avec [!DNL CID] et [!DNL CID_IC]

Pour obtenir une description et une syntaxe, voir Variables [d’URL et Syntaxe pour les identifiants](../../features/declared-ids.md#variables-and-syntax)déclarés.

| Exclusion à l’aide de | Exemple de code |
|--- |--- |
| ID de fournisseur de données et ID d’utilisateur. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Code d’intégration et ID utilisateur. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Plusieurs paires `d_cid` et `d_cid_ic` clé-valeur. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Exclusion au niveau partenaire avec appels d&#39;ID de périphérique

L’exclusion au niveau du partenaire vous permet d’exclure vos utilisateurs de la collecte de données par des [!DNL Audience Manager] partenaires spécifiques. Vous pouvez vous exclure de la collecte de données sur un ID de périphérique donné pour une marque en lançant les appels suivants à l’API [](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS :

| Exclusion à l’aide de | Exemple de code |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Pour en savoir plus sur `uuid`, `mid` et `imsOrgId` dans l’ [index des identifiants en Audience Manager](/help/using/reference/ids-in-aam.md).

Suite à une exclusion au niveau du partenaire avec un appel d’ID de périphérique :

* L’ID de périphérique est retiré de la collecte de données.
* [!DNL Audience Manager] cessera toute collecte, segmentation ou activation de données pour le partenaire, à partir de l&#39;identifiant du périphérique.
* [!DNL Audience Manager] dissocie l’ID de périphérique de tous les segments ;
* Les partenaires de destination reçoivent la demande de non-segmentation pour l&#39;ID de périphérique. La non-segmentation fonctionne à la fois pour les destinations [en temps](data-privacy-requests.md#aam-partners-with-unsegmentation) réel et par lot.
* Aucune donnée historique n&#39;est supprimée.

## [!DNL Audience Manager] Partenaires Disposant De Capacités De Désegmentation {#aam-partners-with-unsegmentation}

Afin de vous aider à automatiser vos requêtes de confidentialité des données des consommateurs, [!DNL Audience Manager] tentera d&#39;informer les partenaires d&#39;activation des demandes de suppression des objets de données en leur envoyant des informations de non-segmentation (ou de suppression de segment).

Cependant, certains de nos partenaires d&#39;activation :

1. Impossible de prendre en charge les requêtes non segmentées provenant de [!DNL Audience Manager] et/ou
2. Ne peuvent pas recevoir de mises à jour [!DNL Audience Manager] plus d’une fois par 30 jours.

Dans ces cas, vous ne pouvez pas envoyer de requêtes de suppression aux partenaires d&#39;activation de manière automatisée [!DNL Audience Manager].

Consultez la [liste des destinations](/help/using/features/destinations/device-based-destinations-list.md) basées sur un périphérique pour savoir quels partenaires d&#39; [!DNL Audience Manager] activation prennent en charge les segments non segmentés.

## Demandes de correction de données {#correction}

Étant donné que ce n&#39; [!DNL Audience Manager] est pas la source des données, il y a un rôle limité pour la correction des données dans [!DNL Audience Manager]. La correction pourrait signifier que le consommateur a demandé soit d&#39;être disqualifié d&#39;un [!UICONTROL trait]/[!UICONTROL segment] incorrect(e), soit d&#39;être qualifié(e) à l&#39;égard [!UICONTROL trait]/[!UICONTROL segment]souhaité(e).

[!DNL Audience Manager] les clients peuvent choisir de capturer les signaux/caractéristiques/segments pertinents par rapport aux profils d’utilisateur et d’envoyer ces informations par assimilation [de données](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) hors ligne à [!DNL Audience Manager]. Veuillez noter que l&#39;utilisateur continuera à être qualifié pour l&#39;original [!UICONTROL trait] et [!UICONTROL segments] s&#39;il répète son comportement.
