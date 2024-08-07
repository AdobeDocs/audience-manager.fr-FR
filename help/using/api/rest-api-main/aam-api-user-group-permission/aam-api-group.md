---
description: Méthodes d’API REST pour gérer les groupes, notamment créer, mettre à jour, répertorier et supprimer des groupes.
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: Méthodes d’API de gestion des groupes
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 5%

---

# Méthodes d’API de gestion des groupes {#group-management-api-methods}

Redéfinissez les méthodes [!DNL API] pour gérer les groupes, notamment créer, mettre à jour, répertorier et supprimer des groupes.

<!-- c_rest_api_user_man_group.xml -->

## Création d’un groupe {#create-group}

Méthode `POST` pour créer un groupe d’utilisateurs.

<!-- r_rest_api_group_create.xml -->

### Requête

`POST /api/v1/groups/`

### Exemple de corps de requête

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Réponse

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Mise à jour d’un groupe {#update-group}

Une méthode `PUT` pour mettre à jour un groupe d’utilisateurs.

<!--
r_rest_api_group_update.xml
-->

### Requête

`PUT /api/v1/groups/`*`<groupId>`*

### Exemple de corps de requête

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Réponse

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Groupes de listes {#list-groups}

Une méthode `GET` pour répertorier les groupes d’utilisateurs.

<!--
r_rest_api_group_list.xml
-->

### Requête

`GET /api/v1/groups/`

### Réponse

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## Suppression d’un groupe {#delete-groups}

Méthode `DELETE` pour supprimer un groupe d’utilisateurs et supprimer tous les membres de ce groupe.

<!-- r_rest_api_group_delete.xml -->

### Requête

`DELETE /api/v1/groups/`*`<groupId>`*

Renvoie `204 No Content` en cas de réussite. En cas de conflit, renvoie `409 Conflict`.

## Suppression de groupes en bloc {#delete-groups-bulk}

Une méthode `DELETE` pour supprimer plusieurs groupes en bloc et supprimer tous les membres de ce groupe.

<!-- r_rest_api_group_delete_bulk.xml -->

### Requête

`DELETE /api/v1/groups/bulk-delete`

Renvoie `204 No Content` en cas de réussite. En cas de conflit, renvoie `409 Conflict`.

## Répertorier toutes les autorisations d’un groupe {#list-permissions-group}

Une méthode `GET` pour répertorier les objets d’autorisation sur un groupe.

<!-- r_rest_api_perm_list_group.xml -->

### Requête

`GET /api/v1/groups/{groupId}/permissions`

### Réponse

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

Renvoie `400 Bad Request` si le groupe n’est pas accessible.

## Définition des autorisations d’un groupe {#set-permissions-group}

Une méthode `PUT` pour mettre à jour les autorisations de groupe. Cette méthode remplace les anciennes autorisations par les nouvelles autorisations.

<!-- r_rest_api_perm_set.xml -->

### Requête

`PUT /api/v1/groups/{groupId}/permissions/`

### Réponse

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

L’exemple de réponse représente la liste mise à jour des objets d’autorisation.

Renvoie `200 OK` en cas de réussite. Renvoie `400` si une autorisation donnée n&#39;est pas valide. Peut également renvoyer `403` si l’objet n’est pas accessible pour l’utilisateur connecté.
