---
description: Méthode GET qui renvoie la destination pour l’ID de destination spécifié.
seo-description: Méthode GET qui renvoie la destination pour l’ID de destination spécifié.
seo-title: Renvoi d’une destination par un identifiant de destination
solution: Audience Manager
title: Renvoi d’une destination par un identifiant de destination
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 9%

---


# Renvoi d’une destination par un identifiant de destination {#return-a-destination-by-destination-id}

Méthode `GET` qui renvoie la destination pour le `destinationId`champ spécifié.

<!-- r_get_all_destinations_order_id.xml -->

## Demande

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>Pour remplir le `mappings` champ transmis `includeMappings=true` dans l’URL.

## Réponse

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## Renvoyer toutes les destinations {#return-all-destinations}

Méthode `GET` qui renvoie toutes les destinations pour le partenaire spécifié.

<!-- r_get_all_destinations.xml -->

### Demande

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(Facultatif)* Transmettez- `containsSegment=<sid>` le pour renvoyer un tableau de toutes les destinations mises en correspondance avec le segment spécifié. Par exemple, votre requête peut ressembler à ceci : `GET .../destinations/?containsSegment=4321`.
   >
   >
* Ne renvoie pas l’objet de destination complet. Obtenez la destination par ordre de données si vous avez besoin d’un objet entièrement renseigné.


### Paramètres de Requête facultatifs

Vous pouvez utiliser ces paramètres facultatifs avec des méthodes d’API qui renvoient *toutes les* propriétés d’un objet. Définissez ces options dans la chaîne de requête lors de la transmission de cette requête à la [!DNL API]. Voir Paramètres [](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters)facultatifs.

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td>
   <td colname="col2"> Renvoie les résultats par numéro de page. débuts de numérotation à 0. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td>
   <td colname="col2"> Définit le nombre de résultats de réponse renvoyés par la requête (10 est la valeur par défaut). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td>
   <td colname="col2">Trie et renvoie les résultats selon la propriété <span class="keyword"> JSON</span> spécifiée. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Trie et renvoie les résultats dans l’ordre décroissant. Ascendant est défini par défaut. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Renvoie des résultats basés sur la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Supposons, par exemple, que vous souhaitiez trouver des résultats pour tous les modèles qui contiennent le mot "Test" dans l’un des champs de valeur de cet élément. Votre exemple de demande peut se présenter comme suit : <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>Vous pouvez rechercher n’importe quelle valeur renvoyée par une méthode "get all". </p> </td>
  </tr>
 </tbody>
</table>

### Réponse

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## Renvoyer un mappage de destination avec l’ID de mappage {#return-dest-mapping-id}

Méthode `GET` qui renvoie un mappage de destination individuel basé sur le `mappingId`.

<!-- r_get_destination_trait_data_order.xml -->

### Demande

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`*`<destinationMappingId>`*

### Réponse

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## Correspondances de destination de retour {#return-dest-mappings}

Méthode `GET` qui renvoie les mappages pour une destination.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>Le mappage renvoyé est spécifique au type et à la configuration de destination.

### Demande

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings`

>[!NOTE]
>
>Prend en charge les paramètres de pagination.

### Réponse

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## Renvoyer toutes les plates-formes de destination disponibles {#return-dest-platforms}

Méthode `GET` qui renvoie toutes les plates-formes de périphériques disponibles pour les destinations.

<!-- r_get_dest_platforms.xml -->

### Demande

`GET /destinations/configurations/available-platforms/`

### Réponse

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Retourner l&#39;historique des tâches de destination S2S et S2S en bloc {#return-job-history}

Méthode `GET` qui renvoie des informations relatives à l’historique des tâches sortantes [!UICONTROL Server-to-Server] ( [!UICONTROL S2S]) et de [!UICONTROL S2S] destination en bloc.

<!-- r_get_job_history.xml -->

### Demande

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Paramètres de requête requis : `startDate` = *&lt;`epochtime`>* et `endDate` = *&lt;`epochtime`>*.

### Réponse

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```
