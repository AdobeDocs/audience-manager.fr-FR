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
source-wordcount: '1173'
ht-degree: 0%

---

# [!UICONTROL Administration] (Contrôles RBAC) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> La gestion des comptes utilisateur passe à l’Admin Console [. ](https://helpx.adobe.com/fr/enterprise/using/admin-console.html) Pour commencer la migration des utilisateurs, nous demandons à tous les clients d’Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Migration des utilisateurs d’Audience Manager vers Admin Console](admin-console-migration.md).
> 
> Une fois tous les clients migrés, les sections de gestion des utilisateurs de ce document disparaîtront.

>[!IMPORTANT]
>
> Avant de pouvoir utiliser [!DNL RBAC], cette fonctionnalité doit être activée par Adobe pour votre organisation. Contactez l’équipe de votre compte pour demander l’activation de [!DNL RBAC] ou contactez l’assistance clientèle.


Les options du menu [!UICONTROL Administration] vous permettent de créer des utilisateurs d’Audience Manager et de les affecter à des groupes. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).

Les clients d’entreprise utilisant [!DNL Audience Manager] ont besoin d’une plateforme de gestion de données pour toutes leurs données, mais doivent être en mesure de contrôler la visibilité des différents éléments de données sur des entités commerciales spécifiques. Pour ce faire, vous pouvez utiliser des autorisations de groupe, également appelées [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilise des groupes pour attribuer des autorisations. Les autorisations ne sont pas affectées au niveau de l’utilisateur. Les autorisations de groupe sont liées aux objets ([!UICONTROL traits], segments, etc.) et aux actions que vous pouvez effectuer sur ces objets (édition, affichage, etc.). Ces commandes sont également disponibles via les API REST d’Audience Manager. Voir les méthodes d’API [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Group Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) et [Permissions Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md).

## Création d’utilisateurs {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> La gestion des comptes utilisateur passe à l’Admin Console [. ](https://helpx.adobe.com/fr/enterprise/using/admin-console.html) Pour commencer la migration des utilisateurs, nous demandons à tous les clients d’Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Migration des utilisateurs d’Audience Manager vers Admin Console](admin-console-migration.md).
> 
> Une fois tous les clients migrés, la section de gestion des utilisateurs de ce document disparaîtra.
> 
Créez des utilisateurs dans [!DNL Audience Manager] et spécifiez les détails de l’utilisateur, l’état de connexion et affectez des utilisateurs à des groupes.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Cliquez sur ![](assets/icon_add.png) pour afficher la page [!UICONTROL Create New User].
1. Sous **[!UICONTROL User Details]**, renseignez les champs suivants :
   * **[!UICONTROL Username]:** Spécifiez un nom d’utilisateur unique pour l’Audience Manager.
   * **[!UICONTROL First Name]:** Spécifiez le prénom de l’utilisateur.
   * **[!UICONTROL Last Name]:** indiquez le nom de l’utilisateur.
   * **[!UICONTROL Email Address]:** indiquez l’adresse électronique de l’utilisateur. [!DNL Audience Manager] n’envoie pas de notification régulière aux utilisateurs. Les administrateurs [!DNL Audience Manager] ont accès aux adresses électroniques des utilisateurs et peuvent envoyer manuellement des e-mails aux utilisateurs, si nécessaire. Par exemple, si un utilisateur oublie son mot de passe, l’adresse électronique indiquée dans ce champ est utilisée pour envoyer un mot de passe temporaire et des instructions pour réinitialiser le mot de passe.
   * **[!UICONTROL Phone Number]:** indiquez le numéro de téléphone de l’utilisateur.
   * **[!UICONTROL Is Admin]:** Indiquez si cet utilisateur est un administrateur [!DNL Audience Manager]. Les utilisateurs administrateurs peuvent gérer les utilisateurs (créer, modifier, etc.) et les groupes (créer, attribuer des autorisations, etc.). Les utilisateurs non-administrateurs peuvent contrôler uniquement leurs propres profils utilisateur, y compris la modification de leurs adresses électroniques et la réinitialisation de leurs propres mots de passe. Pour plus d’informations, voir [Modification des paramètres de votre compte](../../features/administration/edit-account-settings.md).
1. Sous **[!UICONTROL Login]**, sélectionnez l’état souhaité :
   * **[!UICONTROL Active]:** les utilisateurs actifs peuvent accéder à [!DNL Audience Manager] et disposent des autorisations accordées par appartenance à un groupe.
   * **[!UICONTROL Deactivated]:** Les utilisateurs désactivés ne peuvent pas accéder à [!DNL Audience Manager] et ne disposent d’aucune autorisation. Si vous désactivez des utilisateurs, leurs informations utilisateur restent dans [!DNL Audience Manager] et vous pouvez simplement les réactiver, si nécessaire. Si vous supprimez des utilisateurs, vous devez les recréer s’ils doivent à nouveau utiliser [!DNL Audience Manager] à l’avenir.
   * **[!UICONTROL Expired]:** Le mot de passe d’un utilisateur a plus de 90 jours.
   * **[!UICONTROL Pending]:** L’utilisateur dispose d’un mot de passe temporaire, soit après la réinitialisation d’un mot de passe, soit sous la forme d’un nouveau compte, et il n’a pas encore défini de mot de passe permanent.
   * **[!UICONTROL Locked Out]:** 5 tentatives de connexion incorrectes verrouilleront un utilisateur.
1. Sous **[!UICONTROL Assigned Groups]**, dans la liste déroulante, sélectionnez les groupes auxquels vous souhaitez affecter cet utilisateur.
Pour plus d’informations sur les groupes et les autorisations, voir [Création d’un groupe](../../features/administration/administration-overview.md#create-group).
1. Cliquez sur **[!UICONTROL Save]**.

## Créer un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> La gestion des comptes utilisateur passe à l’Admin Console [. ](https://helpx.adobe.com/fr/enterprise/using/admin-console.html) Pour commencer la migration des utilisateurs, nous conseillons à tous les clients d’Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Migration des utilisateurs d’Audience Manager vers Admin Console](admin-console-migration.md).
> 
> Une fois tous les clients migrés, cette section disparaîtra.

Un *groupe* est un ensemble d&#39;utilisateurs qui partagent des droits d&#39;accès aux objets [!UICONTROL destination], [!UICONTROL segment] et [!UICONTROL trait]. Vous pouvez limiter les groupes à des objets uniques ou leur donner un large accès à des combinaisons d’objets différents.

<!-- t_create_groups.xml -->

Pour créer un groupe :

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Cliquez sur ![](assets/icon_add.png) pour ouvrir la page [!UICONTROL Group Settings].
3. Dans [!UICONTROL Group Details] :
   * Nommez le groupe.
   * Fournissez une brève description du groupe.
4. Dans [!UICONTROL Group Members], cliquez sur un utilisateur parmi les options **[!UICONTROL Add Users]** pour les ajouter au groupe.
5. Dans [!UICONTROL Group Permissions], sélectionnez une [caractéristique](../../features/traits/trait-details-page.md), un [segment](../../features/segments/segments-purpose.md) ou une [destination](../../features/destinations/destinations.md) à partir de **[!UICONTROL Add Object]**.
Une fenêtre d’autorisation s’ouvre alors pour l’objet sélectionné.
6. Cochez la case correspondant aux autorisations que vous souhaitez que les membres du groupe possèdent.
7. *(Facultatif)* Attribuez des [ autorisations de caractères génériques](../../features/administration/administration-overview.md#wild-card-permissions) au groupe.
8. Cliquez sur **[!UICONTROL Save Group]**.

## Comprendre [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> La gestion des comptes utilisateur passe à l’Admin Console [. ](https://helpx.adobe.com/fr/enterprise/using/admin-console.html) Pour commencer la migration des utilisateurs, nous conseillons à tous les clients d’Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Migration des utilisateurs d’Audience Manager vers Admin Console](admin-console-migration.md).
> 
> Une fois tous les clients migrés, cette section disparaîtra.

Simplifiez la gestion des droits des groupes avec [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] donne aux membres du groupe un accès automatique à chaque source de données associée à [!UICONTROL segment], [!UICONTROL destination] ou [!UICONTROL trait]. En comparaison, les autorisations régulières ne permettent d&#39;affecter que [!UICONTROL data sources] à l&#39;un de ces objets. Et, lorsque vous ajoutez de nouveaux [!UICONTROL data sources], les membres du groupe n’ont pas accès à ces nouvelles sources.

Vous devez ouvrir les autorisations du groupe et attribuer ces nouveaux [!UICONTROL data sources] au groupe. [!UICONTROL Wild Card Permissions] permet d&#39;éviter ce processus manuel de mise à jour [!UICONTROL data source]. Les groupes avec [!UICONTROL Wild Card Permissions] ont accès au nouvel [!UICONTROL data sources] sans autorisation explicite.

![](assets/wild-card.png)

Lisez ci-dessous une description de chaque [!UICONTROL wildcard permission] :

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Les utilisateurs peuvent sélectionner [!UICONTROL traits] comme référence pour [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Les utilisateurs peuvent modifier tous les [!UICONTROL traits] configurés dans leur compte d’entreprise.
* `VIEW_ALL_TRAITS` - Les utilisateurs peuvent afficher tous les [!UICONTROL traits] configurés dans leur compte d’entreprise.
* `DELETE_ALL_TRAITS` - Les utilisateurs peuvent supprimer tous les [!UICONTROL traits] configurés dans leur compte d’entreprise.
* `CREATE_ALL_ALGO_TRAITS` - Les utilisateurs peuvent créer [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Les utilisateurs peuvent ajouter n’importe lequel des [!UICONTROL traits] appartenant à leur société à [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Les utilisateurs peuvent créer [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Les utilisateurs sont autorisés à afficher [!UICONTROL models] appartenant à leur entreprise.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Les utilisateurs peuvent afficher tous les [!UICONTROL derived signals] appartenant à leur entreprise.
* `CREATE_DERIVED_SIGNALS` - Les utilisateurs peuvent créer [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Les utilisateurs peuvent modifier tous les [!UICONTROL derived signals] appartenant à leur entreprise.
* `DELETE_DERIVED_SIGNALS` - Les utilisateurs peuvent supprimer n’importe lequel des [!UICONTROL derived signals] appartenant à leur entreprise.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Les utilisateurs peuvent modifier toutes les [!UICONTROL destinations] configurées dans leur compte d’entreprise.
* `CREATE_DESTINATIONS` - Les utilisateurs peuvent créer [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Les utilisateurs peuvent afficher toutes les [!UICONTROL destinations] configurées dans leur compte d’entreprise.
* `DELETE_ALL_DESTINATIONS` - Les utilisateurs peuvent supprimer tous les [!UICONTROL destinations] configurés dans leur compte d’entreprise.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Les utilisateurs peuvent tout faire (afficher, créer, modifier, supprimer) sur leur [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Les utilisateurs peuvent tout faire (afficher, créer, modifier, supprimer) sur leurs groupes de test [!UICONTROL Audience Lab].

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Les utilisateurs peuvent créer des segments.
* `DELETE_ALL_SEGMENTS` - Les utilisateurs peuvent supprimer tous les segments configurés dans leur compte d’entreprise.
* `MAP_ALL_TO_DESTINATIONS` - Les utilisateurs peuvent mapper n’importe quel segment appartenant à leur entreprise aux destinations.
* `EDIT_ALL_SEGMENTS` - Les utilisateurs peuvent modifier tous les segments configurés dans leur compte d’entreprise.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Les utilisateurs peuvent sélectionner des segments comme référence pour les modèles.
* `VIEW_ALL_SEGMENTS` - Les utilisateurs peuvent afficher tous les segments configurés dans leur compte d’entreprise.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Les utilisateurs peuvent afficher tous les signaux capturés dans [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Cas d’utilisation {#use-cases}

### Contrôle de l’accès des utilisateurs {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] peut vous aider à surveiller l’état de connexion de l’utilisateur, ce qui vous donne une image claire de qui peut accéder à votre instance d’Audience Manager.

En fonction des besoins de votre entreprise, vous pouvez activer et désactiver des comptes d’utilisateurs si nécessaire.

![monitor-user-access](assets/monitor-user-access.png)

### Assurer la protection de l’accès pour les utilisateurs sensibles [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Vous pouvez configurer [!UICONTROL Role-Based Access Control] au niveau [!UICONTROL trait], segment et [!UICONTROL destination] pour chaque groupe d’utilisateurs.

Cette fonctionnalité vous aide à gérer la manière dont vos utilisateurs visualisent, créent, lisent, écrivent et modifient des jeux de données spécifiques, et même à empêcher les utilisateurs d’accéder aux jeux de données qui ne devraient pas leur être accessibles.

![access-protection](assets/access-protection.png)
