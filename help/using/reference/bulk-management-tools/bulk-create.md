---
description: La création en bloc permet de créer plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments d'une seule opération. Suivez ces instructions pour créer une demande de création en bloc.
seo-description: La création en bloc permet de créer plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments d'une seule opération. Suivez ces instructions pour créer une demande de création en bloc.
seo-title: Création en bloc
solution: Audience Manager
title: Création en bloc
uuid: 1 e 09 bcfa -783 e -4 e 9 b -9 ead -147 f 8 d 1381 c 8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Create{#bulk-create}

La création en bloc permet de créer plusieurs sources de données, signaux dérivés, segments, caractéristiques et autres éléments d&#39;une seule opération. Suivez ces instructions pour créer une demande de création en bloc.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Cet outil est fourni à titre de commodité uniquement. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Les permissions de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans [!DNL Audience Manager] l&#39;interface utilisateur sont respectées dans l&#39; [!UICONTROL Bulk Management Tools]interface.

>[!CAUTION]
>
>Ne mélanger pas les types d&#39;objet dans une demande de création en bloc. Les en-têtes de chaque objet sont uniques et ne peuvent pas être combinés. Effacez la feuille de calcul et faites une demande distincte pour différents éléments.

To create objects in bulk, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
1. Click the **[!UICONTROL Create]** tab.
1. Collez les en-têtes de création dans la première ligne de la feuille de calcul de mise à jour.
1. Collez ou tapez les données à modifier dans une colonne correspondante en fonction du libellé d&#39;en-tête.
1. Dans la barre d&#39;outils de la feuille de calcul, cliquez sur le bouton Créer correspondant à l&#39;élément que vous mettez à jour.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. Avant de saisir des données, votre création de feuille de calcul doit ressembler à l&#39;exemple suivant. Notez que toutes les options de création ne sont pas affichées ici. Ceci est inclus pour vous aider à comprendre à quoi pourrait ressembler une feuille de calcul terminée.

![](assets/cretetraits.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
