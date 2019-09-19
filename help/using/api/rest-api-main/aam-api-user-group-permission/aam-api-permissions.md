---
description: Méthodes de l’API REST pour gérer les autorisations des objets et des groupes.
seo-description: Méthodes de l’API REST pour gérer les autorisations des objets et des groupes.
seo-title: Méthodes de l’API de gestion des autorisations
solution: Audience Manager
title: Méthodes de l’API de gestion des autorisations
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Méthodes de l’API de gestion des autorisations {#permissions-management-api-methods}

Redéfinissez [!DNL API] les méthodes de gestion des autorisations pour les objets et les groupes.

<!-- c_rest_api_perm_man.xml -->

## Liste des types d’objets disponibles {#list-object-types}

Méthode `GET` permettant de répertorier les types d’objet disponibles sur lesquels des contrôles d’accès basés sur les rôles peuvent être définis.

<!-- r_rest_api_perm_list.xml -->

### Demande

`GET /api/v1/permissionable-object-types/`

### Réponse

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Répertorier les autorisations disponibles pour un type d’objet {#list-permissions-object-type}

Méthode `GET` permettant de répertorier les autorisations disponibles pour un type d’objet.

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
>Les types d’objet TAGS et DERIVED SIGNALS n’ont pas d’autorisations régulières à utiliser. Les contrôles de ces types d’objets sont modifiés uniquement par les autorisations de carte générique Tout ou Rien.