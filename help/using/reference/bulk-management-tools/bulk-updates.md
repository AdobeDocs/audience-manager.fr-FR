---
description: Une mise à jour en masse vous permet de modifier plusieurs segments, caractéristiques et dossiers de segments ou de caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en bloc.
keywords: baaam
seo-description: Une mise à jour en masse vous permet de modifier plusieurs segments, caractéristiques et dossiers de segments ou de caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en bloc.
seo-title: Mises à jour en masse
solution: Audience Manager
title: Mises à jour en masse
uuid: 22 f 1 badd-a 274-4 d 3 e -9957-a 24 bf 8 c 1 d 0 dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Updates{#bulk-updates}

Une mise à jour en masse vous permet de modifier plusieurs segments, caractéristiques et dossiers de segments ou de caractéristiques en une seule opération. Suivez ces instructions pour effectuer des mises à jour en bloc.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Cet outil est fourni à titre de commodité uniquement. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Les permissions de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans [!DNL Audience Manager] l&#39;interface utilisateur sont respectées dans l&#39; [!UICONTROL Bulk Management Tools]interface.

To make bulk updates, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the update headers for the item you want to edit.
1. Click the **[!UICONTROL Update]** tab.
1. Collez les en-têtes de mise à jour dans la première ligne de la feuille de calcul de mise à jour. Tenez compte des points suivants :

   * Lors de la mise à jour d&#39;un dossier, tous les en-têtes sont obligatoires.
   * Lors de la mise à jour de segments ou de caractéristiques, vous avez uniquement besoin de l&#39;identifiant de segment (SID) et de l&#39;élément d&#39;en-tête à modifier. Supprimer les en-têtes inutilisés.

1. Collez ou tapez les données à modifier dans une colonne correspondante en fonction du libellé d&#39;en-tête.
1. Dans la barre d&#39;outils de la feuille de calcul, cliquez sur un bouton de mise à jour correspondant à l&#39;élément que vous mettez à jour.
This action opens the [!UICONTROL Account Information] dialog box.

1. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns the JSON response for a successful operation. See the [REST APIs](../../api/rest-api-main/rest-api-main.md) for examples. Avant de saisir des données, votre feuille de calcul de mise à jour globale doit se présenter comme suit :

![](assets/update.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
