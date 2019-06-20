---
description: Méthode GET qui renvoie la destination pour l'DESTINATIONID destinationid spécifié.
seo-description: Méthode GET qui renvoie la destination pour l'DESTINATIONID destinationid spécifié.
seo-title: Renvoyer une destination par ID de destination
solution: Audience Manager
title: Renvoyer une destination par ID de destination
uuid: abce 7426-55 a 5-4045-93 a 7-0487652 a 7189
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Return A Destination by Destination ID {#return-a-destination-by-destination-id}

`GET` Méthode qui renvoie la destination de la valeur spécifiée `destinationId`.

<!-- r_get_all_destinations_order_id.xml -->

## Demande

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>To populate the `mappings` field pass in `includeMappings=true` in the URL.

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

## Return All Destinations {#return-all-destinations}

`GET` Méthode qui renvoie toutes les destinations pour le partenaire spécifié.

<!-- r_get_all_destinations.xml -->

### Demande

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(Facultatif)* `containsSegment=<sid>` Transférez le tableau de toutes les destinations associées au segment spécifié. For example, your query could look similar to this: `GET .../destinations/?containsSegment=4321`.
   >
   >
* Ne renvoie pas l&#39;objet de destination complet. Obtenez la destination par ordre de données si vous avez besoin d&#39;un objet entièrement renseigné.


### Paramètres de requête facultatifs

You can use these optional parameters with API methods that return *all* properties for an object. Set these options in the request string when passing that query in to the [!DNL API]. See [Optional Parameters](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2"> Renvoie les résultats par numéro de page. La numérotation commence à 0. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> Pagesize</code> </td>
   <td colname="col2"> Définit le nombre de résultats de réponse renvoyés par la requête (10 est par défaut). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> Sortby</code> </td>
   <td colname="col2">Sorts and returns results according to the specified <span class="keyword"> JSON</span> property. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> décroissant</code> </td>
   <td colname="col2"> Trie et renvoie les résultats par ordre décroissant. L'ordre croissant est par défaut. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> recherche</code> </td>
   <td colname="col2">Renvoie les résultats en fonction de la chaîne spécifiée que vous souhaitez utiliser comme paramètre de recherche. Par exemple, supposons que vous souhaitiez obtenir des résultats pour tous les modèles qui contiennent le mot « Test » dans l'un des champs de valeur de cet élément. Voici un exemple de demande : <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>Vous pouvez rechercher une valeur renvoyée par une méthode « get all ». </p> </td>
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

## Return a Destination Mapping With the Mapping ID {#return-dest-mapping-id}

`GET` Méthode qui renvoie un mappage de destination individuel basé `mappingId`sur le paramètre.

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

## Return Destination Mappings {#return-dest-mappings}

`GET` Méthode qui renvoie les correspondances d&#39;une destination.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>Le mappage renvoyé est spécifique au type de destination et à la configuration.

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

## Return All Available Destination Platforms {#return-dest-platforms}

`GET` Méthode qui renvoie toutes les plateformes de périphérique disponibles pour les destinations.

<!-- r_get_dest_platforms.xml -->

### Demande

`GET /destinations/configurations/available-platforms/`

### Réponse

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Return S2S and Bulk S2S Destination Job History {#return-job-history}

`GET` Méthode qui renvoie les informations [!UICONTROL Server-to-Server] d&#39;historique [!UICONTROL S2S]des tâches [!UICONTROL S2S] de destination () et de destination en masse.

<!-- r_get_job_history.xml -->

### Demande

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Required query parameters: `startDate` = *&lt;`epochtime`&gt;* and `endDate` = *&lt;`epochtime`&gt;*.

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
