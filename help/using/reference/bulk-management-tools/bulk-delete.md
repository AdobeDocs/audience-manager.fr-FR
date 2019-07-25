---
description: La suppression en bloc vous permet de supprimer plusieurs segments, caractéristiques, dossiers, signaux dérivés et destinations d'une seule opération. Suivez ces instructions pour effectuer une demande de suppression en bloc.
seo-description: La suppression en bloc vous permet de supprimer plusieurs segments, caractéristiques, dossiers, signaux dérivés et destinations d'une seule opération. Suivez ces instructions pour effectuer une demande de suppression en bloc.
seo-title: Suppression en bloc
solution: Audience Manager
title: Suppression en bloc
uuid: 679 cde 46-09 fb -45 c 6-b 84 d -47 e 00 e 00 e 0 c 0 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Delete{#bulk-delete}

La suppression en bloc vous permet de supprimer plusieurs segments, caractéristiques, dossiers, signaux dérivés et destinations d'une seule opération. Suivez ces instructions pour effectuer une demande de suppression en bloc.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Cet outil est fourni à titre de commodité uniquement. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [Les permissions de groupe RBAC](../../features/administration/administration-overview.md) attribuées dans [!DNL Audience Manager] l'interface utilisateur sont respectées dans l' [!UICONTROL Bulk Management Tools]interface.

>[!NOTE]
>
>Une suppression en bloc des correspondances de destination échoue si des segments sont mappés à la destination. Supprimez les segments de cette destination dans l'interface utilisateur avant de tenter de supprimer les destinations en masse. De plus, les dossiers de caractéristique et de segment doivent être vides avant de pouvoir les supprimer.

To delete multiple items, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
2. Click the **[!UICONTROL Delete]** tab.
3. Collez les en-têtes de suppression dans la première ligne de la feuille de calcul de mise à jour.
4. Collez ou tapez les identifiants des objets que vous souhaitez supprimer dans la colonne située sous l'en-tête.
5. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. [!UICONTROL Results] La colonne renvoie un message qui indique si l'élément a été supprimé ou un message d'erreur.
Avant de saisir des données, votre feuille de calcul de mise à jour globale doit se présenter comme suit :

![](assets/delete.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).
