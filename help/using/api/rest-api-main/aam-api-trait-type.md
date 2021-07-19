---
description: Méthodes facultatives qui vous permettent d’affecter des caractéristiques à un type ou à une catégorie défini par l’utilisateur, généralement en fonction ou pour vos propres processus de création de rapports internes.
seo-description: Méthodes facultatives qui vous permettent d’affecter des caractéristiques à un type ou à une catégorie défini par l’utilisateur, généralement en fonction ou pour vos propres processus de création de rapports internes.
seo-title: Méthodes de type de caractéristique
solution: Audience Manager
title: Méthodes de type de caractéristique
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 10%

---

# Méthodes de type de caractéristique {#trait-type-methods}

Méthodes facultatives qui vous permettent d’affecter des caractéristiques à un type ou à une catégorie défini par l’utilisateur, généralement en fonction ou pour vos propres processus de création de rapports internes.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Les méthodes de type caractéristique n’attribuent pas de caractéristiques aux catégories utilisées par la [taxonomie commune](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Considérez-les comme des étiquettes distinctes de la taxonomie commune.

À titre de référence visuelle, [!UICONTROL Trait Types] est une liste déroulante située dans [!DNL UI] sous **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Création d’un type de caractéristique {#create-trait-type}

Une méthode `POST` qui permet de créer un nouveau type de caractéristique.

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

Une méthode `GET` qui renvoie des détails sur le type de caractéristique spécifié.

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

Une méthode `GET` qui renvoie des détails sur tous vos types de caractéristiques dans un tableau.

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
