---
description: Méthodes qui permettent d’afficher la taxonomie commune Audience Manager. Ce schéma de classification facultatif organise les caractéristiques en catégories standard du secteur.
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: Méthodes d’API taxonomiques
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 1%

---

# Méthodes d’API taxonomiques {#taxonomic-api-methods}

Méthodes qui permettent d’afficher la taxonomie commune Audience Manager. Ce schéma de classification facultatif organise les caractéristiques en catégories standard du secteur.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Vous ne pouvez pas créer de nouvelles catégories taxonomiques ni classer les caractéristiques à l’aide de ces méthodes. Pour classer une caractéristique, spécifiez la `categoryId` appropriée avec une méthode de création ou de mise à jour de caractéristique.

## Renvoyer une taxonomie spécifique {#return-specific-taxonomy}

Méthode `GET` qui renvoie des détails sur la catégorie taxonomique spécifiée.

<!-- r_rest_api_taxonomy.xml -->

### Requête

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Réponse

Une réponse réussie renvoie `200 OK` et la catégorie de l’identifiant spécifié. Une requête infructueuse renvoie `404 No Content` si l’identifiant n’existe pas.

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

## Renvoyer toutes les catégories taxonomiques {#return-all-taxonomy-categories}

Une méthode `GET` qui renvoie une liste des catégories de niveau supérieur dans un tableau.

<!-- r_rest_api_taxonomies.xml -->

### Requête

`GET https://api.demdex.com/v1/taxonomies/0/`

### Réponse

Tronqué pour des raisons de concision.

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

## Renvoyer les sous-catégories taxonomiques {#return-taxonomy-sub-categories}

Une méthode `GET` qui renvoie des sous-catégories pour la catégorie parent spécifiée dans un tableau.

<!-- r_rest_api_taxonomy_sub.xml -->

### Requête

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Réponse

Une réponse réussie renvoie `200 OK` et la catégorie de l’identifiant spécifié. Une requête infructueuse renvoie `404 No Content` si l’identifiant n’existe pas. Tronqué pour des raisons de concision.

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
