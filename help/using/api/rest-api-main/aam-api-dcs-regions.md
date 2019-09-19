---
description: Méthodes qui vous permettent de répertorier par programmation les régions DCS d’Audience Manager.
seo-description: Méthodes qui vous permettent de répertorier par programmation les régions DCS d’Audience Manager.
seo-title: Méthodes de l’API de région DCS
solution: Audience Manager
title: Méthodes de l’API de région DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Méthodes de l’API de région DCS {#dcs-region-api-methods}

Méthodes qui vous permettent de répertorier par programmation les [!UICONTROL DCS] régions d’Audience Manager.

<!-- c_rest_api_regions.xml -->

For a list of regions and their corresponding integers, see [DCS Region IDs, Locations, and Host Names](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Répertorier une région spécifique du serveur de collecte de données {#list-specific-dcs-region}

Méthode `GET` permettant de répertorier une [!UICONTROL DCS] région spécifique.

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

## Liste des régions DCS {#list-dcs-regions}

Méthode `GET` permettant de répertorier [!UICONTROL DCS] les régions.

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
