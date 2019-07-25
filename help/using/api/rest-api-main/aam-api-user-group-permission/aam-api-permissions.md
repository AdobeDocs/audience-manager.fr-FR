---
description: Méthodes API REST pour gérer les autorisations pour les objets et les groupes.
seo-description: Méthodes API REST pour gérer les autorisations pour les objets et les groupes.
seo-title: Méthodes de l'API Gestion des permissions
solution: Audience Manager
title: Méthodes de l'API Gestion des permissions
uuid: 111 d 0 f 92-d 92 c -4 d 4 b-b 0 d 6-10 dd 3 fa 466 ad
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Permissions Management API Methods {#permissions-management-api-methods}

Rest [!DNL API] methods to manage permissions for objects and groups.

<!-- c_rest_api_perm_man.xml -->

## List Available Object Types {#list-object-types}

`GET` Méthode permettant de répertorier les types d'objet disponibles sur lesquels les contrôles d'accès basés sur un rôle peuvent être définis.

<!-- r_rest_api_perm_list.xml -->

### Demande

`GET /api/v1/permissionable-object-types/`

### Réponse

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## List Available Permissions for an Object Type {#list-permissions-object-type}

`GET` Méthode permettant de répertorier les autorisations disponibles pour un type d'objet.

<!-- r_rest_api_perm_list_perms.xml -->

### Demande

`GET /api/v1/permissionable-object-types/SEGMENT/`

### Réponse

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>Les types d'objet TAGS et les signaux dérivés n'ont pas d'autorisations normales à utiliser. Les commandes de ces types d'objet sont uniquement modifiées par les autorisations de caractères génériques ou de caractères génériques.