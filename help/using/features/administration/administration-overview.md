---
description: Les options du menu Administration vous permettent de créer des utilisateurs d’Audience Manager et de les affecter à des groupes. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).
keywords: rbac;RBAC;role based;role-based;role-based access controls
seo-description: Les options du menu Administration vous permettent de créer des utilisateurs d’Audience Manager et de les affecter à des groupes. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).
seo-title: Administration
solution: Audience Manager
title: Administration
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1bde60711ca53682b6ab936a7297daf66a1bb336

---


# Administration (contrôles RBAC) {#administration}

![](assets/rbac-controls.png)

Les options du [!UICONTROL Administration] menu vous permettent de créer des utilisateurs d’Audience Manager et de les affecter à des groupes. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).

Les clients d’entreprise qui utilisent [!DNL Audience Manager] une seule plateforme de gestion de données pour toutes leurs données doivent pouvoir contrôler la visibilité des différents éléments de données sur des unités commerciales spécifiques. Pour ce faire, vous pouvez utiliser des autorisations de groupe, également appelées [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilise des groupes pour attribuer des autorisations. Les autorisations ne sont pas attribuées au niveau de l’utilisateur. Les autorisations de groupe sont liées aux objets (caractéristiques, segments, etc.) et aux actions que vous pouvez effectuer sur ces objets (modification, affichage, etc.). Ces commandes sont également disponibles via les API REST d’Audience Manager. Voir Méthodes [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), Gestion [des](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)groupes et API Gestion des [](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) autorisations.

## Create Users {#create-users}

<!-- t_create_users.xml -->

Créez des utilisateurs dans [!DNL Audience Manager] et spécifiez les détails de l’utilisateur, l’état de connexion et affectez des utilisateurs à des groupes.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Cliquez sur ![](assets/icon_add.png) pour afficher la [!UICONTROL Create New User] page.
1. Under **[!UICONTROL User Details]**, fill in the fields:
   * **** Nom d&#39;utilisateur : Spécifiez un nom d’utilisateur unique pour Audience Manager.
   * **** Prénom : Indiquez le prénom de l’utilisateur.
   * **** Nom : Indiquez le nom de famille de l’utilisateur.
   * **** Adresse électronique : Indiquez l’adresse électronique de l’utilisateur. [!DNL Audience Manager] n’envoie pas de notification régulière aux utilisateurs. [!DNL Audience Manager] les administrateurs ont accès aux adresses électroniques des utilisateurs et peuvent envoyer manuellement des courriers électroniques aux utilisateurs selon les besoins. Par exemple, si un utilisateur oublie son mot de passe, l’adresse électronique indiquée dans ce champ est utilisée pour envoyer un mot de passe temporaire et des instructions pour réinitialiser le mot de passe.
   * **** Numéro de téléphone : Indiquez le numéro de téléphone de l’utilisateur.
   * **** Est administrateur : Indiquez si cet utilisateur est un [!DNL Audience Manager] administrateur. Les administrateurs peuvent gérer les utilisateurs (créer, modifier, etc.) et groupes (créer, attribuer des autorisations, etc.). Les utilisateurs non administrateurs ne peuvent contrôler que leurs propres profils, y compris la modification de leurs adresses électroniques et la réinitialisation de leurs propres mots de passe. Pour plus d’informations, voir [Modification des paramètres](../../features/administration/edit-account-settings.md)de votre compte.
1. Sous **[!UICONTROL Login]**, sélectionnez un état :
   * **** Actif :  Les utilisateurs actifs peuvent accéder [!DNL Audience Manager] et bénéficier des autorisations accordées par l’appartenance à un groupe.
   * **** Désactivé :  Les utilisateurs désactivés ne peuvent pas accéder [!DNL Audience Manager] et ne disposent d’aucune autorisation. Si vous désactivez les utilisateurs, leurs informations restent présentes [!DNL Audience Manager] et vous pouvez les réactiver, si nécessaire. Si vous supprimez des utilisateurs, vous devez les recréer s’ils doivent être réutilisés [!DNL Audience Manager] ultérieurement.
   * **** Expiré : Le mot de passe d’un utilisateur a plus de 90 jours.
   * **** En attente : L’utilisateur dispose d’un mot de passe temporaire, soit après la réinitialisation d’un mot de passe, soit sous la forme d’un nouveau compte, et il n’a pas encore défini de mot de passe permanent.
   * **** Verrouillé : 5 tentatives de connexion incorrectes verrouilleront un utilisateur.
1. Sous **[!UICONTROL Assigned Groups]**, dans la liste déroulante, sélectionnez les groupes auxquels vous souhaitez affecter cet utilisateur.
Pour plus d’informations sur les groupes et les autorisations, voir [Création d’un groupe](../../features/administration/administration-overview.md#create-group).
1. Cliquez sur **[!UICONTROL Save]**.

## Création d’un groupe {#create-group}

Un *groupe* est un ensemble d’utilisateurs qui partagent des droits d’accès aux objets de destination, de segment et de caractéristique. Vous pouvez limiter les groupes à des objets uniques ou leur donner un large accès à des combinaisons d’objets différents.

<!-- t_create_groups.xml -->

Création d’un groupe:

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
1. Cliquez sur ![](assets/icon_add.png) pour ouvrir la [!UICONTROL Group Settings] page.
1. Dans [!UICONTROL Group Details]:
   * Nommez le groupe.
   * Fournissez une brève description du groupe.
1. Dans [!UICONTROL Group Members], cliquez sur un utilisateur dans **[!UICONTROL Add Users]** les options pour les ajouter au groupe.
1. Dans [!UICONTROL Group Permissions], sélectionnez une [caractéristique](../../features/traits/trait-details-page.md), un [segment](../../features/segments/segments-purpose.md)ou une [destination](../../features/destinations/destinations.md) depuis .
**[!UICONTROL Add Object]**
Cette opération ouvre une fenêtre d’autorisations pour l’objet sélectionné.
1. Cochez la case correspondant aux autorisations que vous souhaitez que les membres du groupe possèdent.
1. *(Facultatif)* Attribuez des autorisations [de carte](../../features/administration/administration-overview.md#wild-card-permissions) générique au groupe.
1. Cliquez sur **[!UICONTROL Save Group]**.

## Présentation des autorisations de carte génériques {#wild-card-permissions}

Simplifiez la gestion des droits des groupes avec [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] donnent aux membres du groupe un accès automatique à chaque source de données associée à un segment, une destination ou une caractéristique. En comparaison, les autorisations régulières vous permettent uniquement d’affecter des sources de données spécifiques à l’un de ces objets. Et lorsque vous ajoutez de nouvelles sources de données, les membres du groupe n’ont pas accès à ces nouvelles sources.

Vous devez ouvrir les autorisations du groupe et affecter ces nouvelles sources de données au groupe. [!UICONTROL Wild Card Permissions] évitez ce processus manuel de mise à jour de la source de données. Les groupes qui [!UICONTROL Wild Card Permissions] ont accès à de nouvelles sources de données sans autorisation explicite.

![](assets/wild-card.png)

Lisez ci-dessous la description de chaque autorisation de caractères génériques :

**Caractéristique**

* `MAP_ALL_TRAITS_TO_MODELS` - Les utilisateurs peuvent sélectionner des caractéristiques comme base de référence pour les modèles.
* `EDIT_ALL_TRAITS` - Les utilisateurs peuvent modifier toutes les caractéristiques configurées dans leur compte d’entreprise.
* `VIEW_ALL_TRAITS` - Les utilisateurs peuvent afficher toutes les caractéristiques configurées dans leur compte d’entreprise.
* `DELETE_ALL_TRAITS` - Les utilisateurs peuvent supprimer toutes les caractéristiques configurées dans leur compte d’entreprise.
* `CREATE_ALL_ALGO_TRAITS` - Les utilisateurs peuvent créer des caractéristiques algorithmiques.
* `MAP_ALL_TO_SEGMENTS` - Les utilisateurs peuvent ajouter aux segments n’importe laquelle des caractéristiques appartenant à leur entreprise.
* `CREATE_ALL_TRAITS` - Les utilisateurs peuvent créer des caractéristiques.

**Rapports**

* `PTRREPORTS` - Cette autorisation de caractères génériques fait référence à une fonctionnalité obsolète et sera supprimée prochainement de l’interface utilisateur d’Audience Manager.

**Modèles**

* `VIEW_MODELS` - Les utilisateurs sont autorisés à afficher les modèles appartenant à leur entreprise.

**Signaux dérivés**

* `VIEW_DERIVED_SIGNALS` - Les utilisateurs peuvent afficher tous les signaux dérivés de leur entreprise.
* `CREATE_DERIVED_SIGNALS` - Les utilisateurs peuvent créer des signaux dérivés.
* `EDIT_DERIVED_SIGNALS` - Les utilisateurs peuvent modifier tous les signaux dérivés de leur entreprise.
* `DELETE_DERIVED_SIGNALS` - Les utilisateurs peuvent supprimer les signaux dérivés de leur entreprise.

**Destination**

* `EDIT_ALL_DESTINATIONS` - Les utilisateurs peuvent modifier toutes les destinations configurées dans leur compte d’entreprise.
* `CREATE_DESTINATIONS` - Les utilisateurs peuvent créer des destinations.
* `VIEW_ALL_DESTINATIONS` - Les utilisateurs peuvent afficher toutes les destinations configurées dans leur compte d’entreprise.
* `DELETE_ALL_DESTINATIONS` - Les utilisateurs peuvent supprimer toutes les destinations configurées dans leur compte d’entreprise.

**Balises**

* `VIEW_TAGS` - Les utilisateurs peuvent tout faire (afficher, créer, modifier, supprimer) sur leurs conteneurs de balises.

**Audience Lab**

* `MANAGE_SEGMENT_TEST_GROUPS` - Les utilisateurs peuvent tout faire (afficher, créer, modifier, supprimer) sur leurs groupes de tests Audience Lab.

**Segment**

* `CREATE_ALL_SEGMENTS` - Les utilisateurs peuvent créer des segments.
* `DELETE_ALL_SEGMENTS` - Les utilisateurs peuvent supprimer tous les segments configurés dans leur compte d’entreprise.
* `MAP_ALL_TO_DESTINATIONS` - Les utilisateurs peuvent mapper n’importe quel segment appartenant à leur entreprise vers des destinations.
* `EDIT_ALL_SEGMENTS` - Les utilisateurs peuvent modifier tous les segments configurés dans leur compte d’entreprise.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Les utilisateurs peuvent sélectionner des segments comme référence pour les modèles.
* `VIEW_ALL_SEGMENTS` - Les utilisateurs peuvent afficher tous les segments configurés dans leur compte d’entreprise.

**Signaux**

* `VIEW_ALL_SIGNALS` - Les utilisateurs peuvent afficher tous les signaux capturés dans [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Cas d’utilisation {#use-cases}

### Contrôle de l’accès des utilisateurs {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] Vous pouvez surveiller l’état de connexion de l’utilisateur, en vous donnant une idée claire de qui peut accéder à votre instance d’Audience Manager.

Selon les besoins de votre entreprise, vous pouvez activer et désactiver les comptes d’utilisateurs, selon les besoins.

![moniteur-accès utilisateur](assets/monitor-user-access.png)

### Protection de l’accès pour les sources de données sensibles {#protect-sensitive-data-sources}

Vous pouvez configurer [!UICONTROL Role-Based Access Control] au niveau de la caractéristique, du segment et de la destination, pour chaque groupe d’utilisateurs.

Cette fonctionnalité vous permet de gérer la manière dont vos utilisateurs visualisent, créent, lisent, écrivent et modifient des jeux de données spécifiques, et même de limiter l&#39;accès des utilisateurs aux jeux de données qui ne devraient pas être accessibles.

![protection d&#39;accès](assets/access-protection.png)
