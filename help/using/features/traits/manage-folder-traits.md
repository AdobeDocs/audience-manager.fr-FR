---
description: Créez, modifiez et supprimez des caractéristiques de dossier.
keywords: Caractéristique du dossier;caractéristiques du dossier;caractéristiques du dossier;caractéristique du dossier
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: Gestion des caractéristiques de dossier
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: f7a4478589f4af1d467f1045a97dbb7f5cd6f9e5
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---

# Gestion des caractéristiques de dossier {#manage-folder-traits}

Créez, modifiez et supprimez des caractéristiques de dossier.

## Création d’une caractéristique de dossier {#create-folder-trait}

Un [!UICONTROL folder trait] est automatiquement créé lorsque vous créez un dossier dans votre taxonomie.

<!-- create-folder-trait.xml -->

1. Accédez à **[!UICONTROL Audience Data > Traits]** pour accéder au tableau de bord **Caractéristiques**.
1. Dans la fenêtre [!UICONTROL Trait Storage], passez la souris sur :

   * Texte &quot;Toutes les caractéristiques&quot; pour ajouter un nouveau dossier de niveau racine.
   * Dossier parent existant auquel ajouter un nouveau dossier subordonné.

   ![](assets/folder_traits_create.PNG)

1. Cliquez sur l’icône + pour créer le dossier. Notez que vous pouvez créer un maximum de 2 000 dossiers dans votre taxonomie. Pour plus d’informations, consultez la documentation relative aux [limites d’utilisation](../../features/administration/usage-limits.md).
1. Nommez le dossier et cliquez sur **Enregistrer**. Par exemple, un dossier nommé Electronics comporte une caractéristique de dossier nommée &quot;Electronics Folder Trait&quot;. Vous pouvez afficher et sélectionner la nouvelle caractéristique de dossier dans le tableau de bord des caractéristiques.
1. La nouvelle caractéristique de dossier est automatiquement affectée à la source de données générée par [!DNL Audience Manager]. Vos utilisateurs disposant des autorisations [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) appropriées peuvent modifier la source de données dans le processus de modification des caractéristiques du dossier. Voir [Modification d’une caractéristique de dossier](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Modification d’une caractéristique de dossier {#edit-folder-trait}

Décrit comment modifier un [!UICONTROL folder trait].

<!-- edit-folder-trait.xml -->

1. Dans le tableau de bord [!UICONTROL Traits], passez la souris sur la colonne **[!UICONTROL Actions]** de la caractéristique de dossier que vous souhaitez modifier.
1. Cliquez sur le crayon pour modifier la caractéristique.

   ![](assets/folder_traits_edit_border.png)

1. Le workflow **[!UICONTROL Edit]** vous permet de modifier la source de données pour les caractéristiques du dossier. Sélectionnez la source de données de votre choix et cliquez sur **[!UICONTROL Save]**. Les sources de données sont triées numériques, par [!DNL DPID], dans la liste déroulante.

   Si votre entreprise utilise [!UICONTROL Role-Based Access Rights (RBAC)], vous ou vos utilisateurs avez besoin de [autorisations d’accès](../../features/traits/about-folder-traits.md#role-based-access-controls) pour définir les sources de données.

>[!NOTE]
>
>Vous ne pouvez pas renommer directement une caractéristique de dossier. [Renommez son dossier de stockage associé](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) afin de modifier le nom de la caractéristique du dossier.

## Suppression d’une caractéristique de dossier {#delete-folder-trait}

Supprimez une caractéristique de dossier en supprimant le dossier de stockage auquel elle appartient.

<!-- delete-folder-trait.xml -->

1. **Données d’audience > Caractéristiques** pour accéder au tableau de bord **Caractéristiques**.
1. Dans la fenêtre [!UICONTROL Trait Storage], supprimez un dossier en le survolant et en cliquant sur l’icône X.

   ![Résultat de l’étape](assets/folder_traits_create.PNG)

>[!NOTE]
>
>Vous ne pouvez pas supprimer une caractéristique de dossier si elle est utilisée dans une expression de segment. Accédez à la section [vue de caractéristique](../../features/traits/trait-details-page.md) pour voir les segments qui utilisent la caractéristique de dossier. Cliquez ensuite sur le nom du segment pour ouvrir la [vue récapitulative du segment](../../features/segments/segment-summary-view.md), qui vous permet de supprimer des caractéristiques des expressions du segment.
