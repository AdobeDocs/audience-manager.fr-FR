---
description: Faites correspondre les segments aux destinations à l’aide de ces méthodes d’API RESTful.
seo-description: Faites correspondre les segments aux destinations à l’aide de ces méthodes d’API RESTful.
seo-title: Mise en correspondance de segments avec une destination
solution: Audience Manager
title: Mise en correspondance de segments avec une destination
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 11%

---


# Mise en correspondance de segments avec une destination {#map-segments-to-a-destination}

Faites correspondre les segments aux destinations avec ces méthodes [!DNL RESTful API].

<!-- c_api_map_seg_dest.xml -->

## Types de destination pris en charge : URL et cookie uniquement

Les méthodes `POST` disponibles vous permettent de mapper des segments uniquement à [!UICONTROL URL] et [!UICONTROL cookie destinations]. Actuellement, vous ne pouvez pas mapper les segments à [!UICONTROL server-to-server destinations] avec ces méthodes [!DNL REST API]. Utilisez plutôt l’interface utilisateur. Cependant, les méthodes de destination `GET` associées vous permettent de récupérer des informations sur [!UICONTROL server-to-server destinations] créées dans l&#39;interface utilisateur.

## Faire correspondre un segment à une destination URL non sérialisée {#map-segment-non-serial}

Méthode `POST` qui vous permet de mapper un segment à une destination [!UICONTROL URL] non série.

<!-- r_map_noserial_url.xml -->

### Demande

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Exemple de requête

Sauf indication contraire, toutes les valeurs de requête sont requises.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### Réponse

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## Faire correspondre un segment à une destination URL sérialisée {#map-segment-serial}

Méthode `POST` qui vous permet de mapper un segment à une destination [!UICONTROL URL] sérialisée.

<!-- r_map_serialized_url.xml -->

### Demande

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### Exemple de requête

Dans la requête, `traitAlias` correspond à la clé d’une paire clé-valeur. Sauf indication contraire, toutes les valeurs de requête sont requises.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Réponse

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## Faites correspondre un segment à une destination de cookie : Clé unique, non sérialisée {#map-segment-cookie-noserial}

Méthode `POST` qui vous permet de mapper un segment à une destination à clé unique non sérialisée [!UICONTROL cookie].

<!-- r_map_cookie_noserial.xml -->

### Demande

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Exemple de requête

Dans la requête, `valueAlias` correspond à la valeur d’une paire clé-valeur. Sauf indication contraire, toutes les valeurs de requête sont requises.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### Réponse

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## Faites correspondre un segment à une destination de cookie : Multi-clé, non sérialisé {#map-segment-cookie-multi-noserial}

Méthode `POST` qui vous permet de mapper un segment à une destination [!UICONTROL cookie] multi-clé et non sérialisée.

<!-- r_map_cookie_multikey_noserial.xml -->

### Demande

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Exemple de requête

Dans la requête, les valeurs `traitAlias` et `valueAlias` définissent respectivement la clé et la valeur dans une paire clé-valeur. Sauf indication contraire, toutes les valeurs de requête sont requises.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Réponse

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Faites correspondre un segment à une destination de cookie : Multi-clé, sérialisé {#map-segment-cookie-multi-serial}

Méthode `POST` qui vous permet de mapper un segment à un [!UICONTROL cookie destination] multiclé sérialisé.

<!-- r_map_cookie_multikey_serialized.xml -->

### Demande

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Exemple de requête

Dans la requête, les valeurs `traitAlias` et `valueAlias` définissent la clé et la valeur dans une paire clé-valeur. Sauf indication contraire, toutes les valeurs de requête sont requises.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Réponse

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Faire correspondre un segment à une destination serveur à serveur {#map-segment-s2s}

Méthode `POST` qui vous permet de mapper un segment à une destination [!UICONTROL server-to-server] existante. Notez toutefois que vous ne pouvez pas créer de destinations [!UICONTROL server-to-server] avec ces méthodes [!DNL API] actuellement disponibles.

<!-- r_map_segment_s2s.xml -->

### Demande

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Exemple de requête

Dans la requête, `traitAlias` correspond à la clé d’une paire clé-valeur. Sauf indication contraire, toutes les valeurs de requête sont requises.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Réponse

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## Mappages de destination de création en bloc {#bulk-create}

Méthode `POST` qui vous permet de transmettre un tableau de mappages de destination [!UICONTROL cookie] ou [!UICONTROL URL].

<!-- r_bulk_create.xml -->

### Demande

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### Exemple de requête

Sauf indication contraire, toutes les valeurs de requête sont requises.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Réponse

Une réponse réussie renvoie le tableau des mappages créés.

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Ajouter plusieurs segments à une destination {#add-segments-dest}

Méthode `POST` qui vous permet de mapper plusieurs segments à une destination.

<!-- r_add_segments_to_destination.xml -->

### Demande

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### Exemple de requête

Créez plusieurs mappages de destination dans un tableau. Sauf indication contraire, toutes les valeurs de requête sont requises.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Réponse

Renvoie un tableau de mappages créés.

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Mettre à jour une destination par ID de destination {#update-dest-data-order}

Méthode `PUT` qui vous permet de mettre à jour une destination existante par `destinationId`.

<!-- r_update_destination_data_order_id.xml -->

### Demande

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### Exemple de requête

Sauf indication contraire, toutes les valeurs de requête sont requises.

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Réponse

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## Mettre à jour un mappage vers une destination par ID de mappage {#update-mapping-dest-id}

Méthode `PUT` qui vous permet de mettre à jour un mappage vers une destination par le `mappingId` spécifié.

<!-- r_update_destination_trait_data_order_id.xml -->

### Demande

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### Exemple de requête

Sauf indication contraire, toutes les valeurs de requête sont requises.

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### Réponse

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```

>[!MORELIKETHIS]
>
>* [Destinations ](../../../features/destinations/destinations.md)
>* [Sérialisation de destination](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Explication des paires clé-valeur](../../../reference/key-value-pairs-explained.md)

