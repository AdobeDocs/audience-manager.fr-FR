---
description: Dans le créateur de caractéristiques, le Générateur d'expression vous permet de créer et de tester des règles qui définissent les exigences de qualification de l'audience. Les règles consistent en des paires clé-valeur telles que « color = = blue » ou « price > 100 ». Les opérateurs de comparaison définissent la relation entre les clés et les valeurs. Les expressions booléennes déterminent la relation entre les groupes de règles.
seo-description: Dans le créateur de caractéristiques, le Générateur d'expression vous permet de créer et de tester des règles qui définissent les exigences de qualification de l'audience. Les règles consistent en des paires clé-valeur telles que « color = = blue » ou « price > 100 ». Les opérateurs de comparaison définissent la relation entre les clés et les valeurs. Les expressions booléennes déterminent la relation entre les groupes de règles.
seo-title: Gestion des règles de caractéristiques
solution: Audience Manager
title: Gestion des règles de caractéristiques
uuid: 827 d 4567-2 b 6 f -411 e-bd 5 c -9735 c 916291 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Managing Trait Rules {#managing-trait-rules}

In [!UICONTROL Trait Builder], the [!UICONTROL Expression Builder] lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as `color == blue` or `price > 100`. Les opérateurs de comparaison définissent la relation entre les clés et les valeurs. [!DNL Boolean] Les expressions déterminent la relation entre les groupes de règles.

<!-- c_tb_rules.xml -->

## Fonctionnalités des règles de signal principales décrites

![](assets/manage-trait-rules.png)

1. The **[!UICONTROL Expression Builder]** or **[!UICONTROL Code View]** tabs provide an overview of the rules in your trait. **[!UICONTROL Expression Builder]** L'onglet vous permet de créer des règles avec des champs et des menus déroulants. The **[!UICONTROL Code View]** lets you create rules by manually writing those expressions as code. The illustration above shows a simple trait composed of a signal that evaluates data for a qualifying condition where a product key equals a specific value, in this case `color == "blue"`.

1. Les champs et les commandes de cette section vous permettent de créer des signaux à partir de paires clé-valeur et de définir la relation entre eux avec un opérateur de comparaison. Une clé, un opérateur et une valeur sont requis.
1. The [!UICONTROL Data Explorer Options] allow you to backfill trait realizations for your signals.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. Pour plus d'informations, contactez votre consultant Adobe.
1. This section shows you an estimation of trait realizations for the past 7 days, for the signals defined in the [!UICONTROL Expression Builder], for backfilled and non-backfilled traits.
   >[!NOTE]
   >
   >This option is only available for [!UICONTROL Data Explorer] customers. Pour plus d'informations, contactez votre consultant Adobe.
1. The test fields let you validate combinations of signal rules or the [!DNL URL]s that you want to use when sending data to Audience Manager.

## Create a Trait Rule {#create-trait-rule}

Les règles (ou expressions) consistent en des groupes individuels ou des groupes de paires clé-valeur. Les opérateurs de comparaison définissent la relation entre les paires clé-valeur. To create a rule,provide a key, a value, select an operator, and click **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Complete the required fields in the **[!UICONTROL Basic Information]** section *before* creating trait rules.

1. Expand the **[!UICONTROL Trait Expression]** section and enter a key and value name. This creates a *`signal`*.
   >[!NOTE]
   >
   >Include the `c_` prefix (or any other naming convention) for key variable if your event calls send data to [!DNL Audience Manager] using that syntax.
1. Select a [comparison operator](../../features/traits/trait-comparison-operators.md) from the **[!UICONTROL Operator]** dropdown. L'opérateur de comparaison évalue la relation entre les éléments d'un signal.
   >[!NOTE]
   >
   >[!DNL Boolean][!UICONTROL OR] L'opérateur établit la relation entre plusieurs signaux *au sein* d'un groupe et ne peut pas être modifié.
1. Cliquez sur **[!UICONTROL Add Rule]**. La règle enregistrée apparaît dans l'espace de travail Caractéristiques au-dessus des champs de saisie de données.

### Exemple {#example-trait-rule}

Dans l'exemple ci-dessous, un utilisateur a créé une règle de caractéristique basée sur l'ID du produit. To build this rule, the user provided the key `productkey` linked with an equals operator ( `==`) to the value `2093`.
![](assets/tb_sample_rule1.png)

Clicking **[!UICONTROL Add Rule]** saves and moves the trait into the [!UICONTROL Expression Builder] workspace.

![](assets/tb_sample_rule2.png)

>[!MORE_ LIKE_ THIS]
>
>* [Créer un groupe de règles](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Déplacer les règles entre les groupes](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Suppression d'une règle de caractéristique](../../features/traits/manage-trait-rules.md#delete-trait)


## Create a New Rule Group {#create-rule-group}

Cette procédure décrit la création d'un groupe de règles.

<!-- t_tb_new_rule_group.xml -->

Votre caractéristique doit contenir au moins deux règles avant de pouvoir créer un nouveau groupe de règles.

1. Placez le curseur sur la règle que vous souhaitez déplacer pour le mettre en évidence.
1. Passez la souris sur la bordure de règle mise en surbrillance.
Cette règle sépare automatiquement la règle de son groupe actuel et la place dans un nouveau groupe.
   >[!NOTE]
   >
   >Faites glisser une règle vers son groupe d'origine si vous le déplacez involontairement.
1. Select a [!DNL Boolean] operator ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) from the drop-down menu to set the relationship between the rule groups.

>[!MORE_ LIKE_ THIS]
>
>* [Création d'une règle de caractéristique](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Déplacer les règles entre les groupes](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Suppression d'une règle de caractéristique](../../features/traits/manage-trait-rules.md#delete-trait)


## Move Rules Between Groups {#move-rules-between-groups}

Pour déplacer une règle, cliquez dessus et faites-la glisser vers un autre groupe.

>[!MORE_ LIKE_ THIS]
>
>* [Création d'une règle de caractéristique](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Créer un groupe de règles](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Suppression d'une règle de caractéristique](../../features/traits/manage-trait-rules.md#delete-trait)


## Edit a Trait {#edit-trait}

Cette procédure décrit la modification d'une caractéristique.

<!-- t_tb_edit.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the trait you want to edit. Cela permet d'afficher les icônes de gestion des caractéristiques.
1. Cliquez sur le crayon pour modifier la caractéristique.

   ![](assets/tb_edit_trait.png)

## Delete a Trait Rule {#delete-trait}

Cette procédure décrit la suppression d'une règle de caractéristique.

<!-- t_tb_delete_rule.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the [!UICONTROL Actions] columns for the trait you want to edit and click the pencil icon. Cela permet d'afficher les icônes de gestion des caractéristiques.
1. Expand the [!UICONTROL Trait Expression] section.
1. Passez la souris sur la règle à supprimer et cliquez sur l'icône X. La règle est supprimée immédiatement.