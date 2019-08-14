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
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Administration (commandes RBAC) {#administration}

![](assets/rbac-controls.png)

Les options du [!UICONTROL Administration] menu vous permettent de créer des utilisateurs Audience Manager et de les affecter aux groupes. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).

Clients d'entreprise qui utilisent [!DNL Audience Manager] une plateforme de gestion de données pour toutes leurs données, mais doivent pouvoir contrôler la visibilité des différents éléments de données à des unités opérationnelles spécifiques. Vous pouvez y effectuer des autorisations de groupe, également appelées [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilise des groupes pour attribuer des autorisations. Les autorisations ne sont pas attribuées au niveau de l'utilisateur. Les autorisations de groupe sont liées aux objets (caractéristiques, segments, etc.) et aux actions que vous pouvez effectuer sur ces objets (modification, affichage, etc.). Ces contrôles sont également disponibles via les API REST d'Audience Manager. Voir [Méthodes de l'API Gestion des utilisateurs](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gestion](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)[des groupes et Gestion](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) des permissions.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Créez des utilisateurs dans [!DNL Audience Manager] et spécifiez les détails de l'utilisateur, le statut de connexion et affectez des utilisateurs aux groupes.

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Users]**.
1. Cliquez sur ![](assets/icon_add.png) pour afficher [!UICONTROL Create New User] la page.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **Nom d'utilisateur :** Indiquez un nom d'utilisateur unique pour Audience Manager.
   * **Prénom :** Indiquez le prénom de l'utilisateur.
   * **Nom :** Indiquez le nom de l'utilisateur.
   * **Adresse électronique :** Indiquez l'adresse électronique de l'utilisateur. [!DNL Audience Manager] n'envoie pas de notification régulière aux utilisateurs. [!DNL Audience Manager] les administrateurs ont accès aux adresses électroniques des utilisateurs et peuvent manuellement envoyer les utilisateurs par messagerie électronique. Par exemple, si un utilisateur oublie son mot de passe, l'adresse électronique spécifiée dans ce champ est utilisée pour envoyer un mot de passe temporaire et des instructions pour réinitialiser le mot de passe.
   * **Numéro de téléphone :** Indiquez le numéro de téléphone de l'utilisateur.
   * **Est Admin :** Indiquez si cet utilisateur est [!DNL Audience Manager] un administrateur. Les utilisateurs administrateurs peuvent gérer les utilisateurs (création, modification, etc.) et les groupes (créez, attribuez des autorisations, etc.). Les utilisateurs non administrateurs ne peuvent contrôler que leurs propres profils d'utilisateurs, y compris la modification de leurs adresses électroniques et la réinitialisation de leurs propres mots de passe. Pour plus d'informations, voir [Modification des paramètres de votre compte](../../features/administration/edit-account-settings.md).
1. Sous **[!UICONTROL Login]**, sélectionnez l'état de votre choix :
   * **Actif :** Les utilisateurs actifs peuvent accéder [!DNL Audience Manager] aux autorisations et les disposer d'autorisations par adhésion au groupe.
   * **Désactivé :** Les utilisateurs désactivés ne peuvent pas accéder [!DNL Audience Manager] à et ne disposent pas d'autorisations. Si vous désactivez les utilisateurs, leurs informations utilisateur restent dans [!DNL Audience Manager] et vous pouvez les réactiver simple, si nécessaire. Si vous supprimez des utilisateurs, vous devez les recréer s'ils doivent réutiliser [!DNL Audience Manager] ultérieurement.
   * **Expiré :** Le mot de passe d'un utilisateur est supérieur à 90 jours.
   * **En attente :** L'utilisateur dispose d'un mot de passe temporaire, soit après une réinitialisation du mot de passe, soit comme un nouveau compte, et qu'il n'a pas encore défini de mot de passe permanent.
   * **Verrouillé :** 5 tentatives de connexion incorrectes verrouillent un utilisateur.
1. Sous **[!UICONTROL Assigned Groups]**, dans la liste déroulante, sélectionnez les groupes auxquels vous souhaitez affecter cet utilisateur.
Pour plus d'informations sur les groupes et autorisations, voir [Création d'un groupe](../../features/administration/administration-overview.md#create-group).
1. Cliquez sur **[!UICONTROL Save]**.

## Création d’un groupe {#create-group}

Un *groupe* est un ensemble d'utilisateurs qui partagent des droits d'accès aux objets de destination, de segment et de caractéristique. Vous pouvez limiter les groupes aux objets uniques uniquement ou leur donner un accès large aux combinaisons d'objets différents.

<!-- t_create_groups.xml -->

Création d’un groupe:

1. Click **[!UICONTROL Administration]** &gt; **[!UICONTROL Groups]**.
1. Cliquez sur ![](assets/icon_add.png) pour ouvrir [!UICONTROL Group Settings] la page.
1. Dans [!UICONTROL Group Details]:
   * Nommez le groupe.
   * Fournissez une brève description de groupe.
1. Dans [!UICONTROL Group Members], cliquez sur un utilisateur à partir **[!UICONTROL Add Users]** des options pour les ajouter au groupe.
1. Dans [!UICONTROL Group Permissions], sélectionnez [une caractéristique](../../features/traits/trait-details-page.md), [un segment](../../features/segments/segments-purpose.md)ou [une destination](../../features/destinations/destinations.md) .
**[!UICONTROL Add Object]**
Vous ouvrez alors une fenêtre d'autorisations pour l'objet sélectionné.
1. Cochez la case correspondant aux autorisations que vous souhaitez accorder aux membres du groupe.
1. *(Facultatif)* Attribuez [des autorisations](../../features/administration/administration-overview.md#wild-card-permissions) génériques au groupe.
1. Cliquez sur **[!UICONTROL Save Group]**.

## Présentation des autorisations génériques {#wild-card-permissions}

Simplifiez la gestion des droits de groupe.[!UICONTROL Wild Card Permissions]

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] donner aux membres du groupe l'accès automatique à chaque source de données associée à un segment, une destination ou une caractéristique. Par comparaison, les autorisations régulières vous permettent d'affecter des sources de données spécifiques à l'un de ces objets. De plus, lorsque vous ajoutez de nouvelles sources de données, les membres du groupe n'ont pas accès à ces nouvelles sources.

Vous devez ouvrir les autorisations du groupe et affecter ces nouvelles sources de données au groupe. [!UICONTROL Wild Card Permissions] vous permet d'éviter ce processus de mise à jour manuelle de la source de données. Groupes ayant [!UICONTROL Wild Card Permissions] accès aux nouvelles sources de données sans autorisation explicite.

![](assets/wild-card.png)

Lisez la description ci-dessous pour obtenir une description de l'autorisation de chaque caractère générique :

**Caractéristique**

* `MAP_ALL_TRAITS_TO_MODELS` - Les utilisateurs peuvent sélectionner des caractéristiques comme ligne de base pour les modèles.
* `EDIT_ALL_TRAITS` - Les utilisateurs peuvent modifier toutes les caractéristiques configurées dans leur compte de société.
* `VIEW_ALL_TRAITS` - Les utilisateurs peuvent afficher toutes les caractéristiques configurées dans leur compte de société.
* `DELETE_ALL_TRAITS` - Les utilisateurs peuvent supprimer toutes les caractéristiques configurées dans leur compte de société.
* `CREATE_ALL_ALGO_TRAITS` - Les utilisateurs peuvent créer des caractéristiques algorithmiques.
* `MAP_ALL_TO_SEGMENTS` - Les utilisateurs peuvent ajouter n'importe quelle caractéristique appartenant à leur entreprise aux segments.
* `CREATE_ALL_TRAITS` - Les utilisateurs peuvent créer des caractéristiques.

**Rapports**

* `PTRREPORTS` - Cette autorisation de caractère générique fait référence à des fonctionnalités obsolètes et sera supprimée rapidement de l'interface utilisateur d'Audience Manager.

**Modèles**

* `VIEW_MODELS` - Les utilisateurs sont autorisés à afficher les modèles appartenant à leur entreprise.

**Signaux dérivés**

* `VIEW_DERIVED_SIGNALS` - Les utilisateurs peuvent afficher tous les signaux dérivés appartenant à leur entreprise.
* `CREATE_DERIVED_SIGNALS` - Les utilisateurs peuvent créer des signaux dérivés.
* `EDIT_DERIVED_SIGNALS` - Les utilisateurs peuvent modifier tous les signaux dérivés appartenant à leur entreprise.
* `DELETE_DERIVED_SIGNALS` - Les utilisateurs peuvent supprimer l'un des signaux dérivés appartenant à leur entreprise.

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
* `MAP_ALL_TO_DESTINATIONS` - Les utilisateurs peuvent mapper l'un des segments appartenant à leur entreprise aux destinations.
* `EDIT_ALL_SEGMENTS` - Les utilisateurs peuvent modifier tous les segments configurés dans leur compte de société.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Les utilisateurs peuvent sélectionner des segments comme ligne de base pour les modèles.
* `VIEW_ALL_SEGMENTS` - Les utilisateurs peuvent afficher tous les segments configurés dans leur compte de société.

**Signaux**

* `VIEW_ALL_SIGNALS` - Les utilisateurs peuvent afficher tous les signaux capturés dans [l'Explorateur de données](/help/using/features/data-explorer/data-explorer-overview.md).