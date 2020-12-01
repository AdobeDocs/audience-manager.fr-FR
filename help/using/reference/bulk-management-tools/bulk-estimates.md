---
description: Une estimation en masse renvoie des données de taille de segment basées sur des règles de segmentation. Suivez ces instructions pour effectuer une demande d'estimation en masse.
seo-description: Une estimation en masse renvoie des données de taille de segment basées sur des règles de segmentation. Suivez ces instructions pour effectuer une demande d'estimation en masse.
seo-title: Estimations en bloc
solution: Audience Manager
title: Estimations en bloc
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 3%

---


# Estimations en bloc{#bulk-estimates}

Une estimation en masse renvoie des données de taille de segment basées sur des règles de segmentation. Suivez ces instructions pour effectuer une demande d&#39;estimation en masse.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[Les ](../../features/administration/administration-overview.md) autorisations de groupe RBAC attribuées dans l’ [!DNL Audience Manager] interface utilisateur sont respectées dans le  [!UICONTROL Bulk Management Tools].

Pour effectuer des mises à jour en masse, ouvrez la feuille de calcul [!UICONTROL Bulk Management Tools] et :

1. Cliquez sur l&#39;onglet **[!UICONTROL Headers]** et copiez l&#39;en-tête [!UICONTROL Estimate Segment Size].
2. Cliquez sur l&#39;onglet **[!UICONTROL Estimate]**.
3. Collez l&#39;en-tête d&#39;estimation dans la première ligne de la feuille de calcul d&#39;estimation.
4. Collez ou tapez les données à modifier dans une colonne correspondante en fonction du libellé de l&#39;en-tête.
5. Dans la barre d&#39;outils de la feuille de calcul, cliquez sur le bouton Créer correspondant à l&#39;élément que vous mettez à jour.
Cette action ouvre la boîte de dialogue [!UICONTROL Account Information].
6. Fournissez les [informations de connexion requises](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) et cliquez sur **[!UICONTROL Submit]**.

Cette action crée une colonne [!UICONTROL Response] dans la feuille de calcul qui contient des données estimées sur la taille du segment. Avant de saisir des données, votre feuille d&#39;estimation en masse doit ressembler à ce qui suit :

![](assets/estimate.png)
Si votre mise à jour en masse renvoie une erreur ou échoue, voir  [Dépannage des outils](../../reference/bulk-management-tools/bulk-troubleshooting.md) de gestion en bloc.

