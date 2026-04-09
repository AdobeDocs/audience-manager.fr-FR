---
description: Méthodes vous permettant de répertorier par programmation les régions Audience Manager DCS.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: Méthodes d’API de la région DCS
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
TQID: https://experienceleague.adobe.com/ipsOlq24Y00SHvGKgUFJHnRQ11DZIuDNY76D5LCAgso
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: d8f681b8-67cc-42dc-85c5-a0977528a942
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 110
ht-degree: 3%

---

# Méthodes d’API de la région DCS {#dcs-region-api-methods}

Méthodes vous permettant de répertorier par programmation les régions Audience Manager [!DNL DCS].

<!-- c_rest_api_regions.xml -->

Pour obtenir la liste des régions et leurs entiers correspondants, voir [ID de région, emplacements et noms d’hôte du serveur de collecte de données](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Liste d’une région DCS spécifique {#list-specific-dcs-region}

Méthode `GET` pour répertorier une région [!DNL DCS] spécifique.

<!-- r_rest_api_regions_list_specific.xml -->

### Requête

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

Pour obtenir la liste des régions et leurs entiers correspondants, voir [ID de région, emplacements et noms d’hôte du serveur de collecte de données](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Liste des régions DCS {#list-dcs-regions}

Une méthode `GET` pour répertorier les régions [!DNL DCS].

<!-- r_rest_api_regions_list.xml -->

### Requête

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

Pour obtenir la liste des régions et leurs entiers correspondants, voir [ID de région, emplacements et noms d’hôte du serveur de collecte de données](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
