---
description: Dans le créateur de caractéristiques, le créateur d’Expressions vous permet de créer et de tester des règles qui définissent les exigences de qualification des audiences. Les règles se composent de paires clé-valeur telles que "color == blue" ou "price > 100". Les opérateurs de comparaison établissent la relation entre les clés et les valeurs. Les expressions booléennes déterminent la relation entre les groupes de règles.
seo-description: Dans le créateur de caractéristiques, le créateur d’Expressions vous permet de créer et de tester des règles qui définissent les exigences de qualification des audiences. Les règles se composent de paires clé-valeur telles que "color == blue" ou "price > 100". Les opérateurs de comparaison établissent la relation entre les clés et les valeurs. Les expressions booléennes déterminent la relation entre les groupes de règles.
seo-title: Gestion des règles de caractéristiques
solution: Audience Manager
title: Gestion des règles de caractéristiques
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
translation-type: tm+mt
source-git-commit: 14c5ac091a27d125c96d17ce750c6e25ad844856
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 1%

---


# Gestion des règles de caractéristiques {#managing-trait-rules}

Dans [!UICONTROL Trait Builder], [!UICONTROL Expression Builder] vous permet de créer et de tester des règles qui établissent les exigences de qualification des audiences. Les règles se composent de paires clé-valeur, telles que `color == blue` ou `price > 100`. Les opérateurs de comparaison établissent la relation entre les clés et les valeurs. [!DNL Boolean] Les expressions déterminent la relation entre les groupes de règles.

<!-- c_tb_rules.xml -->

## Principales fonctionnalités des règles de signal décrites

![](assets/manage-trait-rules.png)

1. Les onglets **[!UICONTROL Expression Builder]** ou **[!UICONTROL Code View]** fournissent un aperçu des règles de votre caractéristique. L&#39;onglet **[!UICONTROL Expression Builder]** permet de créer des règles avec des champs et des menus déroulants. **[!UICONTROL Code View]** permet de créer des règles en écrivant manuellement ces expressions en tant que code. L&#39;illustration ci-dessus montre une caractéristique simple composée d&#39;un signal qui évalue les données pour une condition de qualification lorsqu&#39;une clé de produit est égale à une valeur spécifique, dans ce cas `color == "blue"`.

1. Les champs et les contrôles de cette section vous permettent de créer des signaux à partir de paires clé-valeur et de définir la relation entre eux avec un opérateur de comparaison. Une clé, un opérateur et une valeur sont requis.
1. Le [!UICONTROL Data Explorer Options] vous permet de renvoyer les réalisations de caractéristiques de vos signaux.

   >[!NOTE]
   >
   >Cette option est disponible uniquement pour les clients [!UICONTROL Data Explorer]. Contactez votre consultant en Adobe pour plus de détails.

1. Cette section présente une estimation des réalisations de caractéristiques pour les 7 derniers jours, pour les signaux définis dans [!UICONTROL Expression Builder], pour les caractéristiques renvoyées et non renversées.

   >[!NOTE]
   >
   >Cette option est disponible uniquement pour les clients [!UICONTROL Data Explorer]. Contactez votre consultant en Adobe pour plus de détails.

1. Les champs de test vous permettent de valider des combinaisons de règles de signal ou les [!DNL URL]s que vous souhaitez utiliser lors de l’envoi de données à l’Audience Manager.

## Créer une règle de caractéristiques {#create-trait-rule}

Les règles (ou expressions) se composent de paires clé-valeur individuelles ou de groupes de paires clé-valeur. Les opérateurs de comparaison définissent la relation entre les paires clé-valeur. Pour créer une règle, fournissez une clé, une valeur, sélectionnez un opérateur, puis cliquez sur **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Renseignez les champs obligatoires de la section **[!UICONTROL Basic Information]** *avant* de créer des règles de caractéristiques.

1. Développez la section **[!UICONTROL Trait Expression]** et saisissez une clé et un nom de valeur. Cela crée un *`signal`*.

   >[!NOTE]
   >
   >Incluez le préfixe `c_` (ou toute autre convention d’affectation de nom) pour la variable clé si vos appels de événement envoient des données à [!DNL Audience Manager] à l’aide de cette syntaxe.

1. Sélectionnez un [opérateur de comparaison](../../features/traits/trait-comparison-operators.md) dans la liste déroulante **[!UICONTROL Operator]**. L’opérateur de comparaison évalue la relation entre les éléments d’un signal.

   >[!NOTE]
   >
   >L&#39;opérateur [!DNL Boolean] [!UICONTROL OR] établit la relation entre plusieurs signaux *dans* un groupe et ne peut pas être modifié.

1. Cliquez sur **[!UICONTROL Add Rule]**. La règle enregistrée s&#39;affiche dans l&#39;espace de travail des caractéristiques au-dessus des champs de saisie de données.

### Exemple {#example-trait-rule}

Dans l’exemple ci-dessous, un utilisateur a créé une nouvelle règle de caractéristiques basée sur l’identifiant du produit. Pour créer cette règle, l’utilisateur a fourni la clé `productkey` associée à un opérateur égal ( `==`) à la valeur `2093`.

![](assets/tb_sample_rule1.png)

Cliquez sur **[!UICONTROL Add Rule]** pour enregistrer et déplacer la caractéristique dans l&#39;espace de travail [!UICONTROL Expression Builder].

![](assets/tb_sample_rule2.png)

## Créer un groupe de règles {#create-rule-group}

Cette procédure décrit comment créer un nouveau groupe de règles.

<!-- t_tb_new_rule_group.xml -->

Votre caractéristique doit contenir au moins deux règles avant de pouvoir créer un nouveau groupe de règles.

1. Placez le curseur sur la règle à déplacer pour la mettre en surbrillance.
1. Passez la souris sur la bordure de la règle mise en surbrillance.

   Cette opération sépare automatiquement la règle de son groupe actuel et la déplace dans un nouveau groupe.

   >[!NOTE]
   >
   >Faites glisser une règle vers son groupe d’origine si vous la déplacez involontairement.

1. Sélectionnez un opérateur [!DNL Boolean] ([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) dans le menu déroulant pour définir la relation entre les groupes de règles.

## Déplacer les règles entre les groupes {#move-rules-between-groups}

Pour déplacer une règle, cliquez dessus et faites-la glisser vers un autre groupe.

## Modifier un trait {#edit-trait}

Cette procédure décrit la modification d’une caractéristique.

<!-- t_tb_edit.xml -->

1. Dans le tableau de bord [!UICONTROL Traits], passez la souris sur la colonne **[!UICONTROL Actions]** correspondant à la caractéristique à modifier. Ceci affiche les icônes de gestion des caractéristiques.
1. Cliquez sur le crayon pour modifier la caractéristique.

   ![](assets/tb_edit_trait.png)

## Supprimer une règle de caractéristiques {#delete-trait}

Cette procédure décrit la suppression d’une règle de caractéristiques.

<!-- t_tb_delete_rule.xml -->

1. Dans le tableau de bord [!UICONTROL Traits], passez la souris sur les colonnes [!UICONTROL Actions] correspondant à la caractéristique à modifier, puis cliquez sur l&#39;icône représentant un crayon. Ceci affiche les icônes de gestion des caractéristiques.
1. Développez la section [!UICONTROL Trait Expression].
1. Passez la souris sur la règle à supprimer, puis cliquez sur l’icône X. La règle est supprimée immédiatement.

>[!MORELIKETHIS]
>
>* [Créer un groupe de règles](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Déplacer les règles entre les groupes](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Créer une règle de caractéristiques](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Supprimer une règle de caractéristiques](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Déplacer les règles entre les groupes](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

