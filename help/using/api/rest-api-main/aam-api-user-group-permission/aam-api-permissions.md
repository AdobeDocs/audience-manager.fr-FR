---
description: Méthodes de l’API REST pour gérer les autorisations des objets et des groupes.
seo-description: Méthodes de l’API REST pour gérer les autorisations des objets et des groupes.
seo-title: Méthodes de l’API de gestion des autorisations
solution: Audience Manager
title: Méthodes de l’API de gestion des autorisations
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 3%

---


# Méthodes de l’API de gestion des autorisations {#permissions-management-api-methods}

Redéfinissez [!DNL API] les méthodes de gestion des autorisations pour les objets et les groupes.

<!-- c_rest_api_perm_man.xml -->

## Types d&#39;objet disponibles pour la Liste {#list-object-types}

Une `GET` méthode permettant de liste les types d&#39;objet disponibles sur lesquels des contrôles d&#39;accès basés sur les rôles peuvent être définis.

<!-- r_rest_api_perm_list.xml -->

### Demande

`GET /api/v1/permissionable-object-types/`

### Réponse

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Liste des autorisations disponibles pour un type d’objet {#list-permissions-object-type}

Méthode `GET` de liste des autorisations disponibles pour un type d’objet.

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
>Les types d&#39;objet TAGS et DERIVED SIGNALS n&#39;ont pas d&#39;autorisations régulières à utiliser. Les contrôles de ces types d’objet sont modifiés uniquement par les autorisations de carte générique Tout ou Rien.