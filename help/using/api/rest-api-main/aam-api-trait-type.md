---
description: Méthodes facultatives vous permettant d'affecter des caractéristiques à un type ou une catégorie définis par l'utilisateur, généralement selon la fonction ou pour vos propres processus de création de rapports internes.
seo-description: Méthodes facultatives vous permettant d'affecter des caractéristiques à un type ou une catégorie définis par l'utilisateur, généralement selon la fonction ou pour vos propres processus de création de rapports internes.
seo-title: Méthodes de type de caractéristique
solution: Audience Manager
title: Méthodes de type de caractéristique
uuid: 082931 d 5-457 b -4622-817 b -86303 f 38 c 26 a
translation-type: tm+mt
source-git-commit: ad81dd596434534906788223f3c9531ffa50d9b4

---


# Trait Type Methods {#trait-type-methods}

Méthodes facultatives vous permettant d&#39;affecter des caractéristiques à un type ou une catégorie définis par l&#39;utilisateur, généralement selon la fonction ou pour vos propres processus de création de rapports internes.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Trait type methods do not assign traits to categories used by the [common taxonomy](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Considérez ces libellés comme des libellés distincts de la taxonomie commune.

For visual reference, [!UICONTROL Trait Types] is a dropdown control located in the [!DNL UI] under **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Create a New Trait Type {#create-trait-type}

`POST` Méthode qui vous permet de créer un type de caractéristique.

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

## Return Properties for a Trait Type {#return-props}

`GET` Méthode qui renvoie des détails sur le type de caractéristique spécifié.

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

## Return Properties for all Trait Types {#return-props-all}

`GET` Méthode qui renvoie des détails sur tous les types de caractéristiques dans un tableau.

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
