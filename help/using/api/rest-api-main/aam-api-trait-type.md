---
description: Méthodes facultatives qui vous permettent d’attribuer des caractéristiques à un type ou une catégorie défini par l’utilisateur, généralement en fonction de la fonction ou pour vos propres processus de rapports interne.
seo-description: Méthodes facultatives qui vous permettent d’attribuer des caractéristiques à un type ou une catégorie défini par l’utilisateur, généralement en fonction de la fonction ou pour vos propres processus de rapports interne.
seo-title: Méthodes de type de caractéristique
solution: Audience Manager
title: Méthodes de type de caractéristique
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 9%

---


# Méthodes de type de caractéristique {#trait-type-methods}

Méthodes facultatives qui vous permettent d’attribuer des caractéristiques à un type ou une catégorie défini par l’utilisateur, généralement en fonction de la fonction ou pour vos propres processus de rapports interne.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Les méthodes de type de caractéristique n&#39;attribuent pas de caractéristiques aux catégories utilisées par la taxonomie [](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods)commune. Considérez ces étiquettes comme des étiquettes distinctes de la taxonomie commune.

Pour la référence visuelle, [!UICONTROL Trait Types] est un contrôle déroulant situé dans le [!DNL UI] sous **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Créer un nouveau type de caractéristique {#create-trait-type}

Méthode `POST` permettant de créer un nouveau type de caractéristique.

<!-- r_rest_api_create_trait_type.xml -->

### Demande

`POST https://api.demdex.com/v1/customer-trait-types`

### Exemple de requête

```
{
"name":"Custom trait type"
}
```

### Réponse

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## Propriétés de retour pour un type de caractéristique {#return-props}

Méthode `GET` qui renvoie des détails sur le type de caractéristique spécifié.

<!-- r_rest_api_get_trait_type.xml -->

### Demande

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### Réponse

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## Propriétés de retour pour tous les types de caractéristiques {#return-props-all}

Méthode `GET` qui renvoie des détails sur tous vos types de caractéristiques dans un tableau.

<!-- r_rest_api_get_trait_types.xml -->

### Demande

`GET https://api.demdex.com/v1/customer-trait-types/`

### Réponse

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```
