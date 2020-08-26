---
description: Créez, modifiez et supprimez des caractéristiques de dossier.
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: Créez, modifiez et supprimez des caractéristiques de dossier.
seo-title: Gestion des caractéristiques de dossier
solution: Audience Manager
title: Gestion des caractéristiques de dossier
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
translation-type: tm+mt
source-git-commit: 4ea5ba4ebd8cd4c13c99c8272f4b5733ab5fa125
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 9%

---


# Gestion des caractéristiques de dossier {#manage-folder-traits}

Créez, modifiez et supprimez des caractéristiques de dossier.

## Créer un profil de dossier {#create-folder-trait}

Une [!UICONTROL folder trait] est créée automatiquement lorsque vous créez un dossier dans votre taxonomie.

<!-- create-folder-trait.xml -->

1. Accédez **[!UICONTROL Audience Data > Traits]** au tableau de bord **Caractéristiques** .
1. Dans la [!UICONTROL Trait Storage] fenêtre, passez la souris sur :

   * Texte &quot;Toutes les caractéristiques&quot; pour ajouter un nouveau dossier de niveau racine.
   * Un dossier parent existant pour ajouter un nouveau dossier Secondaire.

   ![](assets/folder_traits_create.PNG)

1. Cliquez sur l’icône + pour créer le dossier. Vous pouvez créer 2 000 dossiers au maximum dans la taxonomie. Pour plus d’informations, consultez la documentation relative aux [limites d’utilisation](../../features/administration/usage-limits.md).
1. Nommez le dossier et cliquez sur **Enregistrer**. Par exemple, un dossier nommé Electronics aura une caractéristique de dossier nommée &quot;Caractéristique du dossier Electronics&quot;. Vous pouvez vue et sélectionner la nouvelle caractéristique de dossier dans le tableau de bord caractéristiques.
1. La nouvelle caractéristique de dossier est automatiquement affectée à la source de données [!DNL Audience Manager] générée. Vos utilisateurs disposant des autorisations [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) appropriées peuvent modifier la source de données dans le processus de modification de la caractéristique du dossier. Voir [Modification d’une description](../../features/traits/manage-folder-traits.md#edit-folder-trait)de dossier.

## Modification d’une description de dossier {#edit-folder-trait}

Décrit comment modifier un [!UICONTROL folder trait]objet.

<!-- edit-folder-trait.xml -->

1. Dans le [!UICONTROL Traits] tableau de bord, passez la souris sur la **[!UICONTROL Actions]** colonne correspondant à la caractéristique de dossier à modifier.
1. Cliquez sur le crayon pour modifier la caractéristique.

   ![](assets/folder_traits_edit_border.png)

1. Le **[!UICONTROL Edit]** processus vous permet de modifier la source de données pour les caractéristiques des dossiers. Sélectionnez la source de données de votre choix, puis cliquez sur **[!UICONTROL Save]**. Les sources de données sont triées numériquement, par [!DNL DPID], dans la liste déroulante.

   Si votre société utilise [!UICONTROL Role-Based Access Rights (RBAC)], vous ou vos utilisateurs avez besoin d’autorisations [d’](../../features/traits/about-folder-traits.md#role-based-access-controls) accès pour définir les sources de données.

>[!NOTE]
>
>Vous ne pouvez pas renommer directement une caractéristique de dossier. [Renommez son dossier](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) d’enregistrement associé afin de modifier le nom de la caractéristique de dossier.

## Suppression d’une description de dossier {#delete-folder-trait}

Supprimez une caractéristique de dossier en supprimant le dossier d’enregistrement auquel elle appartient.

<!-- delete-folder-trait.xml -->

1. **audience Data > Caractéristiques** pour accéder au tableau de bord **Caractéristiques** .
1. Dans la [!UICONTROL Trait Storage] fenêtre, supprimez un dossier en le survolant et en cliquant sur l’icône X.

   ![Résultat de l’étape](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Vous ne pouvez pas supprimer une caractéristique de dossier, si elle est utilisée dans une expression de segment. Accédez à la section vue [de](../../features/traits/trait-details-page.md) caractéristiques pour savoir quels segments utilisent la caractéristique de dossier. Cliquez ensuite sur le nom du segment pour ouvrir la vue [de résumé du](../../features/segments/segment-summary-view.md)segment, ce qui vous permet de supprimer des caractéristiques des expressions du segment.
