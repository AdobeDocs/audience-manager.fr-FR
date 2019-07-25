---
description: Créez, modifiez et supprimez des caractéristiques de dossier.
keywords: Caractéristique de dossier ; Caractéristiques du dossier ; des caractéristiques de dossier ; caractéristique de dossier
seo-description: Créez, modifiez et supprimez des caractéristiques de dossier.
seo-title: Gérer les caractéristiques de dossier
solution: Audience Manager
title: Gérer les caractéristiques de dossier
uuid: 287 ac 280-bd 58-4985-85 bd-b 6501 eb 64 b 7 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Folder Traits {#manage-folder-traits}

Créez, modifiez et supprimez des caractéristiques de dossier.

## Create a Folder Trait {#create-folder-trait}

A [!UICONTROL folder trait] is created automatically when you create a new folder in your taxonomy.

<!-- create-folder-trait.xml -->

1. Go to **[!UICONTROL Audience Data > Traits]** to navigate to the **Traits** dashboard.
1. In the [!UICONTROL Trait Storage] window, hover over:

   * Texte « Toutes les caractéristiques » pour ajouter un nouveau dossier de niveau racine.
   * Un dossier parent existant pour ajouter un nouveau dossier subordonné.
   ![](assets/folder_traits_create.PNG)

1. Cliquez sur l’icône + pour créer le dossier. Vous pouvez créer 2 000 dossiers au maximum dans la taxonomie. Pour plus d’informations, consultez la documentation relative aux [limites d’utilisation](../../features/administration/usage-limits.md).
1. Name the folder and click **Save**. Par exemple, un dossier nommé Electronics aura une caractéristique de dossier nommée « Caractéristique de dossier électronique ». Vous pouvez afficher et sélectionner la nouvelle caractéristique de dossier dans le tableau de bord Caractéristiques.
1. The new folder trait is automatically assigned to the [!DNL Audience Manager] generated data source. Your users with appropriate [!UICONTROL Role-Based Access Control ([!DNL RBAC])] permissions can change the data source in the edit folder trait workflow. See [Edit a Folder Trait](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Edit a Folder Trait {#edit-folder-trait}

Describes how you can edit a [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. In the [!UICONTROL Traits] dashboard, hover over the **[!UICONTROL Actions]** column for the folder trait you want to edit.
1. Cliquez sur le crayon pour modifier la caractéristique.

   ![](assets/folder_traits_edit_border.png)

1. The **[!UICONTROL Edit]** workflow allows you to change the data source for folder traits. Select your desired data source and click **[!UICONTROL Save]**. Data sources are sorted numerically, by [!DNL DPID], in the drop-down box.

   If your company uses [!UICONTROL Role-Based Access Rights (RBAC)], you or your users need [access permissions](../../features/traits/about-folder-traits.md#role-based-access-controls) to traits data sources.

>[!NOTE]
>
>Vous ne pouvez pas renommer directement une caractéristique de dossier. [Renommez le dossier](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) de stockage associé afin de renommer le dossier.

## Delete a Folder Trait {#delete-folder-trait}

Supprimez une caractéristique de dossier en supprimant le dossier de stockage auquel la caractéristique appartient.

<!-- delete-folder-trait.xml -->

1. **Données d'audience &gt; Caractéristiques** pour accéder au **tableau de bord Caractéristiques** .
1. In the [!UICONTROL Trait Storage] window, delete a folder by hovering over it and clicking the X icon.

   ![Résultat de l'étape](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Vous ne pouvez pas supprimer une caractéristique de dossier, si elle est utilisée dans une expression de segment. Navigate to the [trait view](../../features/traits/trait-details-page.md) section to see which segments use the folder trait. Then, click on the segment name to open the [segment summary view](../../features/segments/segment-summary-view.md), which allows you to remove traits from segment expressions.