---
description: Ce document décrit les technicônes relatives au GDPR (General Data Protection Regulation) pour Audience Manager et explique comment envoyer des demandes GDPR à Audience Manager.
seo-description: Ce document décrit les technicônes relatives au GDPR (General Data Protection Regulation) pour Audience Manager et explique comment envoyer des demandes GDPR à Audience Manager.
seo-title: RGPD dans Audience Manager
solution: Audience Manager
title: RGPD dans Audience Manager
uuid: ed 23 a 478-32 be -460 d-bb 03-a 735317 f 7 c 0 f
translation-type: tm+mt
source-git-commit: b791e22e9c8c848a8fc14c6d6494f77c9e7335dc

---


# RGPD dans Audience Manager{#gdpr-in-audience-manager}

Ce document décrit les technicônes relatives au GDPR (General Data Protection Regulation) pour Audience Manager et explique comment envoyer des demandes GDPR à Audience Manager.

## GDPR Documentation in the Experience Cloud {#gdpr-documentation}

Avant de lire les détails d&#39;Audience Manager, nous vous conseillons d&#39;utiliser le matériel Experience Cloud pour le GDPR (European General Data Protection Regulation), lié ci-dessous :

* [GDPR et votre entreprise](https://www.adobe.com/privacy/general-data-protection-regulation.html)
* [Livre blanc GDPR](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-whitepaper.md)
* [Terminologie relative au règlement général sur la protection des données (RGPD)](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/gdpr-terminology.md)

Les sections ci-dessous décrivent ce que signifie le GDPR pour Audience Manager et comment vous pouvez envoyer des demandes GDPR à Audience Manager.

## Types of GDPR Requests and How to Make a GDPR Request {#types-of-gdpr-requests}

As an Audience Manager customer, you can submit individual GDPR requests to access and delete customer data, either through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)**. You can submit any Audience Manager identifiers (IDs), as described in the section **[Audience Manager Identifiers](../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids)**, in the requests along with their respective namespace IDs (data source IDs). Pour toute question, contactez le service d&#39;assistance clientèle à l&#39;adresse gdprsupport@adobe.com.

## Accéder aux données {#access-data}

Nous comprenons votre engagement à respecter vos demandes de clients GDPR dans les 30 jours qui suivent leur réception. C&#39;est pourquoi nous tentons de traiter votre demande d&#39;accès aux données dès que possible.

**Demande**

You can log data access requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `access` action). Dans tous les cas, vous devez télécharger un fichier JSON avec les identificateurs Audience Manager pour lesquels vous envoyez la demande d&#39;accès aux données. See what a well-formed JSON looks like in the **[Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (specifically, search in page for &quot;POST request format&quot;). Or, you can **[download a sample JSON](assets/access_request.json)**.

**Réponse**

Les réponses à l&#39;accès aux requêtes de données contiennent un résumé du nombre total de caractéristiques et de segments, du type de caractéristique, des descriptions des caractéristiques et des segments ainsi que des noms de source de données correspondants. La réponse Accès comprend également des données tierces et tierces accessibles au contrôleur de données, ainsi que les données propriétaires. When [!UICONTROL declared IDs] such as cross device CRM IDs or customer cookie IDs are sent in GDPR requests, Audience Manager will include the Access response from all the linked devices (up to 100 devices per declared ID).

**État de la réponse**

S&#39;il existe des erreurs d&#39;Audience Manager dans la réponse, elles sont affichées comme des codes d&#39;erreur dans la réponse. We have a [list of error codes](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md), where you can find more information about the returned errors.

**Exemple de réponse**

Une réponse d&#39;accès peut ressembler à celle ci-dessous. Dans cet exemple, l&#39;ID du sujet de données est un identifiant de cookie. Ils sont qualifiés pour plusieurs caractéristiques et appartiennent à quelques segments. L&#39;ID de cookie est lié à un ID mobile. L&#39;exemple contient également des métadonnées pour le smartphone qu&#39;elles utilisent.

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

Le tableau ci-dessous contient des descriptions pour tous les champs renvoyés dans la réponse d&#39;accès aux données, dans l&#39;ordre dans lequel ils apparaissent ci-dessus.

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
   <td colname="col2"> <p>Utilisateur - id pour les données qui suivent. Il s'agit soit d'un ID fourni dans la demande d'accès aux données GDPR, soit d'un ID lié à l'un des ID déclarés que vous avez fournis. The ID types are described in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace</code> </p> </td> 
   <td colname="col2"> <p>Également appelé source de données. See the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> id</code> </p> </td> 
   <td colname="col2"> <p>L’ID de l’espace de noms/la source de données. See <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers (IDs)</a> for all the accepted values. </p> </td> 
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
   <td colname="col2"> <p>Le type d’ID pour lequel vous avez demandé l’accès aux données en vertu du RGPD. Accepted types are listed in the <a href="../../overview/aam-gdpr/aam-gdpr-details.md#aam-ids"> Audience Manager Identifiers</a> section. </p> </td> 
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
      <li id="li_D9354F40FD114802819191450F2375C8"> <i>Tiers</i> pour les caractéristiques qui appartiennent à vos partenaires. Read our <a href="../../overview/data-types-collected.md#second-party-data"> Second Party Data</a> article for more information. </li> 
      <li id="li_C321D8B8256F4102AE64CD40DC57C948"> <i>Tiers</i> pour les caractéristiques obtenues auprès des partenaires de données, via <a href="../../features/audience-marketplace/audience-marketplace.md"> Audience Marketplace</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> description</code> </p> </td> 
   <td colname="col2"> <p>Quelques mots pour décrire la finalité ou la fonction de la caractéristique. Il s'agit d'un champ facultatif. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> contrôles d'exportation de données</code> </p> </td> 
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this trait's data source. </p> </td> 
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
   <td colname="col2"> <p>The <a href="../../features/data-export-controls.md"> data export controls</a> applied to this segment's data source. </p> </td> 
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

Nous comprenons votre engagement à respecter vos demandes de clients GDPR dans les 30 jours qui suivent leur réception. C&#39;est pourquoi nous tentons de traiter votre demande de suppression des données dès que possible.

**Demande**

You can log data deletion requests through the **[GDPR Client Services UI](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/using-gdpr-ui.md)** or by calling the **[GDPR API](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md)** (see `delete` action). Dans tous les cas, vous devez télécharger un fichier JSON avec les identificateurs Audience Manager pour lesquels vous envoyez la demande d&#39;accès aux données. See what a well-formed JSON looks like in the [Experience Cloud GDPR documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) (specifically, search in page for &quot;POST request format&quot;). Or, you can **[download a sample JSON](assets/delete_request.json)**.

**Réponse**

En réponse aux demandes de suppression de données, nous supprimons des caractéristiques et des segments associés à l&#39;identifiant Audience Manager correspondant. En outre, les identifiants Audience Manager respectifs pour le sujet de données seront définitivement exclus d&#39;une collecte de données supplémentaire par Audience Manager et les mappages d&#39;ID correspondants seront supprimés. Lorsque des ID déclarés tels que des identifiants CRM ou des identifiants de cookie client sont envoyés dans des requêtes GDPR, Audience Manager effectue les actions de suppression nécessaires sur tous les périphériques liés (jusqu&#39;à 100 périphériques par ID déclarés).

## Opt-out Request {#opt-out-request}

For opt-out requests, please refer to our documentation on [Opt-out Management](../../overview/data-security-and-privacy/opt-out-management.md).

## Audience Manager Identifiers (IDs) {#aam-ids}

Lors de l&#39;envoi des requêtes GDPR à Adobe Audience Manager, vous devez inclure l&#39;un des identifiants (ID) répertoriés ci-dessous. You can find more information on the ID formats in our [Index of Audience Manager IDs](../../reference/ids-in-aam.md).

### Utilisateur unique d&#39;Adobe Audience Manager - id

**Utilisateur - id**: aam_ uuid

**Définition**: Utilisateur unique d&#39;Adobe Audience Manager - id

**ID d&#39;espace de noms**: 0

>[!NOTE]
>
>Vous pouvez également utiliser l&#39;namespace de noms CORE. Voir le deuxième exemple JSON.

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

**ID d&#39;espace de noms**: 4

>[!NOTE]
>
>Vous pouvez également utiliser l&#39;namespace de noms ECID. Voir le deuxième exemple JSON.

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

**Définition**: ID de client, par exemple un cookie que vous définissez pour les visiteurs anonymes du site ou un identifiant de gestion de la relation client à partir d&#39;un système hors ligne ou d&#39;un nom d&#39;utilisateur haché

**ID d&#39;espace de noms**: Spécifique au client. Veuillez la trouver depuis votre instance Audience Manager.

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
> Si vous utilisez le SDK Mobile, vous devez ensuite envoyer l&#39;identifiant d&#39;expérience (MID) avec les identifiants de publicité mobile pour obtenir des réponses GDPR complètes et supprimer des réponses.

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

### Code d&#39;intégration

**Utilisateur - id**: d_ cid_ ic

**Définition**: Code d&#39;intégration pour la source de données. Cette option peut être utilisée à la place de l&#39;ID de source de données/ID de l&#39;namespace de noms dans la demande d&#39;API vers le service principal de confidentialité Adobe Experience Cloud.

**ID d&#39;espace de noms**: Non applicable

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
