---
description: Méthodes de l’API REST pour gérer les autorisations des objets et des groupes
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: Méthodes d’API de gestion des autorisations
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 2%

---

# Méthodes d’API de gestion des autorisations {#permissions-management-api-methods}

Les méthodes Rest [!DNL API] permettent de gérer les autorisations pour les objets et les groupes.

<!-- c_rest_api_perm_man.xml -->

## Répertorier les types d’objets disponibles {#list-object-types}

Une méthode `GET` pour répertorier les types d’objets disponibles sur lesquels les contrôles d’accès basés sur les rôles peuvent être définis.

<!-- r_rest_api_perm_list.xml -->

### Requête

`GET /api/v1/permissionable-object-types/`

### Réponse

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Liste des autorisations disponibles pour un type d’objet {#list-permissions-object-type}

Méthode `GET` pour répertorier les autorisations disponibles pour un type d’objet.

<!-- r_rest_api_perm_list_perms.xml -->

### Requête

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
>Les types d&#39;objet TAGS et DERIVED SIGNALS n&#39;ont pas d&#39;autorisations régulières à utiliser. Les contrôles sur ces types d&#39;objets sont modifiés uniquement par les autorisations de caractères génériques Tout ou Rien.
