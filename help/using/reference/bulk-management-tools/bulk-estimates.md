---
description: Une estimation en masse renvoie les données de taille de segment en fonction des règles de segmentation. Suivez ces instructions pour effectuer une demande d'estimation en masse.
seo-description: Une estimation en masse renvoie les données de taille de segment en fonction des règles de segmentation. Suivez ces instructions pour effectuer une demande d'estimation en masse.
seo-title: Estimations en masse
solution: Audience Manager
title: Estimations en masse
uuid: 63 b 2 f 06 a -8 ba 0-47 a 2-bd 0 b -8039 b 2 d 4 c 95 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Estimates{#bulk-estimates}

Une estimation en masse renvoie les données de taille de segment en fonction des règles de segmentation. Suivez ces instructions pour effectuer une demande d&#39;estimation en masse.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Cet outil est fourni à titre de commodité uniquement. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Les permissions de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans [!DNL Audience Manager] l&#39;interface utilisateur sont respectées dans l&#39; [!UICONTROL Bulk Management Tools]interface.

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the [!UICONTROL Estimate Segment Size] header.
1. Click the **[!UICONTROL Estimate]** tab.
1. Collez l&#39;en-tête d&#39;estimation dans la première ligne de la feuille de calcul d&#39;estimation.
1. Collez ou tapez les données à modifier dans une colonne correspondante en fonction du libellé d&#39;en-tête.
1. Dans la barre d&#39;outils de la feuille de calcul, cliquez sur le bouton Créer correspondant à l&#39;élément que vous mettez à jour.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

This action creates a [!UICONTROL Response] column in the worksheet that contains estimated segment size data. Avant de saisir des données, votre feuille de calcul d&#39;estimation en masse doit se présenter comme suit :

![](assets/estimate.png)Si votre mise à jour en masse renvoie une erreur ou échoue, voir [Dépannage des outils de gestion en bloc](../../reference/bulk-management-tools/bulk-troubleshooting.md).

