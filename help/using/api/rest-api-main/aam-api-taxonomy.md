---
description: Méthodes qui vous permettent de vue de la taxonomie commune à l'Audience Manager. Ce schéma de classification facultatif organise les caractéristiques en catégories standard du secteur.
seo-description: Méthodes qui vous permettent de vue de la taxonomie commune à l'Audience Manager. Ce schéma de classification facultatif organise les caractéristiques en catégories standard du secteur.
seo-title: Méthodes d’API taxonomiques
solution: Audience Manager
title: Méthodes d’API taxonomiques
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 7%

---


# Méthodes d’API taxonomiques {#taxonomic-api-methods}

Méthodes qui vous permettent de vue de la taxonomie commune à l&#39;Audience Manager. Ce schéma de classification facultatif organise les caractéristiques en catégories standard du secteur.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Vous ne pouvez pas créer de nouvelles catégories taxonomiques ni classifier les caractéristiques avec ces méthodes. Pour classer une caractéristique, spécifiez la caractéristique appropriée `categoryId` avec une méthode de création ou de mise à jour de caractéristique.

## Renvoyer une taxonomie spécifique {#return-specific-taxonomy}

Méthode `GET` qui renvoie des détails sur la catégorie taxonomique spécifiée.

<!-- r_rest_api_taxonomy.xml -->

### Demande

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Réponse

Une réponse réussie renvoie `200 OK` et la catégorie de l&#39;identifiant spécifié. Une requête non réussie renvoie `404 No Content` si l&#39;ID n&#39;existe pas.

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

## Renvoyer toutes les Catégories taxonomiques {#return-all-taxonomy-categories}

Méthode `GET` qui renvoie une liste des catégories de niveau supérieur dans un tableau.

<!-- r_rest_api_taxonomies.xml -->

### Demande

`GET https://api.demdex.com/v1/taxonomies/0/`

### Réponse

Tronqué pour la brièveté.

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

## Sous-Catégories taxonomiques de retour {#return-taxonomy-sub-categories}

Méthode `GET` qui renvoie des sous-catégories pour la catégorie parente spécifiée dans un tableau.

<!-- r_rest_api_taxonomy_sub.xml -->

### Demande

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Réponse

Une réponse réussie renvoie `200 OK` et la catégorie de l&#39;identifiant spécifié. Une requête non réussie renvoie `404 No Content` si l&#39;ID n&#39;existe pas. Tronqué pour la brièveté.

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
