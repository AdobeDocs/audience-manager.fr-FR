---
description: Méthodes qui permettent de répertorier par programmation les régions DCS d’Audience Manager.
seo-description: Méthodes qui permettent de répertorier par programmation les régions DCS d’Audience Manager.
seo-title: Méthodes d’API de région DCS
solution: Audience Manager
title: Méthodes d’API de région DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 15%

---

# Méthodes d’API de région DCS {#dcs-region-api-methods}

Méthodes qui permettent de répertorier par programmation les régions d’Audience Manager [!DNL DCS].

<!-- c_rest_api_regions.xml -->

Pour obtenir la liste des régions et de leurs nombres entiers correspondants, voir [Identifiants de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Liste d’une région DCS spécifique {#list-specific-dcs-region}

Une méthode `GET` pour répertorier une région [!DNL DCS] spécifique.

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

Pour obtenir la liste des régions et de leurs nombres entiers correspondants, voir [Identifiants de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Liste des régions DCS {#list-dcs-regions}

Une méthode `GET` pour répertorier les régions [!DNL DCS].

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

Pour obtenir la liste des régions et de leurs nombres entiers correspondants, voir [Identifiants de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
