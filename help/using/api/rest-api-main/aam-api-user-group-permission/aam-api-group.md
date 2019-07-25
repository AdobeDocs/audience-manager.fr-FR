---
description: Méthodes API REST pour gérer les groupes, notamment la création, la mise à jour, la liste et la suppression de groupes.
seo-description: Méthodes API REST pour gérer les groupes, notamment la création, la mise à jour, la liste et la suppression de groupes.
seo-title: Méthodes de l'API Gestion des groupes
solution: Audience Manager
title: Méthodes de l'API Gestion des groupes
uuid: fe 042 eb 5-ea 12-42 fe-be 98-d 721 f 987 a 914
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Group Management API Methods {#group-management-api-methods}

Rest [!DNL API] methods to manage groups, including creating, updating, listing, deleting groups.

<!-- c_rest_api_user_man_group.xml -->

## Création d’un groupe {#create-group}

`POST` Méthode de création d'un groupe d'utilisateurs.

<!-- r_rest_api_group_create.xml -->

### Demande

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

## Update a Group {#update-group}

`PUT` Méthode de mise à jour d'un groupe d'utilisateurs.

<!--
r_rest_api_group_update.xml
-->

### Demande

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

## List Groups {#list-groups}

`GET` Méthode permettant de répertorier les groupes d'utilisateurs.

<!--
r_rest_api_group_list.xml
-->

### Demande

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

`DELETE` Méthode permettant de supprimer un groupe d'utilisateurs et de supprimer tous les membres de ce groupe.

<!-- r_rest_api_group_delete.xml -->

### Demande

`DELETE /api/v1/groups/`*`<groupId>`*

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## Delete Groups in Bulk {#delete-groups-bulk}

`DELETE` Méthode permettant de supprimer plusieurs groupes en bloc et de supprimer tous les membres de ce groupe.

<!-- r_rest_api_group_delete_bulk.xml -->

### Demande

`DELETE /api/v1/groups/bulk-delete`

Returns `204 No Content` if successful. In case of conflict returns `409 Conflict`.

## List All Permissions for a Group {#list-permissions-group}

`GET` Méthode permettant de répertorier les objets d'autorisation d'un groupe.

<!-- r_rest_api_perm_list_group.xml -->

### Demande

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

Returns `400 Bad Request` if the group is inaccessible.

## Set Permissions for a Group {#set-permissions-group}

`PUT` Méthode de mise à jour des autorisations de groupe. Cette méthode remplace les anciennes autorisations par les nouvelles autorisations.

<!-- r_rest_api_perm_set.xml -->

### Demande

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

L'exemple de réponse représente la liste mise à jour des objets d'autorisation.

Returns `200 OK` if successful. Returns `400` if any given permission is invalid. Can also return `403` if the object is not accessible by the logged-in user.