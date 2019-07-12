---
description: Les options du menu Administration vous permettent de créer des utilisateurs Audience Manager et de les affecter aux groupes. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).
keywords: rbac ; RBAC ; role based ; role-based ; contrôles d'accès basés sur un rôle
seo-description: Les options du menu Administration vous permettent de créer des utilisateurs Audience Manager et de les affecter aux groupes. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).
seo-title: Administration
solution: Audience Manager
title: Administration
topic: API DIL
uuid: 498 e 0316-cf 1 b -43 e 9-88 ba -338 ee 0 daf 225
translation-type: tm+mt
source-git-commit: 5d66c44a9072129de9da69918e9eeda2e18ccb22

---


# Administration (RBAC Controls) {#administration}

![](assets/rbac-controls.png)

The options under the [!UICONTROL Administration] menu let you create Audience Manager users and assign them to groups. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).

Enterprise customers using [!DNL Audience Manager] need one data management platform for all of their data, but must be able to control the visibility of the different data elements to specific business units. You can accomplish this using group permissions, also referred to as [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilise des groupes pour attribuer des autorisations. Les autorisations ne sont pas attribuées au niveau de l&#39;utilisateur. Les autorisations de groupe sont liées aux objets (caractéristiques, segments, etc.) et aux actions que vous pouvez effectuer sur ces objets (modification, affichage, etc.). Ces contrôles sont également disponibles via les API REST d&#39;Audience Manager. See [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Group Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), and [Permissions Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API methods.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Create users in [!DNL Audience Manager] and specify user details, login status, and assign users to groups.

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Click ![](assets/icon_add.png) to display the [!UICONTROL Create New User] page.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Nom d&#39;utilisateur :** Indiquez un nom d&#39;utilisateur unique pour Audience Manager.
   * **Prénom :** Indiquez le prénom de l&#39;utilisateur.
   * **Nom :** Indiquez le nom de l&#39;utilisateur.
   * **Adresse électronique :** Indiquez l&#39;adresse électronique de l&#39;utilisateur. [!DNL Audience Manager] n&#39;envoie pas de notification régulière aux utilisateurs. [!DNL Audience Manager] les administrateurs ont accès aux adresses électroniques des utilisateurs et peuvent manuellement envoyer les utilisateurs par messagerie électronique. Par exemple, si un utilisateur oublie son mot de passe, l&#39;adresse électronique spécifiée dans ce champ est utilisée pour envoyer un mot de passe temporaire et des instructions pour réinitialiser le mot de passe.
   * **Numéro de téléphone :** Indiquez le numéro de téléphone de l&#39;utilisateur.
   * **Est Admin :** Indiquez si cet utilisateur est [!DNL Audience Manager] un administrateur. Les utilisateurs administrateurs peuvent gérer les utilisateurs (création, modification, etc.) et les groupes (créez, attribuez des autorisations, etc.). Les utilisateurs non administrateurs ne peuvent contrôler que leurs propres profils d&#39;utilisateurs, y compris la modification de leurs adresses électroniques et la réinitialisation de leurs propres mots de passe. For more information, see [Edit Your Account Settings](../../features/administration/edit-account-settings.md).
1. Under **[!UICONTROL Login]**, select the desired status:
   * **Actif :** Les utilisateurs actifs peuvent accéder [!DNL Audience Manager] aux autorisations et les disposer d&#39;autorisations par adhésion au groupe.
   * **Désactivé :** Les utilisateurs désactivés ne peuvent pas accéder [!DNL Audience Manager] à et ne disposent pas d&#39;autorisations. If you deactivate users, their user information remains in [!DNL Audience Manager] and you can simple reactivate them, if necessary. If you remove users, you must re-create them if they need to use [!DNL Audience Manager] again in the future.
   * **Expiré :** Le mot de passe d&#39;un utilisateur est supérieur à 90 jours.
   * **En attente :** L&#39;utilisateur dispose d&#39;un mot de passe temporaire, soit après une réinitialisation du mot de passe, soit comme un nouveau compte, et qu&#39;il n&#39;a pas encore défini de mot de passe permanent.
   * **Verrouillé :** 5 tentatives de connexion incorrectes verrouillent un utilisateur.
1. Under **[!UICONTROL Assigned Groups]**, from the drop-down list, select the desired groups to which you want to assign this user.
For more information about groups and permissions, see [Create a Group](../../features/administration/administration-overview.md#create-group).
1. Cliquez sur **[!UICONTROL Save]**.

## Création d’un groupe {#create-group}

A *group* is a collection of users that share access rights to destination, segment, and trait objects. Vous pouvez limiter les groupes aux objets uniques uniquement ou leur donner un accès large aux combinaisons d&#39;objets différents.

<!-- t_create_groups.xml -->

Création d’un groupe:

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Click  ![](assets/icon_add.png) to open the [!UICONTROL Group Settings] page.
1. Dans [!UICONTROL Group Details]:
   * Nommez le groupe.
   * Fournissez une brève description de groupe.
1. In [!UICONTROL Group Members], click a user from **[!UICONTROL Add Users]** options to add them to the group.
1. In [!UICONTROL Group Permissions], select a [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md), or [destination](../../features/destinations/destinations.md) from **[!UICONTROL Add Object]**.
Vous ouvrez alors une fenêtre d&#39;autorisations pour l&#39;objet sélectionné.
1. Cochez la case correspondant aux autorisations que vous souhaitez accorder aux membres du groupe.
1. *(Facultatif)* Attribuez [des autorisations](../../features/administration/administration-overview.md#wild-card-permissions) génériques au groupe.
1. Cliquez sur **[!UICONTROL Save Group]**.

## Understanding Wild Card Permissions {#wild-card-permissions}

Simplify group rights management with [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] donner aux membres du groupe l&#39;accès automatique à chaque source de données associée à un segment, une destination ou une caractéristique. Par comparaison, les autorisations régulières vous permettent d&#39;affecter des sources de données spécifiques à l&#39;un de ces objets. De plus, lorsque vous ajoutez de nouvelles sources de données, les membres du groupe n&#39;ont pas accès à ces nouvelles sources.

Vous devez ouvrir les autorisations du groupe et affecter ces nouvelles sources de données au groupe. [!UICONTROL Wild Card Permissions] vous permet d&#39;éviter ce processus de mise à jour manuelle de la source de données. Groups with [!UICONTROL Wild Card Permissions] get access to new data sources without explicit authorization.

![](assets/wild-card.png)

Lisez la description ci-dessous pour obtenir une description de l&#39;autorisation de chaque caractère générique :

**Caractéristique**

* `MAP_ALL_TRAITS_TO_MODELS` - Les utilisateurs peuvent sélectionner des caractéristiques comme ligne de base pour les modèles.
* `EDIT_ALL_TRAITS` - Les utilisateurs peuvent modifier toutes les caractéristiques appartenant à leur entreprise (PID).
* `VIEW_ALL_TRAITS` - Les utilisateurs peuvent afficher toutes les caractéristiques appartenant à leur entreprise (PID).
* `DELETE_ALL_TRAITS` - Les utilisateurs peuvent supprimer toutes les caractéristiques appartenant à leur entreprise.
* `CREATE_ALL_ALGO_TRAITS` - Les utilisateurs peuvent créer des caractéristiques algorithmiques.
* `MAP_ALL_TO_SEGMENTS` - Les utilisateurs peuvent ajouter n&#39;importe quelle caractéristique appartenant à leur entreprise aux segments.
* `CREATE_ALL_TRAITS` - Les utilisateurs peuvent créer des caractéristiques.

**Rapports**

* `PTRREPORTS` - Cette autorisation de caractère générique fait référence à des fonctionnalités obsolètes et sera supprimée rapidement de l&#39;interface utilisateur d&#39;Audience Manager.

**Modèles**

* `VIEW_MODELS` - Les utilisateurs sont autorisés à afficher les modèles appartenant à leur entreprise.

**Signaux dérivés**

* `VIEW_DERIVED_SIGNALS` - Les utilisateurs peuvent afficher tous les signaux dérivés appartenant à leur entreprise.
* `CREATE_DERIVED_SIGNALS` - Les utilisateurs peuvent créer des signaux dérivés.
* `EDIT_DERIVED_SIGNALS` - Les utilisateurs peuvent modifier tous les signaux dérivés appartenant à leur entreprise.
* `DELETE_DERIVED_SIGNALS` - Les utilisateurs peuvent supprimer l&#39;un des signaux dérivés appartenant à leur entreprise.

**Destination**

* `EDIT_ALL_DESTINATIONS` - Les utilisateurs peuvent modifier toutes les configurations de destination dans leur compte de société.
* `CREATE_DESTINATIONS` - Les utilisateurs peuvent créer des destinations.
* `VIEW_ALL_DESTINATIONS` - Les utilisateurs peuvent afficher toutes les destinations configurées au sein de leur compte de société.
* `DELETE_ALL_DESTINATIONS` - Les utilisateurs peuvent supprimer toutes les configurations de destinations au sein de leur compte de société.

**Balises**

* `VIEW_TAGS` - Les utilisateurs peuvent tout faire (afficher, créer, modifier, supprimer) dans leurs conteneurs de balises.

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - Les utilisateurs peuvent tout faire (afficher, créer, modifier, supprimer) dans leurs groupes de test Audience Lab.

**Segment**

* `CREATE_ALL_SEGMENTS` - Les utilisateurs peuvent créer des segments.
* `DELETE_ALL_SEGMENTS` - Les utilisateurs peuvent supprimer tous les segments configurés dans leur compte de société.
* `MAP_ALL_TO_DESTINATIONS` - Les utilisateurs peuvent mapper l&#39;un des segments appartenant à leur entreprise aux destinations.
* `EDIT_ALL_SEGMENTS` - Les utilisateurs peuvent modifier tous les segments configurés dans leur compte de société.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Les utilisateurs peuvent sélectionner des segments comme ligne de base pour les modèles.
* `VIEW_ALL_SEGMENTS` - Les utilisateurs peuvent afficher tous les segments configurés dans leur compte de société.

**Signaux**

* `VIEW_ALL_SIGNALS` - Les utilisateurs peuvent afficher tous les signaux capturés dans [l&#39;Explorateur de données](/help/using/features/data-explorer/data-explorer-overview.md).