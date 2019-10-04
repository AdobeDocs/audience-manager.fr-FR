---
description: Ce document décrit les aspects techniques du Règlement général sur la protection des données (RDMD) d’Audience Manager et vous explique comment envoyer des demandes de RDMD à Audience Manager.
seo-description: This document covers the technicalities related to the General Data Protection Regulation (GDPR) for Audience Manager and shows you how to submit GDPR requests to Audience Manager.
seo-title: RGPD dans Audience Manager
solution: Audience Manager
keywords: GDPR UI, GDPR API
title: RGPD dans Audience Manager
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 5661bcef9816b6646ee63ebc6c19b730c1ccadc9

---


# RGPD dans Audience Manager{#gdpr-in-audience-manager}

Ce document décrit les aspects techniques du Règlement général sur la protection des données (RDMD) d’Audience Manager et vous explique comment envoyer des demandes de RDMD à Audience Manager.

## Documentation GDPR dans Experience Cloud {#gdpr-documentation}

Avant de lire les détails d’Audience Manager, nous vous conseillons de consulter le document Experience Cloud relatif au Règlement général européen sur la protection des données (RDPC), lié ci-dessous :

* [GDPR and Your Business](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [Livre blanc GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [Terminologie relative au règlement général sur la protection des données (RGPD)](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

The sections below explain what GDPR means for Audience Manager and how you can submit GDPR requests to Audience Manager.

## Types de demandes de RPMD et Comment faire une demande de RPMD {#types-of-gdpr-requests}

En tant qu’utilisateur d’Audience Manager, vous pouvez envoyer des demandes GDPR individuelles pour accéder aux données client et les supprimer, soit par l’intermédiaire de l’interface utilisateur **** Privacy Service (lien[IU ici](https://gdprui.cloud.adobe.io/) et [documentation ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)), soit en appelant l’API **Privacy Service (documentation ici et référence à l’API ici).**[](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)[](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml) You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). Si vous avez des questions, contactez le service à la clientèle à l’adresse gdprsupport@adobe.com.

## Accéder aux données {#access-data}

Nous comprenons votre engagement à répondre à vos demandes de clients du RMDP dans les 30 jours suivant la réception. For that reason, we try to process your data access request as soon as possible.

**Demande**

Vous pouvez consigner les demandes d’accès aux données par l’intermédiaire de l’interface utilisateur **de** Privacy Service (lien[IU ici](https://gdprui.cloud.adobe.io/) et [documentation ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)) ou en appelant l’API de **Privacy Service (documentation ici et référence à l’API de ici).**[](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)[](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml) Dans les deux cas, vous devez charger un fichier JSON avec les identifiants Audience Manager pour lesquels vous envoyez la demande d’accès aux données. Pour voir à quoi ressemble un fichier JSON bien formé, vous pouvez **[télécharger un exemple de fichier JSON](assets/access_request.json)**.

**Réponse**

Les réponses aux demandes d’accès aux données contiennent un résumé du nombre total de caractéristiques et de segments, du type de caractéristique, des descriptions des caractéristiques et des segments, ainsi que des noms de source de données respectifs. La réponse Access inclura également les données tierces et de deuxième partie accessibles au contrôleur de données, ainsi que les données propriétaires. Lorsque [!UICONTROL declared IDs] des ID de gestion de la relation client inter-périphériques ou des ID de cookie client sont envoyés dans des demandes GDPR, Audience Manager inclut la réponse Access de tous les périphériques liés (jusqu’à 100 périphériques par ID déclaré).

**État de la réponse**

S’il y a des erreurs d’Audience Manager dans la réponse, celles-ci sont affichées sous forme de codes d’erreur dans la réponse. Nous avons une [liste de codes](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)d'erreur, où vous pouvez trouver plus d'informations sur les erreurs renvoyées.

**Exemple de réponse**

Un exemple de réponse d’accès peut ressembler à celui ci-dessous. Dans cet exemple, l’ID de la personne concernée est un ID de cookie. They qualified for several traits and belong to a few segments. The cookie ID is linked to a mobile ID. L’exemple contient également des métadonnées pour le téléphone qu’ils utilisent.

```
{
  "id": "45338264191156397602180946733455975613",
  "namespace": {
    "id": 0,
    "integration code": "",
    "data provider name": "Demdex, Inc",
    "type": "COOKIE"
  },
  "warnings": [{
    "title": "Device Data",
    "description": "Contains data from all users of this device"
  }],
  "data": {
    "traits": [{
      "name": "Website Visitors",
      "type": "1st party",
      "description": "All Active Visitors",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Interested in Italian Holidays",
      "type": "1st party",
      "description": "Query string contains holidays/bella_italia",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37"
    }, {
      "name": "Lifestyle>Recreational>Garden Party",
      "type": "3rd party",
      "description": "Survey respondents that have expressed an interest in hosting garden parties",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:36"
    }],
    "segments": [{
      "name": "test",
      "description": "Interested in Photography",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "false"
    }, {
      "name": "Traveler and Frequent Flier",
      "description": "",
      "data export controls": [],
      "data provider name": "A third party data provider",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }, {
      "name": "Interested in Sports",
      "description": "",
      "data export controls": [],
      "data provider name": "My company",
      "last realization": "2018-04-10 17:00:37",
      "active": "true"
    }]
  },
  "links": [{
    "id": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2",
    "namespace": {
      "id": 20914,
      "integration code": "DSID_20914",
      "data provider name": "Google",
      "type": "MOBILE"
    },
    "linking datetime": "2018-04-10 17:00:37"
  }],
  "deviceMetadata": {
    "hardware": "Mobile Phone",
    "manufacturer": "Samsung",
    "marketing name": "Galaxy S8 Plus",
    "model": "",
    "os name": "Android",
    "os version": "7.0",
    "vendor": "Samsung"
  }
}
```

Le tableau ci-dessous décrit tous les champs renvoyés dans la réponse d’accès aux données, dans l’ordre dans lequel ils apparaissent ci-dessus.

<table id="table_DF08231257F64588B98BD71A088C50DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Champ </p> </th> 
   <th colname="col2" class="entry"> <p>Description </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>The user ID for the data that follows. Il s’agit soit d’un ID que vous avez fourni dans la demande d’accès aux données GDPR, soit d’un ID lié à l’un des ID déclarés que vous avez fournis. Les types d’ID sont décrits dans la section Identifiants <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> d’Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>Également appelé source de données. See the  Audience Manager Identifiers section.<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>L’ID de l’espace de noms/la source de données. Voir <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Identifiants (ID)</a> Audience Manager pour toutes les valeurs acceptées. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> integration code </code> </p> </td> 
   <td colname="col2"> <p>Les codes d’intégration sont des noms conviviaux pour vos sources de données et vous aident à effectuer le suivi de vos sources de données plus facilement qu’en utilisant des ID de source de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nom du fournisseur de données </code> </p> </td> 
   <td colname="col2"> <p>Nom du propriétaire de la source de données. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">Pour les données propriétaires, il s’agit du nom de l’entreprise du client. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">Pour les données tierces, il s’agit du nom de la société partenaire. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">Pour les données tierces, il s’agit du nom du partenaire de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>Le type d’ID pour lequel vous avez demandé l’accès aux données en vertu du RGPD. Accepted types are listed in the  Audience Manager Identifiers section.<a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> warnings</code> </p> </td> 
   <td colname="col2"> <p>Warnings return further information related to the data access request. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> titre </code> </p> </td> 
   <td colname="col2"> <p>Brief information about the warning. </p> <p>The two warnings you may receive are: </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Device Data </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Requête incomplète </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>A more detailed description of the warning you received: </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Device Data - Contains data from all users of this device </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">Incomplete request - Retrieval of Audience Manager data was not completed. Certaines informations peuvent être manquantes. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data </code> </p> </td> 
   <td colname="col2"> <p>Caractéristiques et segments associés à cet ID utilisateur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>Caractéristiques associées à l’ID utilisateur. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>Nom du trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>The trait type. Les valeurs possibles sont les suivantes : </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>Première partie</i> pour vos propres caractéristiques. </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Deuxième partie</i> pour les caractéristiques qui appartiennent à vos partenaires. Consultez notre <a href="../../overview/data-types-collected.md#second-party-data"> article sur les données</a> de deuxième partie pour en savoir plus. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Tierce</i> pour les caractéristiques obtenues auprès des partenaires de données, via <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>A few words to help describe the trait's purpose or function. Il s’agit d’un champ facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> contrôles des exportations de données</code> </p> </td> 
   <td colname="col2"> <p>Les contrôles <a href="../../features/data-export-controls.md"> d’exportation de</a> données appliqués à la source de données de cette caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nom du fournisseur de données</code> </p> </td> 
   <td colname="col2"> <p>Nom du propriétaire de la source de données à laquelle appartient cette caractéristique. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">Pour les données propriétaires, il s’agit du nom de l’entreprise du client. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">Pour les données tierces, il s’agit du nom de la société partenaire. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">Pour les données tierces, il s’agit du nom du partenaire de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dernière réalisation</code> </p> </td> 
   <td colname="col2"> <p>Heure exacte à laquelle le sujet de données s'est qualifié pour la dernière fois pour cette caractéristique. Le format de date est AAAA-MM-JJ. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segments </code> </p> </td> 
   <td colname="col2"> <p>Segments auxquels cet utilisateur appartient. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>Nom du segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Quelques mots pour décrire ce segment. Il s’agit d’un champ facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> contrôles des exportations de données</code> </p> </td> 
   <td colname="col2"> <p>The  data export controls applied to this segment's data source.<a href="../../features/data-export-controls.md"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nom du fournisseur de données</code> </p> </td> 
   <td colname="col2"> <p>Nom du propriétaire de la source de données à laquelle ce segment appartient. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">Pour les données propriétaires, il s’agit du nom de l’entreprise du client. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">Pour les données tierces, il s’agit du nom de la société partenaire. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">Pour les données tierces, il s’agit du nom du partenaire de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> last realization</code> </p> </td> 
   <td colname="col2"> <p>The exact time that the Data Subject last qualified for this segment. Le format de date est AAAA-MM-JJ. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> actif</code> </p> </td> 
   <td colname="col2"> <p>Indicates whether the Data Subject is currently qualified for this segment. Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> liens </code> </p> </td> 
   <td colname="col2"> <p>Additional ID that this ID has been linked to. Les informations sont renvoyées le : </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (data source) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">namespace ID </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">integration code </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">nom du fournisseur de données </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">Type d’ID </li> 
     </ul> </p> <p>Tous ces champs sont décrits dans les premières lignes du tableau. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> linking datetime</code> </p> </td> 
   <td colname="col2"> <p>Heure exacte à laquelle un événement de synchronisation des identifiants a créé le lien entre les identifiants. Le format de date est AAAA-MM-JJ. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> métadonnées de périphérique </code> </p> </td> 
   <td colname="col2"> <p>Informations sur le périphérique. Ces informations comprennent les champs ci-dessous. Notez que tous les champs ne sont pas renvoyés pour tous les types de périphériques. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Informations sur le matériel </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>Fabricant du périphérique </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>Nom marketing du périphérique </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>The device model </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>Nom du système d’exploitation (SE) du périphérique </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>Version du système d’exploitation </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>Le fournisseur du périphérique </p> </li> 
     </ul> </p> <p> <p>Remarque : Nous ne renvoyons les métadonnées de périphérique que lorsque vous envoyez l’un des éléments suivants : 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">ID mobiles </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Audience Manager IDs </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Experience Cloud IDs </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Supprimer des données {#delete-data}

Nous comprenons votre engagement à répondre à vos demandes de clients du RMDP dans les 30 jours suivant la réception. C'est pourquoi nous essayons de traiter votre demande de suppression de données le plus rapidement possible.

**Demande**

Vous pouvez consigner les demandes de suppression de données par l’intermédiaire de l’interface utilisateur **de** Privacy Service (lien[IU ici](https://gdprui.cloud.adobe.io/) et [documentation ici](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)) ou en appelant l’API de **Privacy Service ( documentation ici et référence à l’API de ici).**[](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md)[](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml) In either case, you must upload a JSON with the Audience Manager identifiers for which you are submitting the data access request. To see what a well-formed JSON looks like, you can download a sample JSON.**[](assets/delete_request.json)**

**Réponse**

In response to data deletion requests, we delete traits and segments associated with the respective Audience Manager identifier. In addition, the respective Audience Manager identifiers for the Data Subject will be permanently opted out of further data collection by Audience Manager and the respective Id mappings will be removed. Lorsque des ID déclarés, tels que des ID CRM inter-périphériques ou des ID de cookie client sont envoyés dans des demandes GDPR, Audience Manager effectue les actions de suppression nécessaires sur tous les périphériques liés (jusqu’à 100 périphériques par ID déclaré).

## Opt-out Request {#opt-out-request}

For opt-out requests, please refer to our documentation on Opt-out Management.[](../../overview/data-security-and-privacy/opt-out-management.md)

## Identifiants (ID) Audience Manager {#aam-ids}

Lors de l’envoi de demandes GDPR à Adobe Audience Manager, vous devez inclure l’un des identifiants (ID) répertoriés ci-dessous. Vous trouverez plus d’informations sur les formats d’ID dans notre [Index des identifiants](../../reference/ids-in-aam.md)Audience Manager.

### Adobe Audience Manager Unique User ID

**User ID: aam_uuid**

**Définition**: ID utilisateur unique Adobe Audience Manager

**ID** d’espace de noms : 0

>[!NOTE]
>
>Vous pouvez également utiliser l’espace de noms CORE. Voir le deuxième exemple JSON.

**Exemple dans JSON**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

### Adobe Experience Cloud ID

**ID** utilisateur : mid

**Définition**: Adobe Experience Cloud ID, anciennement appelé identifiant visiteur ou Marketing Cloud ID

**Namespace ID**: 4

>[!NOTE]
>
>Vous pouvez également utiliser l’espace de noms ECID. See the second JSON example.

**Exemple dans JSON**:

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

### Customer ID

**User ID: cid**

**Définition**: ID de client, tel qu’un cookie que vous avez défini pour les visiteurs anonymes du site ou un ID de gestion de la relation client provenant d’un système hors ligne ou un nom d’utilisateur haché

**ID** d’espace de noms : Spécifique au client. Please find it from your Audience Manager instance.

**Example in JSON:**

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

### Mobile advertising ID

**ID** utilisateur : d_cid

**Définition**: Identifiants de publicité mobile.
>[!IMPORTANT]
>
> Si vous utilisez Mobile SDK, vous devez également envoyer le MID Experience Cloud ID (MID) avec les ID de publicité mobile pour obtenir des réponses d’accès au RDDC et de suppression complètes.

**ID d’espace de noms**:

* IDFA: 20915
* GAID : 2014

**Example in JSON:**

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

### Code d’intégration

**ID** utilisateur : d_cid_ic

**Definition: An integration code for the data source.** Vous pouvez l’utiliser à la place de l’ID de source de données/de l’ID d’espace de noms dans la demande d’API au service principal de confidentialité d’Adobe Experience Cloud.

**ID** d’espace de noms : Sans objet

Exemple dans JSON :

```
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
