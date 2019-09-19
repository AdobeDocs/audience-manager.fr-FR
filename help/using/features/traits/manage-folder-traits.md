---
description: Créez, modifiez et supprimez des caractéristiques de dossier.
keywords: Caractéristique du dossier;Caractéristiques du dossier;caractéristiques du dossier;caractéristiques du dossier
seo-description: Créez, modifiez et supprimez des caractéristiques de dossier.
seo-title: Gérer les caractéristiques des dossiers
solution: Audience Manager
title: Gérer les caractéristiques des dossiers
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Gérer les caractéristiques des dossiers {#manage-folder-traits}

Créez, modifiez et supprimez des caractéristiques de dossier.

## Création d’un profil de dossier {#create-folder-trait}

Une [!UICONTROL folder trait] est créée automatiquement lorsque vous créez un dossier dans votre taxonomie.

<!-- create-folder-trait.xml -->

1. Accédez **[!UICONTROL Audience Data > Traits]** au tableau de bord **Caractéristiques** .
1. Dans la [!UICONTROL Trait Storage] fenêtre, passez la souris sur :

   * Texte "Toutes les caractéristiques" pour ajouter un nouveau dossier de niveau racine.
   * Un dossier parent existant pour ajouter un nouveau dossier subordonné.
   ![](assets/folder_traits_create.PNG)

1. Cliquez sur l’icône + pour créer le dossier. Vous pouvez créer 2 000 dossiers au maximum dans la taxonomie. Pour plus d’informations, consultez la documentation relative aux [limites d’utilisation](../../features/administration/usage-limits.md).
1. Nommez le dossier et cliquez sur **Enregistrer**. Par exemple, un dossier nommé Electronics aura une caractéristique de dossier nommée "Caractéristique du dossier Electronique". Vous pouvez afficher et sélectionner la nouvelle caractéristique de dossier dans le tableau de bord Caractéristiques.
1. La nouvelle caractéristique de dossier est automatiquement affectée à la source de données [!DNL Audience Manager] générée. Vos utilisateurs disposant des autorisations appropriées de [!UICONTROL Role-Based Access Control ([!DNL RBAC])] peuvent modifier la source de données dans le flux de travaux de modification des caractéristiques du dossier. Voir [Modification d’une description](../../features/traits/manage-folder-traits.md#edit-folder-trait)de dossier.

## Modification d’une description de dossier {#edit-folder-trait}

Décrit comment modifier une [!UICONTROL folder trait]balise .

<!-- edit-folder-trait.xml -->

1. Dans le [!UICONTROL Traits] tableau de bord, passez la souris sur la **[!UICONTROL Actions]** colonne correspondant à la caractéristique de dossier à modifier.
1. Cliquez sur le crayon pour modifier la caractéristique.

   ![](assets/folder_traits_edit_border.png)

1. Le **[!UICONTROL Edit]** processus vous permet de modifier la source de données pour les caractéristiques des dossiers. Sélectionnez la source de données de votre choix, puis cliquez sur **[!UICONTROL Save]**. Les sources de données sont triées numériquement, par [!DNL DPID], dans la liste déroulante.

   Si votre entreprise l’utilise [!UICONTROL Role-Based Access Rights (RBAC)], vous ou vos utilisateurs avez besoin d’autorisations [d’](../../features/traits/about-folder-traits.md#role-based-access-controls) accès aux caractéristiques des sources de données.

>[!NOTE]
>
>Vous ne pouvez pas renommer directement une caractéristique de dossier. [Renommez le dossier](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) de stockage associé afin de modifier le nom de la caractéristique du dossier.

## Suppression d’une description de dossier {#delete-folder-trait}

Supprimez une caractéristique de dossier en supprimant le dossier de stockage auquel elle appartient.

<!-- delete-folder-trait.xml -->

1. **Données d’audience &gt; Caractéristiques** pour accéder au tableau de bord **Caractéristiques** .
1. Dans la [!UICONTROL Trait Storage] fenêtre, supprimez un dossier en le survolant et en cliquant sur l’icône X.

   ![Résultat de l’étape](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Vous ne pouvez pas supprimer une caractéristique de dossier, si elle est utilisée dans une expression de segment. Accédez à la section Affichage [des](../../features/traits/trait-details-page.md) caractéristiques pour savoir quels segments utilisent la caractéristique de dossier. Cliquez ensuite sur le nom du segment pour ouvrir la vue [Résumé du](../../features/segments/segment-summary-view.md)segment, qui vous permet de supprimer des caractéristiques des expressions de segment.