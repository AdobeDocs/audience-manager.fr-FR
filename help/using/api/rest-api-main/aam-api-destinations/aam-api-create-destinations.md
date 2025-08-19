---
description: Créez des destinations avec ces méthodes d’API RESTful.
seo-description: Create destinations with these RESTful API methods.
seo-title: Create Destinations
solution: Audience Manager
title: Création de destinations
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
exl-id: bae0f304-0ff3-4c5f-b432-19aef61d9d10
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 6%

---

# Création de destinations {#create-destinations}

Créez des destinations avec ces méthodes de [!UICONTROL RESTful API].

<!-- c_create_destinations.xml -->

## Types de destination pris en charge : URL et cookie uniquement

Les méthodes de `POST` disponibles vous permettent de créer des [!UICONTROL URL] et des [!UICONTROL cookie destinations] uniquement. Actuellement, vous ne pouvez pas créer de [!UICONTROL server-to-server destinations] avec ces méthodes de [!DNL REST API]. Toutefois, les méthodes de `GET` de destination associées vous permettent de récupérer des informations sur les [!UICONTROL server-to-server destinations] créées dans l’interface utilisateur.

## Création d’une destination d’URL non série {#create-nonserial-dest}

Une méthode `POST` qui vous permet de créer une destination qui accepte les segments composés de paires clé-valeur uniques (par exemple, `gender=male` ou `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### Requête

`POST https://api.demdex.com/v1/destinations/`

### Exemple de requête

Cette requête crée une destination unique. Toutes les valeurs de requête sont requises, sauf indication contraire.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Réponse

Une requête réussie renvoie `201 created` et la destination.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 
```

## Créer une destination d’URL sérialisée {#create-serial-url-dest}

Une méthode `POST` qui vous permet de créer une destination qui accepte plusieurs valeurs associées à une seule clé (par exemple, `color=blue, red, green`).

<!-- r_create_serial_url_destination.xml -->

### Requête

`POST https://api.demdex.com/v1/destinations/`

### Exemple de requête

Spécifiez le [!DNL URL] sécurisé et le délimiteur pour la paire clé-valeur transmise à la destination. Toutes les valeurs de requête sont requises, sauf indication contraire.

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### Réponse

Une mise à jour réussie renvoie le code de réponse `201 created` et la destination.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

## Création d’une destination de cookie : clé unique, non sérialisée {#create-cookie-dest-single}

Une méthode `POST` qui vous permet de créer une [!UICONTROL cookie destination] qui accepte les segments composés de paires clé-valeur uniques (par exemple, `gender=male` ou `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### Requête

`POST https://api.demdex.com/v1/destinations/`

### Exemple de requête

Toutes les valeurs de requête sont requises, sauf indication contraire.

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### Réponse

Une mise à jour réussie renvoie le code de réponse `201 created` et la destination.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false
} 
```

## Création d’une destination de cookie : clé unique, sérialisée {#create-cookie-dest-single-serial}

Une méthode `POST` qui vous permet de créer une destination qui accepte plusieurs valeurs associées à une seule clé (par exemple, `color=blue, red, green`).

<!-- r_cookie_destination_singlekey_serial.xml -->

### Requête

`POST https://api.demdex.com/v1/destinations/`

### Exemple de requête

Toutes les valeurs de requête sont requises, sauf indication contraire.

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Réponse

Une mise à jour réussie renvoie le code de réponse `201 created` et la destination.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

## Création d’une destination de cookie : multi-clé, non sérialisée {#create-cookie-dest-multi}

Une méthode `POST` qui vous permet de créer une destination qui accepte des segments contenant plusieurs clés avec des valeurs différentes (par exemple, `gender=male; gender=female; color=blue; color=red`).

<!-- r_create_cookie_multikey_noserial.xml -->

### Requête

`POST https://api.demdex.com/v1/destinations/`

### Exemple de requête

Toutes les valeurs de requête sont requises, sauf indication contraire.

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### Réponse

Une mise à jour réussie renvoie le code de réponse `201 created` et la destination.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## Création d’une destination de cookie : multi-clé, sérialisé {#create-cookie-dest-multi-serial}

Une méthode `POST` qui vous permet de créer une destination qui accepte des segments contenant plusieurs clés et valeurs (par exemple, `gender=male, female; color=blue, red, green`).

<!-- r_cookie_destination_multikey_serial.xml -->

### Requête

`POST https://api.demdex.com/v1/destinations/`

### Exemple de requête

Toutes les valeurs de requête sont requises, sauf indication contraire.

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains",
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Réponse

Une mise à jour réussie renvoie le code de réponse `201 created` et la destination.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORELIKETHIS]
>
>* [Destinations](../../../features/destinations/destinations.md)
>* [Sérialisation de destination](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Explication des paires clé-valeur](../../../reference/key-value-pairs-explained.md)
