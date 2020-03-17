---
description: Les feuilles de calcul de création et de mise à jour acceptent un en-tête traitRule qui vous permet d’appliquer plusieurs règles en une seule opération. Suivez ces instructions pour effectuer des demandes de règle en bloc.
seo-description: Les feuilles de calcul de création et de mise à jour acceptent un en-tête traitRule qui vous permet d’appliquer plusieurs règles en une seule opération. Suivez ces instructions pour effectuer des demandes de règle en bloc.
seo-title: Création ou mise à jour de règles de caractéristiques et de règles de segments
solution: Audience Manager
title: Création ou mise à jour de règles de caractéristiques et de règles de segments
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
translation-type: tm+mt
source-git-commit: 8cc3d9d629536c48b7013ffede16c0b112704c89

---


# Création ou mise à jour de règles de caractéristiques et de règles de segments{#create-or-update-trait-rules-and-segment-rules}

Les feuilles de calcul de création et de mise à jour acceptent un en-tête traitRule qui vous permet d’appliquer plusieurs règles en une seule opération. Suivez ces instructions pour effectuer des demandes de règle en bloc.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[Les autorisations](../../features/administration/administration-overview.md) de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans le [!UICONTROL Bulk Management Tools].

## Utilisation des règles de caractéristiques {#trait-rules}

Dans votre feuille de calcul, la colonne de règle de caractéristique renvoie et accepte des règles composées de  booléens, d’opérateurs de comparaison et de de  de données  ordinaires. Vous pouvez créer des règles avec le créateur de caractéristiques ou de segments dans [!DNL Audience Manager] et les copier dans votre feuille de calcul. Ou, si vous connaissez la syntaxe des règles, vous pouvez écrire  directement dans les feuilles de calcul.

## Exemple de créateur de règles {#rule-builder-example}

Examinons un exemple qui montre comment utiliser [!UICONTROL Segment Builder] pour créer une règle que vous pouvez dans la feuille de calcul en masse. Cependant, il ne s&#39;agit pas d&#39;un ensemble d&#39;instructions étape par étape pour ces outils. Au lieu de cela, nous allons  avec une règle simple qui a déjà été créée. Pour plus d’informations sur l’utilisation des créateurs de règles, voir Créateur [de](../../features/segments/segment-builder.md) segments et Créateur de [caractéristiques](../../features/traits/about-trait-builder.md).

Avec le créateur de règles visuel, nous avons créé une règle de segment avec 3 caractéristiques et un opérateur booléen [!UICONTROL AND] .

![](assets/visualrule.png)

Cliquez sur **[!UICONTROL Code View]** pour obtenir la version textuelle de cette règle.

>[!TIP]
>
>Cliquez sur **[!UICONTROL Validate Expression]** pour vérifier la logique de votre règle. Cela vous évitera de télécharger une règle non valide.

![](assets/coderule.png)

Collez la règle dans la [!UICONTROL Bulk Management Tools] feuille de calcul et validez vos modifications pour mettre à jour les règles de segment en bloc.

![](assets/segmentrule.png)

## Création de vos propres règles {#create-rules}

Vous pouvez écrire vos propres règles en dehors de [!UICONTROL Rule Builder]. Avant de , veillez à lire la documentation qui couvre des éléments tels que les opérateurs,  les et les variables requises. Nous vous recommandons de consulter les éléments suivants :

* [Utilisation D’Opérateurs De Comparaison Dans Le Créateur De Caractéristiques](../../features/traits/trait-comparison-operators.md)
* [Ordre des opérations](../../features/traits/trait-operator-precedence.md)
* [Préfixe requis pour les variables clés](../../features/traits/trait-variable-prefixes.md)
* [Exemple de  avec opérateur booléen et de comparaison](../../features/traits/trait-expression-samples.md)

