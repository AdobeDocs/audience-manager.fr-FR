---
description: Méthodes facultatives qui vous permettent d’affecter des caractéristiques à un type ou à une catégorie défini par l’utilisateur, généralement en fonction de la fonction ou pour vos propres processus de création de rapports internes.
seo-description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-title: Trait Type Methods
solution: Audience Manager
title: Méthodes de type de caractéristique
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
TQID: https://experienceleague.adobe.com/IoPUeMYwHk-D5F31Gx76Vmd97yRQqRIHlDWu3-5KZLg
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6c
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: f8667931-f646-4dd3-af2a-b9d0cb8098ad
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 151
ht-degree: 3%

---

# Méthodes de type de caractéristique {#trait-type-methods}

Méthodes facultatives qui vous permettent d’affecter des caractéristiques à un type ou à une catégorie défini par l’utilisateur, généralement en fonction de la fonction ou pour vos propres processus de création de rapports internes.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Les méthodes de type de caractéristique n’attribuent pas de caractéristiques aux catégories utilisées par la [taxonomie commune](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Considérez-les comme des libellés distincts de la taxonomie commune.

À titre de référence visuelle, [!UICONTROL Trait Types] est un contrôle déroulant situé dans le [!DNL UI] sous **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Création d’un type de caractéristique {#create-trait-type}

Une méthode `POST` qui permet de créer un nouveau type de caractéristique.

<!-- r_rest_api_create_trait_type.xml -->

### Requête

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

## Renvoyer les propriétés d’un type de caractéristique {#return-props}

Une méthode `GET` qui renvoie des détails sur le type de caractéristique spécifié.

<!-- r_rest_api_get_trait_type.xml -->

### Requête

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

### Requête

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
