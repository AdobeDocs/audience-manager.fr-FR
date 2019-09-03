---
description: Ce document décrit les technicônes relatives au GDPR (General Data Protection Regulation) pour Audience Manager et explique comment envoyer des demandes GDPR à Audience Manager.
seo-description: Ce document décrit les technicônes relatives au GDPR (General Data Protection Regulation) pour Audience Manager et explique comment envoyer des demandes GDPR à Audience Manager.
seo-title: RGPD dans Audience Manager
solution: Audience Manager
title: RGPD dans Audience Manager
uuid: ed 23 a 478-32 be -460 d-bb 03-a 735317 f 7 c 0 f
translation-type: tm+mt
source-git-commit: 98914987331ce31bc8d3e67647d5b8273b287d4c

---


# RGPD dans Audience Manager{#gdpr-in-audience-manager}

Ce document décrit les technicônes relatives au GDPR (General Data Protection Regulation) pour Audience Manager et explique comment envoyer des demandes GDPR à Audience Manager.

## Documentation GDPR dans Experience Cloud {#gdpr-documentation}

Avant de lire les détails d'Audience Manager, nous vous conseillons d'utiliser le matériel Experience Cloud pour le GDPR (European General Data Protection Regulation), lié ci-dessous :

* [GDPR et votre entreprise](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [Livre blanc GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [Terminologie relative au règlement général sur la protection des données (RGPD)](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

Les sections ci-dessous décrivent ce que signifie le GDPR pour Audience Manager et comment vous pouvez envoyer des demandes GDPR à Audience Manager.

## Types de demandes GDPR et comment effectuer une demande GDPR {#types-of-gdpr-requests}

En tant qu'audience Manager Manager, vous pouvez envoyer des demandes GDPR individuelles pour accéder aux données client et les supprimer, soit via l'interface **[utilisateur des services client](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** GDPR, soit en appelant l'API **[GDPR](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)**. You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). Pour toute question, contactez le service d'assistance clientèle à l'adresse gdprsupport@adobe.com.

## Accéder aux données {#access-data}

Nous comprenons votre engagement à respecter vos demandes de clients GDPR dans les 30 jours qui suivent leur réception. C'est pourquoi nous tentons de traiter votre demande d'accès aux données dès que possible.

**Demande**

Vous pouvez enregistrer les demandes d'accès aux données via l'interface utilisateur des services client **[GDPR](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** ou en appelant l'API **[GDPR](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** (voir `access` action). Dans tous les cas, vous devez télécharger un fichier JSON avec les identificateurs Audience Manager pour lesquels vous envoyez la demande d'accès aux données. Découvrez à quoi ressemble un JSON bien formé dans la documentation d **['Experience Cloud GDPR](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** (en particulier, recherche dans la page pour « FORMAT DE DEMANDE POST »). Vous **[pouvez également télécharger un exemple de fichier JSON](assets/access_request.json)**.

**Réponse**

Les réponses à l'accès aux requêtes de données contiennent un résumé du nombre total de caractéristiques et de segments, du type de caractéristique, des descriptions des caractéristiques et des segments ainsi que des noms de source de données correspondants. La réponse Accès comprend également des données tierces et tierces accessibles au contrôleur de données, ainsi que les données propriétaires. Lorsque [!UICONTROL declared IDs] des identifiants CRM ou des identifiants de cookie client sont envoyés dans des demandes GDPR, Audience Manager inclura la réponse Access de tous les périphériques liés (jusqu'à 100 périphériques par ID déclarés).

**État de la réponse**

S'il existe des erreurs d'Audience Manager dans la réponse, elles sont affichées comme des codes d'erreur dans la réponse. Nous disposons d' [une liste de codes](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md)d'erreur qui vous permet d'obtenir davantage d'informations sur les erreurs renvoyées.

**Exemple de réponse**

Une réponse d'accès peut ressembler à celle ci-dessous. Dans cet exemple, l'ID du sujet de données est un identifiant de cookie. Ils sont qualifiés pour plusieurs caractéristiques et appartiennent à quelques segments. L'ID de cookie est lié à un ID mobile. L'exemple contient également des métadonnées pour le smartphone qu'elles utilisent.

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

Le tableau ci-dessous contient des descriptions pour tous les champs renvoyés dans la réponse d'accès aux données, dans l'ordre dans lequel ils apparaissent ci-dessus.

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
   <td colname="col2"> <p>Utilisateur - id pour les données qui suivent. Il s'agit soit d'un ID fourni dans la demande d'accès aux données GDPR, soit d'un ID lié à l'un des ID déclarés que vous avez fournis. Les types d'ID sont décrits dans <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> la section Identifiants</a> Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>Également appelé source de données. Voir <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> la section Identifiants</a> Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>L’ID de l’espace de noms/la source de données. Voir <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Identifiants d'Audience Manager (ID)</a> pour toutes les valeurs prises en charge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> integration code </code> </p> </td> 
   <td colname="col2"> <p>Les codes d'intégration sont des noms conviviaux pour vos sources de données et vous aident à effectuer un suivi plus facile sur vos sources de données que l'utilisation des identifiants de sources de données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nom du fournisseur de données </code> </p> </td> 
   <td colname="col2"> <p>Nom du propriétaire de la source de données. 
     <ul id="ul_5CEAF23C28154662AFC443D3494107D3"> 
      <li id="li_EC2DA09F618D4225B655ADF455C0D654">Pour les données propriétaires, il s'agit du nom d'entreprise du client. </li> 
      <li id="li_C4A5E1BD2A994109BBCD839DDC4B2E64">Pour les données tierces, il s'agit du nom de la société partenaire. </li> 
      <li id="li_1AA1246B7E40443CB18108512FBB8B19">Pour les données tierces, il s'agit du nom du partenaire de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type </code> </p> </td> 
   <td colname="col2"> <p>Le type d’ID pour lequel vous avez demandé l’accès aux données en vertu du RGPD. Les types acceptés sont répertoriés <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> dans la section Identifiants</a> Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> avertissements</code> </p> </td> 
   <td colname="col2"> <p>Les avertissements renvoient des informations supplémentaires concernant la demande d'accès aux données. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> titre </code> </p> </td> 
   <td colname="col2"> <p>Informations succinctes sur l'avertissement. </p> <p>Les deux avertissements que vous pouvez recevoir sont les suivants : </p> <p> 
     <ul id="ul_34019A1529594DC7B2566913937EAF0C"> 
      <li id="li_F0104BE3D5FE4DB7BA54195504E260E9">Données de périphérique </li> 
      <li id="li_8A22D9F9A1454AFDBC4CAF942E80498F">Demande incomplète </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description </code> </p> </td> 
   <td colname="col2"> <p>Description plus détaillée de l'avertissement reçu : </p> <p> 
     <ul id="ul_78E03ABA52674E07A48835FDD3431FF8"> 
      <li id="li_6BB6D58660594CA0B1A89804F2FC6274">Données de périphérique : contient les données de tous les utilisateurs de ce périphérique </li> 
      <li id="li_E328D5BF066C4E7E8CCCDCAA5E91CCDC">Demande incomplète : la récupération des données Audience Manager n'a pas été terminée. Certaines informations peuvent être manquantes. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> data </code> </p> </td> 
   <td colname="col2"> <p>Caractéristiques et segments associés à cet utilisateur - id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> traits </code> </p> </td> 
   <td colname="col2"> <p>Caractéristiques associées à l'utilisateur - id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> name</code> </p> </td> 
   <td colname="col2"> <p>Nom de la caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> type</code> </p> </td> 
   <td colname="col2"> <p>Type de caractéristique. Les valeurs possibles sont les suivantes : </p> <p> 
     <ul id="ul_DBAC618D9FE94B17B2494B83832A969F"> 
      <li id="li_740F2DCA8F2A4A22A7D9988ECD2FC976"> <i>Propriétaire</i> de vos propres caractéristiques. </li> 
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Tiers</i> pour les caractéristiques qui appartiennent à vos partenaires. Lisez <a href="../../overview/data-types-collected.md#second-party-data"> notre article Données</a> tierces pour en savoir plus. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Tiers</i> pour les caractéristiques obtenues auprès des partenaires de données, via <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Quelques mots pour décrire la finalité ou la fonction de la caractéristique. Il s'agit d'un champ facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> contrôles d'exportation de données</code> </p> </td> 
   <td colname="col2"> <p>Contrôles d'exportation <a href="../../features/data-export-controls.md"> de données</a> appliqués à la source de données de cette caractéristique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nom du fournisseur de données</code> </p> </td> 
   <td colname="col2"> <p>Nom du propriétaire de la source de données à laquelle cette caractéristique appartient. 
     <ul id="ul_D2D424E903A143779342D35D6F625656"> 
      <li id="li_55B3A40A6CD24A25B5AAFD07AD28F662">Pour les données propriétaires, il s'agit du nom d'entreprise du client. </li> 
      <li id="li_BC6A9F52543D4532BC7D90948D1EB35F">Pour les données tierces, il s'agit du nom de la société partenaire. </li> 
      <li id="li_DFD35A3E3E844E4993B59A62DB3C38D9">Pour les données tierces, il s'agit du nom du partenaire de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dernière concrétisation</code> </p> </td> 
   <td colname="col2"> <p>Heure exacte de la dernière qualification du sujet de données pour cette caractéristique. Le format de date est AAAA-MM-JJ. </p> </td> 
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
   <td colname="col2"> <p>Quelques mots pour décrire ce segment. Il s'agit d'un champ facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> contrôles d'exportation de données</code> </p> </td> 
   <td colname="col2"> <p>Contrôles d'exportation <a href="../../features/data-export-controls.md"> de données</a> appliqués à la source de données de ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> nom du fournisseur de données</code> </p> </td> 
   <td colname="col2"> <p>Nom du propriétaire de la source de données auquel ce segment appartient. 
     <ul id="ul_D437D149BDBE470489D1DD03CF47841C"> 
      <li id="li_90133644911A49AEB0DB209BCAC8E789">Pour les données propriétaires, il s'agit du nom d'entreprise du client. </li> 
      <li id="li_788AAFCDA9914235830F0440DF9982E5">Pour les données tierces, il s'agit du nom de la société partenaire. </li> 
      <li id="li_F59FD714746E46BEB27FDF6B7245A7D1">Pour les données tierces, il s'agit du nom du partenaire de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dernière concrétisation</code> </p> </td> 
   <td colname="col2"> <p>Heure exacte de la dernière qualification du sujet de données pour ce segment. Le format de date est AAAA-MM-JJ. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> actif</code> </p> </td> 
   <td colname="col2"> <p>Indique si le sujet de données est actuellement qualifié pour ce segment. Returns <code><i>true</i></code> or <code><i>false</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> liens </code> </p> </td> 
   <td colname="col2"> <p>ID supplémentaire auquel cet ID a été associé. Les informations sont renvoyées sur : </p> <p> 
     <ul id="ul_679F372A83164CC8B6BFE5A833347B9E"> 
      <li id="li_BCBF4F4C6C4049519BDE9186EE84868A">ID </li> 
      <li id="li_46AC081C993041E6BCE70119FE04BE7F">namespace (source de données) </li> 
      <li id="li_E9B906C8947E484B94FBCAEB03BDF4E2">ID de namespace de noms </li> 
      <li id="li_FB2A2F28290B4BA7844A558C01F8D9D4">integration code </li> 
      <li id="li_2569982810B64F8AABD78F5AC3717971">nom du fournisseur de données </li> 
      <li id="li_2A3C282279064373BF7E4619A63454CF">Type d’ID </li> 
     </ul> </p> <p>Tous ces champs sont décrits dans les premières lignes de ce tableau. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> liaison de datetime</code> </p> </td> 
   <td colname="col2"> <p>Heure exacte à laquelle un événement de synchronisation des identifiants a effectué le lien entre les identifiants. Le format de date est AAAA-MM-JJ. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> métadonnées de périphérique </code> </p> </td> 
   <td colname="col2"> <p>Informations sur le périphérique. Ces informations comprennent les champs ci-dessous. Notez que tous les champs ne sont pas renvoyés pour tous les types de périphériques. </p> <p> 
     <ul id="ul_F0031D50DF074634A428DBC73F958159"> 
      <li id="li_4E26042A6B8D4397829F30B7BC7A2D6E"> <p>Informations matérielles </p> </li> 
      <li id="li_99A049D585A9440EA79F57A3B03181AB"> <p>Fabricant du périphérique </p> </li> 
      <li id="li_290F92FC3F6449EFBC4E7870B62AFE8B"> <p>Nom marketing du périphérique </p> </li> 
      <li id="li_FC37954CE133471398352240A8B0478F"> <p>Le modèle de périphérique </p> </li> 
      <li id="li_D54AEB0527C34E32A8AEEAEDEA5AD1B2"> <p>Le nom du système d'exploitation du périphérique (système d'exploitation) </p> </li> 
      <li id="li_0B343C4599344E1791B35A56EBBDC567"> <p>Version du système d'exploitation </p> </li> 
      <li id="li_634B391D95104C42A43D6EFA95F3C0D3"> <p>Fournisseur de périphérique </p> </li> 
     </ul> </p> <p> <p>Remarque : Nous retournons uniquement les métadonnées de périphérique lorsque vous envoyez l'un des éléments suivants : 
      <ul id="ul_2692AF4D28DB44FEAF5F657397F58D32"> 
       <li id="li_FBA2446BB5914772AF24D12B32D9DF1B">ID mobiles </li> 
       <li id="li_FBC45D16DEFE49CF91A7A541402A3BF3">Identifiants Audience Manager </li> 
       <li id="li_2051AA94B53049DEA26654E79ED8FF2A">Identifiants Experience Cloud </li> 
      </ul> </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Supprimer des données {#delete-data}

Nous comprenons votre engagement à respecter vos demandes de clients GDPR dans les 30 jours qui suivent leur réception. C'est pourquoi nous tentons de traiter votre demande de suppression des données dès que possible.

**Demande**

Vous pouvez enregistrer des requêtes de suppression de données dans l'interface utilisateur des services client **[GDPR](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** ou en appelant l'API **[GDPR](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)** (voir `delete` action). Dans tous les cas, vous devez télécharger un fichier JSON avec les identificateurs Audience Manager pour lesquels vous envoyez la demande d'accès aux données. Découvrez à quoi ressemble un JSON bien formé dans la documentation d ['Experience Cloud GDPR](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) (en particulier, recherche dans la page pour « FORMAT DE DEMANDE POST »). Vous **[pouvez également télécharger un exemple de fichier JSON](assets/delete_request.json)**.

**Réponse**

En réponse aux demandes de suppression de données, nous supprimons des caractéristiques et des segments associés à l'identifiant Audience Manager correspondant. En outre, les identifiants Audience Manager respectifs pour le sujet de données seront définitivement exclus d'une collecte de données supplémentaire par Audience Manager et les mappages d'ID correspondants seront supprimés. Lorsque des ID déclarés tels que des identifiants CRM ou des identifiants de cookie client sont envoyés dans des requêtes GDPR, Audience Manager effectue les actions de suppression nécessaires sur tous les périphériques liés (jusqu'à 100 périphériques par ID déclarés).

## Demande d'exclusion {#opt-out-request}

Pour les demandes d'exclusion, reportez-vous à notre documentation sur [la gestion des exclusions](../../overview/data-security-and-privacy/opt-out-management.md).

## Identifiants d'Audience Manager (ID) {#aam-ids}

Lors de l'envoi des requêtes GDPR à Adobe Audience Manager, vous devez inclure l'un des identifiants (ID) répertoriés ci-dessous. Vous trouverez plus d'informations sur les formats d'ID dans l ['index des identifiants d'Audience Manager](../../reference/ids-in-aam.md).

### Utilisateur unique d'Adobe Audience Manager - id

**Utilisateur - id**: aam_ uuid

**Définition**: Utilisateur unique d'Adobe Audience Manager - id

**ID d'espace de noms**: 0

>[!NOTE]
>
>Vous pouvez également utiliser l'namespace de noms CORE. Voir le deuxième exemple JSON.

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

**Utilisateur - id**: mid

**Définition**: Adobe Experience Cloud ID, anciennement appelé Identifiant visiteur ou Marketing Cloud ID

**ID d'espace de noms**: 4

>[!NOTE]
>
>Vous pouvez également utiliser l'namespace de noms ECID. Voir le deuxième exemple JSON.

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

**Utilisateur - id**: cid

**Définition**: ID de client, par exemple un cookie que vous définissez pour les visiteurs anonymes du site ou un identifiant de gestion de la relation client à partir d'un système hors ligne ou d'un nom d'utilisateur haché

**ID d'espace de noms**: Spécifique au client. Veuillez la trouver depuis votre instance Audience Manager.

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

### Identifiant de publicité mobile

**Utilisateur - id**: d_ cid

**Définition**: Identifiants de publicité mobile.
>[!IMPORTANT]
>
> Si vous utilisez le SDK Mobile, vous devez ensuite envoyer l'identifiant d'expérience (MID) avec les identifiants de publicité mobile pour obtenir des réponses GDPR complètes et supprimer des réponses.

**ID d’espace de noms**:

* IDFA : 20915
* GAID : 20914

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

### Code d'intégration

**Utilisateur - id**: d_ cid_ ic

**Définition**: Code d'intégration pour la source de données. Cette option peut être utilisée à la place de l'ID de source de données/ID de l'namespace de noms dans la demande d'API vers le service principal de confidentialité Adobe Experience Cloud.

**ID d'espace de noms**: Non applicable

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
