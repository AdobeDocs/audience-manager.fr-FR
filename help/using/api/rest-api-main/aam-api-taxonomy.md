---
description: Méthodes qui vous permettent d'afficher la taxonomie commune d'Audience Manager. Ce modèle de classification facultatif organise les caractéristiques dans des catégories standard du secteur.
seo-description: Méthodes qui vous permettent d'afficher la taxonomie commune d'Audience Manager. Ce modèle de classification facultatif organise les caractéristiques dans des catégories standard du secteur.
seo-title: Méthodes API taxonomiques
solution: Audience Manager
title: Méthodes API taxonomiques
uuid: 4 ee 29 ba 5-e 9 ba -4498-a 6 ee -7343227 dd 7 ba
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Taxonomic API Methods {#taxonomic-api-methods}

Méthodes qui vous permettent d&#39;afficher la taxonomie commune d&#39;Audience Manager. Ce modèle de classification facultatif organise les caractéristiques dans des catégories standard du secteur.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Vous ne pouvez pas créer de catégories taxonomiques ou classifier des caractéristiques avec ces méthodes. To classify a trait, specify the appropriate `categoryId` with a trait create or update method.

## Return a Specific Taxonomy {#return-specific-taxonomy}

`GET` Méthode qui renvoie des détails sur la catégorie taxonomique spécifiée.

<!-- r_rest_api_taxonomy.xml -->

### Demande

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Réponse

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist.

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## Return all Taxonomic Categories {#return-all-taxonomy-categories}

`GET` Méthode qui renvoie une liste des catégories de niveau supérieur dans un tableau.

<!-- r_rest_api_taxonomies.xml -->

### Demande

`GET https://api.demdex.com/v1/taxonomies/0/`

### Réponse

Tronqué pour concision.

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## Return Taxonomic Sub-Categories {#return-taxonomy-sub-categories}

`GET` Méthode qui renvoie des sous-catégories pour la catégorie parente spécifiée dans un tableau.

<!-- r_rest_api_taxonomy_sub.xml -->

### Demande

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Réponse

A successful response returns `200 OK` and the category for the specified ID. An unsuccessful request returns `404 No Content` if the ID does not exist. Tronqué pour concision.

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```
