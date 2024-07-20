---
description: Dans le créateur de caractéristiques, le créateur d’expressions vous permet de créer et de tester des règles qui établissent des exigences de qualification d’audience. Les règles se composent de paires clé-valeur telles que "color == blue" ou "price &gt; 100". Les opérateurs de comparaison établissent la relation entre les clés et les valeurs. Les expressions booléennes déterminent la relation entre les groupes de règles.
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price &gt; 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: Gestion des règles de caractéristiques
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 0%

---

# Gestion des règles de caractéristiques {#managing-trait-rules}

Dans [!UICONTROL Trait Builder], le [!UICONTROL Expression Builder] vous permet de créer et de tester des règles qui établissent des exigences de qualification d’audience. Les règles se composent de paires clé-valeur, telles que `color == blue` ou `price > 100`. Les opérateurs de comparaison établissent la relation entre les clés et les valeurs. Les expressions [!DNL Boolean] déterminent la relation entre les groupes de règles.

<!-- c_tb_rules.xml -->

## Principales fonctionnalités des règles de signal décrites

![](assets/manage-trait-rules.png)

1. Les onglets **[!UICONTROL Expression Builder]** ou **[!UICONTROL Code View]** fournissent un aperçu des règles de votre caractéristique. L&#39;onglet **[!UICONTROL Expression Builder]** permet de créer des règles avec des champs et des menus déroulants. Le **[!UICONTROL Code View]** vous permet de créer des règles en écrivant manuellement ces expressions sous forme de code. L’illustration ci-dessus présente une caractéristique simple composée d’un signal qui évalue les données pour une condition admissible lorsqu’une clé de produit est égale à une valeur spécifique, dans ce cas `color == "blue"`.

1. Les champs et contrôles de cette section vous permettent de créer des signaux à partir de paires clé-valeur et de définir la relation entre eux avec un opérateur de comparaison. Une clé, un opérateur et une valeur sont requis.
1. Le [!UICONTROL Data Explorer Options] vous permet de renvoyer des réalisations de caractéristiques pour vos signaux.

   >[!NOTE]
   >
   >Cette option est disponible uniquement pour les clients [!UICONTROL Data Explorer]. Pour plus d’informations, contactez votre consultant d’Adobe.

1. Cette section présente une estimation des réalisations des caractéristiques pour les 7 derniers jours, pour les signaux définis dans l’ [!UICONTROL Expression Builder], pour les caractéristiques renvoyées et non renvoyées.

   >[!NOTE]
   >
   >Cette option est disponible uniquement pour les clients [!UICONTROL Data Explorer]. Pour plus d’informations, contactez votre consultant d’Adobe.

1. Les champs de test permettent de valider des combinaisons de règles de signal ou des [!DNL URL]s que vous souhaitez utiliser lors de l&#39;envoi de données à Audience Manager.

## Création d’une règle de caractéristique {#create-trait-rule}

Les règles (ou expressions) se composent d’individus ou de groupes de paires clé-valeur. Les opérateurs de comparaison définissent la relation entre les paires clé-valeur. Pour créer une règle, fournissez une clé, une valeur, sélectionnez un opérateur, puis cliquez sur **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Renseignez les champs requis de la section **[!UICONTROL Basic Information]** *avant* de créer des règles de caractéristiques.

1. Développez la section **[!UICONTROL Trait Expression]** et saisissez une clé et un nom de valeur. Cela crée un *`signal`*.

   >[!NOTE]
   >
   >Incluez le préfixe `c_` (ou toute autre convention d’affectation des noms) pour la variable clé si vos appels d’événement envoient des données à [!DNL Audience Manager] en utilisant cette syntaxe.

1. Sélectionnez un [opérateur de comparaison](../../features/traits/trait-comparison-operators.md) dans la liste déroulante **[!UICONTROL Operator]**. L’opérateur de comparaison évalue la relation entre les éléments d’un signal.

   >[!NOTE]
   >
   >L&#39;opérateur [!DNL Boolean] [!UICONTROL OR] établit la relation entre plusieurs signaux *dans* un groupe et ne peut pas être modifié.

1. Cliquez sur **[!UICONTROL Add Rule]**. La règle enregistrée s’affiche dans l’espace de travail des caractéristiques au-dessus des champs de saisie de données.

### Exemple {#example-trait-rule}

Dans l’exemple ci-dessous, un utilisateur a créé une règle de caractéristique basée sur l’ID de produit. Pour créer cette règle, l’utilisateur a fourni la clé `productkey` associée à un opérateur égal ( `==`) à la valeur `2093`.

![](assets/tb_sample_rule1.png)

Cliquez sur **[!UICONTROL Add Rule]** pour enregistrer et déplacer la caractéristique dans l’espace de travail [!UICONTROL Expression Builder].

![](assets/tb_sample_rule2.png)

## Création d’un groupe de règles {#create-rule-group}

Cette procédure décrit la création d’un groupe de règles.

<!-- t_tb_new_rule_group.xml -->

Votre caractéristique doit contenir au moins deux règles avant de pouvoir créer un nouveau groupe de règles.

1. Déplacez le curseur sur la règle que vous souhaitez déplacer pour la mettre en surbrillance.
1. Pointez sur la bordure de la règle mise en surbrillance.

   Cela sépare automatiquement la règle de son groupe actuel et la déplace dans un nouveau groupe.

   >[!NOTE]
   >
   >Faites glisser une règle vers son groupe d’origine si vous la déplacez involontairement.

1. Sélectionnez un opérateur [!DNL Boolean] ([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) dans le menu déroulant pour définir la relation entre les groupes de règles.

## Déplacement de règles entre groupes {#move-rules-between-groups}

Pour déplacer une règle, cliquez dessus et faites-la glisser vers un autre groupe.

## Modification d’une caractéristique {#edit-trait}

Cette procédure décrit la modification d’une caractéristique.

<!-- t_tb_edit.xml -->

1. Dans le tableau de bord [!UICONTROL Traits], passez la souris sur la colonne **[!UICONTROL Actions]** de la caractéristique que vous souhaitez modifier. Les icônes de gestion des caractéristiques s’affichent.
1. Cliquez sur le crayon pour modifier la caractéristique.

   ![](assets/tb_edit_trait.png)

## Suppression d’une règle de caractéristique {#delete-trait}

Cette procédure décrit la suppression d’une règle de caractéristique.

<!-- t_tb_delete_rule.xml -->

1. Dans le tableau de bord [!UICONTROL Traits], passez la souris sur les colonnes [!UICONTROL Actions] de la caractéristique à modifier, puis cliquez sur l’icône en forme de crayon. Les icônes de gestion des caractéristiques s’affichent.
1. Développez la section [!UICONTROL Trait Expression] .
1. Pointez sur la règle à supprimer, puis cliquez sur l’icône X. La règle est immédiatement supprimée.

>[!MORELIKETHIS]
>
>* [Créer un groupe de règles](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Déplacer des règles entre des groupes](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Créer une règle de caractéristique](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Supprimer une règle de caractéristique](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Déplacer des règles entre des groupes](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
