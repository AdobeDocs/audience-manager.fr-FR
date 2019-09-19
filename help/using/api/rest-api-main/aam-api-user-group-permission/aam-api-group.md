---
description: Méthodes de l’API REST pour gérer les groupes, y compris la création, la mise à jour, la liste et la suppression de groupes.
seo-description: Méthodes de l’API REST pour gérer les groupes, y compris la création, la mise à jour, la liste et la suppression de groupes.
seo-title: Méthodes de l'API Gestion des groupes
solution: Audience Manager
title: Méthodes de l'API Gestion des groupes
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Méthodes de l'API Gestion des groupes {#group-management-api-methods}

Méthodes [!DNL API] de test pour gérer les groupes, y compris la création, la mise à jour, la liste et la suppression de groupes.

<!-- c_rest_api_user_man_group.xml -->

## Création d’un groupe {#create-group}

Méthode `POST` permettant de créer un groupe d’utilisateurs.

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

## Mettre à jour un groupe {#update-group}

Méthode `PUT` de mise à jour d’un groupe d’utilisateurs.

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

## Groupes de listes {#list-groups}

Méthode `GET` permettant de répertorier les groupes d’utilisateurs.

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

Méthode `DELETE` permettant de supprimer un groupe d’utilisateurs et tous les membres de ce groupe.

<!-- r_rest_api_group_delete.xml -->

### Demande

`DELETE /api/v1/groups/`*`<groupId>`*

Renvoie `204 No Content` en cas de réussite. En cas de conflit revient `409 Conflict`.

## Suppression de groupes en bloc {#delete-groups-bulk}

Méthode `DELETE` permettant de supprimer plusieurs groupes en bloc et de supprimer tous les membres de ce groupe.

<!-- r_rest_api_group_delete_bulk.xml -->

### Demande

`DELETE /api/v1/groups/bulk-delete`

Renvoie `204 No Content` en cas de réussite. En cas de conflit revient `409 Conflict`.

## Répertorier toutes les autorisations d’un groupe {#list-permissions-group}

Méthode `GET` permettant de répertorier les objets d’autorisation d’un groupe.

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

Renvoie `400 Bad Request` si le groupe est inaccessible.

## Set Permissions for a Group {#set-permissions-group}

Méthode `PUT` de mise à jour des autorisations de groupe. Cette méthode remplace les anciennes autorisations par les nouvelles autorisations.

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

L’exemple de réponse représente la liste mise à jour des objets d’autorisation.

Renvoie `200 OK` en cas de réussite. Renvoie `400` si une autorisation donnée n’est pas valide. Peut également renvoyer `403` si l’objet n’est pas accessible à l’utilisateur connecté.