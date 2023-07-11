---
description: Les options du menu Administration vous permettent de créer des utilisateurs d’Audience Manager et de les affecter à des groupes. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).
keywords: rbac;RBAC;basé sur les rôles;basé sur les rôles;contrôle d’accès basé sur les rôles
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: Administration
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1187'
ht-degree: 2%

---

# [!UICONTROL Administration] (Contrôles RBAC) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> La gestion des comptes d’utilisateurs se déplace vers le [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Pour commencer la migration des utilisateurs, nous demandons à tous les clients d’Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Audience Manager de la migration des utilisateurs vers Admin Console](admin-console-migration.md).
> 
> Une fois tous les clients migrés, les sections de gestion des utilisateurs de ce document disparaîtront.

>[!IMPORTANT]
>
> Avant d’utiliser [!DNL RBAC], cette fonctionnalité doit être activée par Adobe pour votre organisation. Contactez l’équipe de votre compte pour demander. [!DNL RBAC] ou contactez l’assistance clientèle.


Les options situées sous la propriété [!UICONTROL Administration] vous permet de créer des utilisateurs d’Audience Manager et de les affecter à des groupes. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).

Clients d’entreprise utilisant [!DNL Audience Manager] nécessitent une plateforme de gestion des données unique pour toutes leurs données, mais doivent pouvoir contrôler la visibilité des différents éléments de données sur des entités commerciales spécifiques. Pour ce faire, vous pouvez utiliser les autorisations de groupe, également appelées [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilise des groupes pour attribuer des autorisations. Les autorisations ne sont pas affectées au niveau de l’utilisateur. Les autorisations de groupe sont liées à des objets ([!UICONTROL traits], segments, etc.) et aux actions que vous pouvez effectuer sur ces objets (édition, affichage, etc.). Ces commandes sont également disponibles via les API REST d’Audience Manager. Voir [Gestion des utilisateurs](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gestion des groupes](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md), et [Gestion des autorisations](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) méthodes API.

## Création d’utilisateurs {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> La gestion des comptes d’utilisateurs se déplace vers le [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Pour commencer la migration des utilisateurs, nous demandons à tous les clients d’Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Audience Manager de la migration des utilisateurs vers Admin Console](admin-console-migration.md).
> 
> Une fois tous les clients migrés, la section de gestion des utilisateurs de ce document disparaîtra.
> 
Création d’utilisateurs dans [!DNL Audience Manager] et spécifiez les détails de l’utilisateur, l’état de connexion et affectez des utilisateurs à des groupes.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Cliquez sur ![](assets/icon_add.png) pour afficher la variable [!UICONTROL Create New User] page.
1. Sous **[!UICONTROL User Details]**, renseignez les champs suivants :
   * **[!UICONTROL Username]:** Spécifiez un nom d’utilisateur unique pour l’Audience Manager.
   * **[!UICONTROL First Name]:** Indiquez le prénom de l’utilisateur.
   * **[!UICONTROL Last Name]:** Indiquez le nom de l’utilisateur.
   * **[!UICONTROL Email Address]:** Indiquez l’adresse électronique de l’utilisateur. [!DNL Audience Manager] n’envoie pas de notification régulière aux utilisateurs. [!DNL Audience Manager] Les administrateurs ont accès aux adresses électroniques des utilisateurs et peuvent envoyer manuellement des adresses électroniques aux utilisateurs, si nécessaire. Par exemple, si un utilisateur oublie son mot de passe, l’adresse électronique indiquée dans ce champ est utilisée pour envoyer un mot de passe temporaire et des instructions pour réinitialiser le mot de passe.
   * **[!UICONTROL Phone Number]:** Indiquez le numéro de téléphone de l’utilisateur.
   * **[!UICONTROL Is Admin]:** Spécifiez si cet utilisateur est un [!DNL Audience Manager] administrateur. Les utilisateurs administrateurs peuvent gérer les utilisateurs (créer, modifier, etc.) et les groupes (créer, attribuer des autorisations, etc.). Les utilisateurs non-administrateurs peuvent contrôler uniquement leurs propres profils utilisateur, y compris la modification de leurs adresses électroniques et la réinitialisation de leurs propres mots de passe. Pour plus d’informations, voir [Modification des paramètres de votre compte](../../features/administration/edit-account-settings.md).
1. Sous **[!UICONTROL Login]**, sélectionnez l’état souhaité :
   * **[!UICONTROL Active]:**  Les utilisateurs principaux peuvent accéder à [!DNL Audience Manager] et ont les autorisations accordées par appartenance à un groupe.
   * **[!UICONTROL Deactivated]:**  Les utilisateurs désactivés ne peuvent pas accéder à [!DNL Audience Manager] et ne disposent d’aucune autorisation. Si vous désactivez des utilisateurs, leurs informations utilisateur restent dans [!DNL Audience Manager] et vous pouvez simplement les réactiver, si nécessaire. Si vous supprimez des utilisateurs, vous devez les recréer s’ils doivent utiliser [!DNL Audience Manager] à l&#39;avenir.
   * **[!UICONTROL Expired]:** Le mot de passe d’un utilisateur a plus de 90 jours.
   * **[!UICONTROL Pending]:** L’utilisateur dispose d’un mot de passe temporaire, soit après la réinitialisation d’un mot de passe, soit sous la forme d’un nouveau compte, et il n’a pas encore défini de mot de passe permanent.
   * **[!UICONTROL Locked Out]:** 5 tentatives de connexion incorrectes verrouillent un utilisateur.
1. Sous **[!UICONTROL Assigned Groups]**, dans la liste déroulante, sélectionnez les groupes auxquels vous souhaitez affecter cet utilisateur.
Pour plus d’informations sur les groupes et les autorisations, voir [Création d’un groupe](../../features/administration/administration-overview.md#create-group).
1. Cliquez sur **[!UICONTROL Save]**.

## Créez un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> La gestion des comptes d’utilisateurs se déplace vers le [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Pour lancer la migration des utilisateurs, nous conseillons à tous les clients d’Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Audience Manager de la migration des utilisateurs vers Admin Console](admin-console-migration.md).
> 
> Une fois tous les clients migrés, cette section disparaîtra.

A *group* est un ensemble d’utilisateurs qui partagent des droits d’accès à [!UICONTROL destination], [!UICONTROL segment], et [!UICONTROL trait] objets. Vous pouvez limiter les groupes à des objets uniques ou leur donner un large accès à des combinaisons d’objets différents.

<!-- t_create_groups.xml -->

Création d’un groupe:

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Cliquez sur  ![](assets/icon_add.png) pour ouvrir le [!UICONTROL Group Settings] page.
3. Dans [!UICONTROL Group Details]:
   * Nommez le groupe.
   * Fournissez une brève description du groupe.
4. Dans [!UICONTROL Group Members], cliquez sur un utilisateur dans **[!UICONTROL Add Users]** pour les ajouter au groupe.
5. Dans [!UICONTROL Group Permissions], sélectionnez une [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md)ou [destination](../../features/destinations/destinations.md) de **[!UICONTROL Add Object]**.
Une fenêtre d’autorisation s’ouvre alors pour l’objet sélectionné.
6. Cochez la case correspondant aux autorisations que vous souhaitez que les membres du groupe possèdent.
7. *(Facultatif)* Attribuer [Autorisations génériques](../../features/administration/administration-overview.md#wild-card-permissions) au groupe.
8. Cliquez sur **[!UICONTROL Save Group]**.

## Compréhension [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> La gestion des comptes d’utilisateurs se déplace vers le [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Pour lancer la migration des utilisateurs, nous conseillons à tous les clients d’Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Audience Manager de la migration des utilisateurs vers Admin Console](admin-console-migration.md).
> 
> Une fois tous les clients migrés, cette section disparaîtra.

Simplifiez la gestion des droits des groupes avec [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] donner aux membres du groupe un accès automatique à chaque source de données associée à un [!UICONTROL segment], [!UICONTROL destination]ou [!UICONTROL trait]. Par comparaison, les autorisations régulières ne permettent d’affecter que des [!UICONTROL data sources] à l’un de ces objets. Et lorsque vous ajoutez de nouvelles [!UICONTROL data sources], les membres du groupe n’ont pas accès à ces nouvelles sources.

Vous devez ouvrir les autorisations de groupe et attribuer ces nouvelles autorisations. [!UICONTROL data sources] au groupe. [!UICONTROL Wild Card Permissions] éviter ce manuel ; [!UICONTROL data source] processus de mise à jour. Groupes avec [!UICONTROL Wild Card Permissions] accéder aux nouvelles [!UICONTROL data sources] sans autorisation explicite.

![](assets/wild-card.png)

Lisez ci-dessous une description de chaque [!UICONTROL wildcard permission] signifie :

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Les utilisateurs peuvent sélectionner [!UICONTROL traits] comme ligne de base pour [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Les utilisateurs peuvent modifier toutes les [!UICONTROL traits] configuré dans leur compte d’entreprise.
* `VIEW_ALL_TRAITS` - Les utilisateurs peuvent afficher toutes les [!UICONTROL traits] configuré dans leur compte d’entreprise.
* `DELETE_ALL_TRAITS` - Les utilisateurs peuvent supprimer tous les [!UICONTROL traits] configuré dans leur compte d’entreprise.
* `CREATE_ALL_ALGO_TRAITS` - Les utilisateurs peuvent créer [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Les utilisateurs peuvent ajouter n’importe lequel des éléments [!UICONTROL traits] appartenir à leur société à [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Les utilisateurs peuvent créer [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Les utilisateurs sont autorisés à afficher [!UICONTROL models] appartenant à leur entreprise.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Les utilisateurs peuvent afficher toutes les [!UICONTROL derived signals] appartenant à leur entreprise.
* `CREATE_DERIVED_SIGNALS` - Les utilisateurs peuvent créer [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Les utilisateurs peuvent modifier tous les [!UICONTROL derived signals] appartenant à leur entreprise.
* `DELETE_DERIVED_SIGNALS` - Les utilisateurs peuvent supprimer n’importe lequel des [!UICONTROL derived signals] appartenant à leur entreprise.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Les utilisateurs peuvent modifier tous les [!UICONTROL destinations] configuré dans leur compte d’entreprise.
* `CREATE_DESTINATIONS` - Les utilisateurs peuvent créer [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Les utilisateurs peuvent afficher toutes les [!UICONTROL destinations] configuré dans leur compte d’entreprise.
* `DELETE_ALL_DESTINATIONS` - Les utilisateurs peuvent supprimer tous les [!UICONTROL destinations] configuré dans leur compte d’entreprise.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Les utilisateurs peuvent tout faire (afficher, créer, modifier, supprimer) sur leur [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Les utilisateurs peuvent tout faire (afficher, créer, modifier, supprimer) sur leur [!UICONTROL Audience Lab] groupes de test.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Les utilisateurs peuvent créer des segments.
* `DELETE_ALL_SEGMENTS` - Les utilisateurs peuvent supprimer tous les segments configurés dans leur compte d’entreprise.
* `MAP_ALL_TO_DESTINATIONS` - Les utilisateurs peuvent mapper n’importe quel segment appartenant à leur entreprise sur les destinations.
* `EDIT_ALL_SEGMENTS` - Les utilisateurs peuvent modifier tous les segments configurés dans leur compte d’entreprise.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Les utilisateurs peuvent sélectionner des segments comme référence pour les modèles.
* `VIEW_ALL_SEGMENTS` - Les utilisateurs peuvent afficher tous les segments configurés dans leur compte d’entreprise.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Les utilisateurs peuvent afficher tous les signaux capturés dans [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Cas d’utilisation {#use-cases}

### Contrôle de l’accès des utilisateurs {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] peut vous aider à surveiller l’état de connexion des utilisateurs, en vous donnant une image claire de qui peut accéder à votre instance d’Audience Manager.

En fonction des besoins de votre entreprise, vous pouvez activer et désactiver des comptes d’utilisateurs si nécessaire.

![monitor-user-access](assets/monitor-user-access.png)

### Garantir la protection de l’accès pour les utilisateurs sensibles [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Vous pouvez configurer [!UICONTROL Role-Based Access Control] at [!UICONTROL trait], segment et [!UICONTROL destination] pour chaque groupe d’utilisateurs.

Cette fonctionnalité vous aide à gérer la manière dont vos utilisateurs visualisent, créent, lisent, écrivent et modifient des jeux de données spécifiques, et même à empêcher les utilisateurs d’accéder aux jeux de données qui ne devraient pas leur être accessibles.

![protection d&#39;accès](assets/access-protection.png)
