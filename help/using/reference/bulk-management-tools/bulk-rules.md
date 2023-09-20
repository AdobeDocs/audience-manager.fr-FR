---
description: Les feuilles de calcul de création et de mise à jour acceptent un en-tête traitRule qui vous permet d’appliquer plusieurs règles au cours d’une seule opération. Suivez ces instructions pour effectuer des demandes de règle en bloc.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Création ou mise à jour de règles de caractéristiques et de segments
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 8%

---

# Création ou mise à jour de règles de caractéristiques et de segments{#create-or-update-trait-rules-and-segment-rules}

Les feuilles de calcul de création et de mise à jour acceptent un en-tête traitRule qui vous permet d’appliquer plusieurs règles au cours d’une seule opération. Suivez ces instructions pour effectuer des demandes de règle en bloc.

>[!IMPORTANT]
>
>Les outils de gestion en bloc ne sont pas une offre d’Adobe officiellement prise en charge. Le dépannage et l’assistance par l’intermédiaire de l’assistance clientèle seront gérés au cas par cas.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[Autorisations des groupes RBAC](../../features/administration/administration-overview.md) affecté dans la variable [!DNL Audience Manager] L’interface utilisateur est honorée dans la [!UICONTROL Bulk Management Tools].

## Utilisation des règles de caractéristiques {#trait-rules}

Dans votre feuille de calcul, la colonne de règle de caractéristique renvoie et accepte les règles composées d’expressions booléennes, d’opérateurs de comparaison et d’expressions régulières. Vous pouvez créer des règles avec le créateur de caractéristiques ou de segments dans [!DNL Audience Manager] et copiez-les dans votre feuille de calcul. Si vous connaissez la syntaxe des règles, vous pouvez également écrire des expressions directement dans les feuilles de calcul.

## Exemple de créateur de règles {#rule-builder-example}

Examinons un exemple qui illustre l’utilisation de [!UICONTROL Segment Builder] pour créer une règle, vous pouvez accéder à la feuille de calcul en bloc. Cependant, il ne s’agit pas d’un ensemble d’instructions étape par étape pour ces outils. Au lieu de cela, nous allons commencer avec une règle simple qui a déjà été créée. Pour plus d’informations sur l’utilisation des créateurs de règles, voir [Créateur de segments](../../features/segments/segment-builder.md) et [Créateur de caractéristiques](../../features/traits/about-trait-builder.md).

Avec le créateur de règles visuel, nous avons créé une règle de segment avec 3 caractéristiques et une valeur booléenne. [!UICONTROL AND] de l’opérateur.

![](assets/visualrule.png)

Cliquez sur **[!UICONTROL Code View]** pour obtenir la version texte de cette règle.

>[!TIP]
>
>Cliquez sur **[!UICONTROL Validate Expression]** pour vérifier la logique de votre règle. Cela vous empêchera de charger une règle non valide.

![](assets/coderule.png)

Collez la règle dans le [!UICONTROL Bulk Management Tools] et validez vos modifications pour mettre à jour les règles de segment en bloc.

![](assets/segmentrule.png)

## Créer vos propres règles {#create-rules}

Vous pouvez créer vos propres règles en dehors de [!UICONTROL Rule Builder]. Avant de commencer, veillez à lire la documentation qui couvre des éléments tels que les opérateurs, l’expression et les variables obligatoires. Nous vous recommandons de consulter les éléments suivants :

* [Utilisation D’Opérateurs De Comparaison Dans Le Créateur De Caractéristiques](../../features/traits/trait-comparison-operators.md)
* [Ordre des opérations](../../features/traits/trait-operator-precedence.md)
* [Exigences de préfixe pour les variables clés](../../features/traits/trait-variable-prefixes.md)
* [Exemple d’expressions avec des opérateurs booléens et de comparaison](../../features/traits/trait-expression-samples.md)
