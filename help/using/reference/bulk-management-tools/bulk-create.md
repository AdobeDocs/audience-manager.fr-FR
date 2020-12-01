---
description: La création en bloc vous permet de créer plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments à l’aide d’une seule opération. Suivez ces instructions pour effectuer une demande de création en masse.
seo-description: La création en bloc vous permet de créer plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments à l’aide d’une seule opération. Suivez ces instructions pour effectuer une demande de création en masse.
seo-title: Création en bloc
solution: Audience Manager
title: Création en bloc
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 2%

---


# Création en bloc{#bulk-create}

La création en bloc vous permet de créer plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments à l’aide d’une seule opération. Suivez ces instructions pour effectuer une demande de création en masse.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[Les ](../../features/administration/administration-overview.md) autorisations de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans le  [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Ne mélangez pas les types d’objet dans une demande de création en bloc. Les en-têtes de chaque objet sont uniques et ne peuvent pas être combinés. Effacez la feuille de calcul et effectuez une requête distincte pour différents éléments.

Pour créer des objets en bloc, ouvrez la feuille de calcul [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur l&#39;onglet **[!UICONTROL Headers]** et copiez les en-têtes de création de l&#39;élément à ajouter.
2. Cliquez sur l&#39;onglet **[!UICONTROL Create]**.
3. Collez les en-têtes de création dans la première ligne de la feuille de calcul de mise à jour.
4. Collez ou tapez les données à modifier dans une colonne correspondante en fonction du libellé de l&#39;en-tête.
5. Dans la barre d&#39;outils de la feuille de calcul, cliquez sur le bouton Créer correspondant à l&#39;élément que vous mettez à jour.
Cette action ouvre la boîte de dialogue [!UICONTROL Account Information].
6. Fournissez les [informations de connexion requises](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) et cliquez sur **[!UICONTROL Submit]**.

La feuille de calcul crée une colonne [!UICONTROL Results]. La colonne [!UICONTROL Results] renvoie la réponse JSON pour une opération réussie. Voir les [API REST](../../api/rest-api-main/rest-api-main.md) pour obtenir des exemples. Avant de saisir des données, votre feuille de calcul de création en masse doit ressembler à l&#39;exemple suivant. Notez que toutes les différentes options de création ne sont pas affichées ici. Elle vous aide à comprendre à quoi pourrait ressembler une feuille de calcul terminée.

![](assets/cretetraits.png)

Si votre mise à jour en masse renvoie une erreur ou échoue, voir [Résolution des problèmes liés aux outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).
