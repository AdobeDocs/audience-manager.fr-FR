---
description: Dans le créateur de caractéristiques, le créateur d’expressions vous permet de créer et de tester des règles qui établissent les exigences de qualification des audiences. Les règles se composent de paires clé-valeur telles que « color == blue » ou « price &gt; 100 ». Les opérateurs de comparaison établissent la relation entre les clés et les valeurs. Les expressions booléennes déterminent la relation entre les groupes de règles.
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

En [!UICONTROL Trait Builder], le [!UICONTROL Expression Builder] vous permet de créer et de tester des règles qui établissent les exigences de qualification d’audience. Les règles se composent de paires clé-valeur telles que `color == blue` ou `price > 100`. Les opérateurs de comparaison établissent la relation entre les clés et les valeurs. Les expressions [!DNL Boolean] déterminent la relation entre les groupes de règles.

<!-- c_tb_rules.xml -->

## Principales caractéristiques des règles de signalisation décrites

![](assets/manage-trait-rules.png)

1. Les onglets **[!UICONTROL Expression Builder]** ou **[!UICONTROL Code View]** donnent un aperçu des règles de votre caractéristique. L&#39;onglet **[!UICONTROL Expression Builder]** permet de créer des règles avec des champs et des menus déroulants. Le **[!UICONTROL Code View]** vous permet de créer des règles en écrivant manuellement ces expressions en tant que code. L’illustration ci-dessus montre une caractéristique simple composée d’un signal qui évalue les données d’une condition de qualification où une clé de produit est égale à une valeur spécifique, dans ce cas `color == "blue"`.

1. Les champs et commandes de cette section permettent de créer des signaux à partir de paires clé-valeur et de définir la relation entre elles avec un opérateur de comparaison. Une clé, un opérateur et une valeur sont requis.
1. Les [!UICONTROL Data Explorer Options] vous permettent de renvoyer des réalisations de caractéristiques pour vos signaux.

   >[!NOTE]
   >
   >Cette option n’est disponible que pour les clients [!UICONTROL Data Explorer]. Contactez votre consultant Adobe pour plus d’informations.

1. Cette section vous présente une estimation des réalisations des caractéristiques au cours des 7 derniers jours, pour les signaux définis dans le [!UICONTROL Expression Builder], pour les caractéristiques renvoyées et non renvoyées.

   >[!NOTE]
   >
   >Cette option n’est disponible que pour les clients [!UICONTROL Data Explorer]. Contactez votre consultant Adobe pour plus d’informations.

1. Les champs de test vous permettent de valider des combinaisons de règles de signal ou les [!DNL URL] que vous souhaitez utiliser lors de l’envoi de données à Audience Manager.

## Création d’une règle de caractéristique {#create-trait-rule}

Les règles (ou expressions) se composent d’individus ou de groupes de paires clé-valeur. Les opérateurs de comparaison définissent la relation entre les paires clé-valeur. Pour créer une règle, fournissez une clé, une valeur, sélectionnez un opérateur et cliquez sur **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Renseignez les champs obligatoires de la section **[!UICONTROL Basic Information]** *avant* de créer des règles de caractéristique.

1. Développez la section **[!UICONTROL Trait Expression]** et saisissez un nom de clé et de valeur. Cela crée une *`signal`*.

   >[!NOTE]
   >
   >Incluez le préfixe `c_` (ou toute autre convention de nommage) pour la variable clé si vos appels d’événement envoient des données à [!DNL Audience Manager] en utilisant cette syntaxe.

1. Sélectionnez un [opérateur de comparaison](../../features/traits/trait-comparison-operators.md) dans la liste déroulante **[!UICONTROL Operator]**. L&#39;opérateur de comparaison évalue la relation entre les éléments d&#39;un signal.

   >[!NOTE]
   >
   >L’opérateur [!DNL Boolean] [!UICONTROL OR] établit la relation entre plusieurs signaux *au sein* d’un groupe et ne peut pas être modifié.

1. Cliquez sur **[!UICONTROL Add Rule]**. La règle enregistrée s’affiche dans l’espace de travail des caractéristiques au-dessus des champs de saisie de données.

### Exemple {#example-trait-rule}

Dans l’exemple ci-dessous, un utilisateur a créé une règle de caractéristique en fonction de l’ID de produit. Pour créer cette règle, l’utilisateur a fourni la clé `productkey` liée à un opérateur égal ( `==`) à la valeur `2093`.

![](assets/tb_sample_rule1.png)

Cliquez sur **[!UICONTROL Add Rule]** pour enregistrer et déplacer la caractéristique dans l’espace de travail [!UICONTROL Expression Builder].

![](assets/tb_sample_rule2.png)

## Créer un groupe de règles {#create-rule-group}

Cette procédure décrit comment créer un groupe de règles.

<!-- t_tb_new_rule_group.xml -->

Votre caractéristique doit contenir au moins deux règles avant de pouvoir créer un groupe de règles.

1. Placez le curseur sur la règle à déplacer pour la mettre en surbrillance.
1. Pointez sur la bordure de règle en surbrillance.

   Cette opération sépare automatiquement la règle de son groupe actuel et la déplace vers un nouveau groupe.

   >[!NOTE]
   >
   >Faites glisser une règle vers son groupe d’origine si vous la déplacez involontairement.

1. Sélectionnez un opérateur de [!DNL Boolean] ([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) dans le menu déroulant pour définir la relation entre les groupes de règles.

## Déplacer Des Règles Entre Les Groupes {#move-rules-between-groups}

Pour déplacer une règle, cliquez dessus et faites-la glisser vers un autre groupe.

## Modification d’une caractéristique {#edit-trait}

Cette procédure décrit comment modifier une caractéristique.

<!-- t_tb_edit.xml -->

1. Dans le tableau de bord [!UICONTROL Traits], passez la souris sur la colonne **[!UICONTROL Actions]** pour la caractéristique à modifier. Les icônes de gestion des caractéristiques s’affichent.
1. Cliquez sur le crayon pour modifier la caractéristique.

   ![](assets/tb_edit_trait.png)

## Suppression d’une règle de caractéristique {#delete-trait}

Cette procédure décrit comment supprimer une règle de caractéristique.

<!-- t_tb_delete_rule.xml -->

1. Dans le tableau de bord [!UICONTROL Traits], passez la souris sur les colonnes [!UICONTROL Actions] pour la caractéristique à modifier, puis cliquez sur l’icône en forme de crayon. Les icônes de gestion des caractéristiques s’affichent.
1. Développez la section [!UICONTROL Trait Expression] .
1. Pointez sur la règle à supprimer, puis cliquez sur l’icône X. La règle est immédiatement supprimée.

>[!MORELIKETHIS]
>
>* [Créer un groupe de règles](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Déplacer Des Règles Entre Les Groupes](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Créer une règle de caractéristique](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Supprimer une règle de caractéristique](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Déplacer Des Règles Entre Les Groupes](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
