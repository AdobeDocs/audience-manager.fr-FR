---
description: Les feuilles de calcul de création et de mise à jour acceptent un en-tête traitrule qui vous permet d'appliquer plusieurs règles en une seule opération. Suivez ces instructions pour créer des requêtes de règle en masse.
seo-description: Les feuilles de calcul de création et de mise à jour acceptent un en-tête traitrule qui vous permet d'appliquer plusieurs règles en une seule opération. Suivez ces instructions pour créer des requêtes de règle en masse.
seo-title: Création ou mise à jour de règles de caractéristiques et de règles de segmentation
solution: Audience Manager
title: Création ou mise à jour de règles de caractéristiques et de règles de segmentation
uuid: bdd 5 f 8 f 1-bb 83-4844-b 681-654 e 45 ace 3 e 1
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Create or Update Trait Rules and Segment Rules{#create-or-update-trait-rules-and-segment-rules}

Les feuilles de calcul de création et de mise à jour acceptent un en-tête traitrule qui vous permet d&#39;appliquer plusieurs règles en une seule opération. Suivez ces instructions pour créer des requêtes de règle en masse.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Cet outil est fourni à titre de commodité uniquement. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Les permissions de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans [!DNL Audience Manager] l&#39;interface utilisateur sont respectées dans l&#39; [!UICONTROL Bulk Management Tools]interface.

## Working with trait rules {#trait-rules}

Dans votre feuille de calcul, la colonne de règle de caractéristique renvoie et accepte les règles comprenant des expressions booléennes, des opérateurs de comparaison et des expressions régulières. You can create rules with trait or segment builder in [!DNL Audience Manager] and copy them to your worksheet. Ou, si vous connaissez la syntaxe des règles, vous pouvez écrire des expressions directement dans les feuilles de calcul.

## Rule builder example {#rule-builder-example}

Let&#39;s take a look at an example that demonstrates how to use [!UICONTROL Segment Builder] to create a rule you can to the bulk worksheet. Toutefois, il ne s&#39;agit pas d&#39;un ensemble d&#39;instructions pas à pas pour ces outils. Nous allons commencer par une règle simple qui a déjà été créée. For instructions about how to use the rule builders see [Segment Builder](../../features/segments/segment-builder.md) and [Trait Builder](../../features/traits/about-trait-builder.md).

With the visual rule builder, we&#39;ve created a segment rule with 3 traits and a Boolean [!UICONTROL AND] operator.

![](assets/visualrule.png)

Click **[!UICONTROL Code View]** to get the text version of this rule.

>[!TIP]
>
>Click **[!UICONTROL Validate Expression]** to check your rule logic. Cela vous évite de télécharger une règle non valide.

![](assets/coderule.png)

Paste the rule into the [!UICONTROL Bulk Management Tools] worksheet and commit your changes to update segment rules in bulk.

![](assets/segmentrule.png)

## Creating your own rules {#create-rules}

You can write your own rules outside of [!UICONTROL Rule Builder]. Avant de commencer, veillez à lire la documentation qui couvre des éléments tels que les opérateurs, l&#39;expression et les variables requises. Nous vous recommandons de consulter les éléments suivants :

* [Utilisation des opérateurs de comparaison dans le créateur de caractéristiques](../../features/traits/trait-comparison-operators.md)
* [Ordre des opérations](../../features/traits/trait-operator-precedence.md)
* [Exigences en matière de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)
* [Exemples d&#39;expressions avec opérateurs booléens et de comparaison](../../features/traits/trait-expression-samples.md)

