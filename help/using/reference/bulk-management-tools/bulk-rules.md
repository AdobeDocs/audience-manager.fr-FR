---
description: Les feuilles de calcul de création et de mise à jour acceptent un en-tête traitRule qui vous permet d’appliquer plusieurs règles en une seule opération. Suivez ces instructions pour effectuer des requêtes de règles en bloc.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Créer ou mettre à jour des règles de caractéristiques et des règles de segments
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
TQID: https://experienceleague.adobe.com/7vkYd55lKv1PCjRqX-OxK1A-VIjgH3O9Tx0AnbZvRWA
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2: id: d3dfac44-e20d-492d-a806-0f4a4a495901id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2: id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 343
ht-degree: 1%

---

# Créer ou mettre à jour des règles de caractéristiques et des règles de segments{#create-or-update-trait-rules-and-segment-rules}

Les feuilles de calcul de création et de mise à jour acceptent un en-tête traitRule qui vous permet d’appliquer plusieurs règles en une seule opération. Suivez ces instructions pour effectuer des requêtes de règles en bloc.

>[!IMPORTANT]
>
>Les outils de gestion en bloc ne sont pas une offre Adobe officiellement prise en charge. Le dépannage et l’assistance par l’intermédiaire de l’assistance clientèle seront gérés au cas par cas.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>Les [autorisations de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans l’interface utilisateur de [!DNL Audience Manager] sont respectées dans la [!UICONTROL Bulk Management Tools].

## Utilisation des règles de caractéristiques {#trait-rules}

Dans votre feuille de calcul, la colonne de règle de caractéristique renvoie et accepte les règles composées d’expressions booléennes, d’opérateurs de comparaison et d’expressions régulières. Vous pouvez créer des règles avec le créateur de caractéristiques ou de segments dans [!DNL Audience Manager] et les copier dans votre feuille de calcul. Ou, si vous connaissez la syntaxe des règles, vous pouvez écrire des expressions directement dans les feuilles de calcul.

## Exemple de créateur de règles {#rule-builder-example}

Prenons un exemple qui montre comment utiliser [!UICONTROL Segment Builder] pour créer une règle que vous pouvez appliquer à la feuille de calcul en bloc. Cependant, il ne s’agit pas d’un ensemble d’instructions détaillées pour ces outils. Au lieu de cela, nous allons commencer avec une règle simple qui a déjà été créée. Pour obtenir des instructions sur l’utilisation des créateurs de règles, voir [Créateur de segments](../../features/segments/segment-builder.md) et [Créateur de caractéristiques](../../features/traits/about-trait-builder.md).

Avec le créateur de règles visuel, nous avons créé une règle de segment avec 3 caractéristiques et un opérateur [!UICONTROL AND] booléen.

![](assets/visualrule.png)

Cliquez sur **[!UICONTROL Code View]** pour obtenir la version texte de cette règle.

>[!TIP]
>
>Cliquez sur **[!UICONTROL Validate Expression]** pour vérifier la logique de vos règles. Cela vous aidera à éviter de charger une règle non valide.

![](assets/coderule.png)

Collez la règle dans la feuille de calcul [!UICONTROL Bulk Management Tools] et validez vos modifications pour mettre à jour les règles de segment en bloc.

![](assets/segmentrule.png)

## Création de vos propres règles {#create-rules}

Vous pouvez écrire vos propres règles en dehors de [!UICONTROL Rule Builder]. Avant de commencer, veillez à lire la documentation qui couvre des éléments tels que les opérateurs, l’expression et les variables requises. Nous vous recommandons de consulter les éléments suivants :

* [Utilisation Des Opérateurs De Comparaison Dans Le Générateur De Caractéristiques](../../features/traits/trait-comparison-operators.md)
* [Ordre des opérations](../../features/traits/trait-operator-precedence.md)
* [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)
* [Exemples d’expressions avec des opérateurs booléens et de comparaison](../../features/traits/trait-expression-samples.md)
