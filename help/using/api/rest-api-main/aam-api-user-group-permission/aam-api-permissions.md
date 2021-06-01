---
description: Méthodes d’API REST pour gérer les autorisations des objets et des groupes.
seo-description: Méthodes d’API REST pour gérer les autorisations des objets et des groupes.
seo-title: Méthodes d’API de gestion des autorisations
solution: Audience Manager
title: Méthodes d’API de gestion des autorisations
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 15%

---

# Méthodes d’API de gestion des autorisations {#permissions-management-api-methods}

Redéfinissez les méthodes [!DNL API] pour gérer les autorisations des objets et des groupes.

<!-- c_rest_api_perm_man.xml -->

## Liste des types d’objet disponibles {#list-object-types}

Une méthode `GET` pour répertorier les types d’objets disponibles sur lesquels des contrôles d’accès basés sur les rôles peuvent être définis.

<!-- r_rest_api_perm_list.xml -->

### Demande

`GET /api/v1/permissionable-object-types/`

### Réponse

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Liste des autorisations disponibles pour un type d’objet {#list-permissions-object-type}

Une méthode `GET` pour répertorier les autorisations disponibles pour un type d’objet.

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
>Les types d’objet BALISES et SIGNAUX DÉRIVÉS ne disposent pas d’autorisations régulières à utiliser. Les contrôles sur ces types d’objets sont modifiés uniquement par les autorisations génériques All (Tout ou Rien).
