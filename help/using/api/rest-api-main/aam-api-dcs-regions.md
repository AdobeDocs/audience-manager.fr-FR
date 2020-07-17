---
description: Méthodes permettant d’liste par programmation des régions DCS d’Audience Manager.
seo-description: Méthodes permettant d’liste par programmation des régions DCS d’Audience Manager.
seo-title: Méthodes d’API de région DCS
solution: Audience Manager
title: Méthodes d’API de région DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 14%

---


# Méthodes d’API de région DCS {#dcs-region-api-methods}

Méthodes qui vous permettent d’liste par programmation [!DNL DCS] des régions d’Audience Manager.

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Liste d’une région DCS spécifique {#list-specific-dcs-region}

Méthode `GET` de liste d’une [!DNL DCS] région spécifique.

<!-- r_rest_api_regions_list_specific.xml -->

### Demande

`GET /v1/dcs-regions/`*`<id>`*

### Exemple de réponse

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

Renvoie `200 OK` en cas de réussite.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Régions DCS Liste {#list-dcs-regions}

Méthode `GET` de liste des [!DNL DCS] régions.

<!-- r_rest_api_regions_list.xml -->

### Demande

`GET /v1/dcs-regions/`

### Exemple de réponse

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

Renvoie `200 OK` en cas de réussite.

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
