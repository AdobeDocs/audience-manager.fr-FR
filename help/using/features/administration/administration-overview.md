---
description: Les options du menu Administration vous permettent de créer des utilisateurs Audience Manager et de les affecter à des groupes. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).
keywords: rbac;RBAC;basé sur les rôles;basé sur les rôles;contrôles d’accès basés sur les rôles
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

# [!UICONTROL Administration] (contrôles RBAC) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> La gestion des comptes d&#39;utilisateurs est transférée vers [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Pour démarrer la migration des utilisateurs, nous demandons à tous les clients Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [migration des utilisateurs Audience Manager vers Admin Console](admin-console-migration.md).
> 
> Une fois la migration de tous les clients effectuée, les sections Gestion des utilisateurs de ce document seront supprimées.

>[!IMPORTANT]
>
> Avant de pouvoir utiliser [!DNL RBAC], cette fonctionnalité doit être activée par Adobe pour votre organisation. Contactez l’équipe en charge de votre compte pour demander l’activation du [!DNL RBAC] ou contactez l’assistance clientèle.


Les options du menu [!UICONTROL Administration] vous permettent de créer des utilisateurs Audience Manager et de les affecter à des groupes. Vous pouvez également afficher les limites (caractéristiques, segments, destinations et modèles).

Les entreprises clientes qui utilisent [!DNL Audience Manager] ont besoin d’une plateforme de gestion des données pour toutes leurs données, mais doivent être en mesure de contrôler la visibilité des différents éléments de données sur des unités commerciales spécifiques. Pour ce faire, utilisez les autorisations de groupe, également appelées [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilise des groupes pour attribuer des autorisations. Les autorisations ne sont pas attribuées au niveau de l’utilisateur. Les autorisations de groupe sont liées à des objets ([!UICONTROL traits], segments, etc.) et à des actions que vous pouvez effectuer sur ces objets (modifier, afficher, etc.). Ces commandes sont également disponibles via les API REST Audience Manager. Consultez les méthodes d’API [User Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Group Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) et [Permissions Management](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md).

## Créer des utilisateurs {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> La gestion des comptes d&#39;utilisateurs est transférée vers [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Pour démarrer la migration des utilisateurs, nous demandons à tous les clients Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [migration des utilisateurs Audience Manager vers Admin Console](admin-console-migration.md).
> 
> Une fois la migration de tous les clients terminée, la section Gestion des utilisateurs de ce document disparaîtra.
> 
Créez des utilisateurs dans [!DNL Audience Manager], spécifiez les détails des utilisateurs, le statut de connexion et affectez des utilisateurs à des groupes.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Cliquez sur ![](assets/icon_add.png) pour afficher la page [!UICONTROL Create New User].
1. Sous **[!UICONTROL User Details]**, renseignez les champs suivants :
   * **[!UICONTROL Username]:** un nom d’utilisateur unique pour Audience Manager.
   * **[!UICONTROL First Name]:** spécifiez le prénom de l’utilisateur.
   * **[!UICONTROL Last Name]:** indiquez le nom de l’utilisateur.
   * **[!UICONTROL Email Address]:** indiquez l’adresse e-mail de l’utilisateur. [!DNL Audience Manager] n’envoie pas de notification régulière aux utilisateurs. Les administrateurs [!DNL Audience Manager] ont accès aux adresses électroniques des utilisateurs et peuvent envoyer manuellement des e-mails aux utilisateurs selon les besoins. Par exemple, si un utilisateur oublie son mot de passe, l’adresse e-mail spécifiée dans ce champ est utilisée pour envoyer un mot de passe temporaire et des instructions pour réinitialiser le mot de passe.
   * **[!UICONTROL Phone Number]:** indiquez le numéro de téléphone de l’utilisateur.
   * **[!UICONTROL Is Admin]:** indiquez si cet utilisateur est un administrateur [!DNL Audience Manager]. Les utilisateurs administrateurs peuvent gérer des utilisateurs (créer, modifier, etc.) et des groupes (créer, attribuer des autorisations, etc.). Les utilisateurs non-administrateurs ne peuvent contrôler que leurs propres profils d’utilisateurs, notamment la modification de leurs adresses e-mail et la réinitialisation de leurs propres mots de passe. Pour plus d’informations, voir [Modifier les paramètres de votre compte](../../features/administration/edit-account-settings.md).
1. Sous **[!UICONTROL Login]**, sélectionnez le statut souhaité :
   * **[!UICONTROL Active]:** les utilisateurs actifs peuvent accéder aux [!DNL Audience Manager] et disposer des autorisations accordées par l’appartenance à un groupe.
   * **[!UICONTROL Deactivated]:** Les utilisateurs désactivés ne peuvent pas accéder aux [!DNL Audience Manager] et ne disposent d’aucune autorisation. Si vous désactivez des utilisateurs, leurs informations d’utilisateur restent en [!DNL Audience Manager] et vous pouvez simplement les réactiver, si nécessaire. Si vous supprimez des utilisateurs, vous devez les recréer s’ils doivent réutiliser [!DNL Audience Manager] à l’avenir.
   * **[!UICONTROL Expired]:** Le mot de passe d&#39;un utilisateur a plus de 90 jours.
   * **[!UICONTROL Pending]:** l’utilisateur dispose d’un mot de passe temporaire, tel qu’il a été réinitialisé après un mot de passe ou il s’agit d’un tout nouveau compte, et il n’a pas encore défini de mot de passe permanent.
   * **[!UICONTROL Locked Out]:** 5 tentatives de connexion incorrectes verrouilleront un utilisateur.
1. Sous **[!UICONTROL Assigned Groups]**, dans la liste déroulante, sélectionnez les groupes auxquels vous souhaitez affecter cet utilisateur.
Pour plus d’informations sur les groupes et les autorisations, voir [Créer un groupe](../../features/administration/administration-overview.md#create-group).
1. Cliquez sur **[!UICONTROL Save]**.

## Création d’un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> La gestion des comptes d&#39;utilisateurs est transférée vers [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Pour démarrer la migration des utilisateurs, nous conseillons à tous les clients Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [migration des utilisateurs Audience Manager vers Admin Console](admin-console-migration.md).
> 
> Une fois que tous les clients ont migré, cette section disparaît.

Un *groupe* est un ensemble d’utilisateurs qui partagent des droits d’accès aux objets [!UICONTROL destination], [!UICONTROL segment] et [!UICONTROL trait]. Vous pouvez limiter les groupes à des objets uniques uniquement ou leur donner un accès étendu à des combinaisons d’objets différents.

<!-- t_create_groups.xml -->

Pour créer un groupe :

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Cliquez sur ![](assets/icon_add.png) pour ouvrir la page [!UICONTROL Group Settings].
3. En [!UICONTROL Group Details] :
   * Nommez le groupe.
   * Fournissez une brève description du groupe.
4. Dans [!UICONTROL Group Members], cliquez sur un utilisateur dans **[!UICONTROL Add Users]** options pour l’ajouter au groupe.
5. Dans [!UICONTROL Group Permissions], sélectionnez une [caractéristique](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md) ou [destination](../../features/destinations/destinations.md) dans **[!UICONTROL Add Object]**.
Une fenêtre d’autorisations s’ouvre alors pour l’objet sélectionné.
6. Cochez la case correspondant aux autorisations que vous souhaitez accorder aux membres du groupe.
7. *(Facultatif)* Attribuez [autorisations génériques](../../features/administration/administration-overview.md#wild-card-permissions) au groupe .
8. Cliquez sur **[!UICONTROL Save Group]**.

## Comprendre les [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> La gestion des comptes d&#39;utilisateurs est transférée vers [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Pour démarrer la migration des utilisateurs, nous conseillons à tous les clients Audience Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [migration des utilisateurs Audience Manager vers Admin Console](admin-console-migration.md).
> 
> Une fois que tous les clients ont migré, cette section disparaît.

Simplifiez la gestion des droits des groupes avec [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] donner aux membres du groupe un accès automatique à chaque source de données associée à un [!UICONTROL segment], un [!UICONTROL destination] ou un [!UICONTROL trait]. En comparaison, les autorisations standard vous permettent uniquement d’attribuer des [!UICONTROL data sources] spécifiques à l’un de ces objets. Et lorsque vous ajoutez de nouvelles [!UICONTROL data sources], les membres du groupe n’ont pas accès à ces nouvelles sources.

Vous devez ouvrir les autorisations du groupe et attribuer ces nouvelles [!UICONTROL data sources] au groupe. [!UICONTROL Wild Card Permissions] vous permettent d’éviter ce processus de mise à jour [!UICONTROL data source] manuel. Les groupes avec [!UICONTROL Wild Card Permissions] ont accès aux nouveaux [!UICONTROL data sources] sans autorisation explicite.

![](assets/wild-card.png)

Lisez ci-dessous pour une description de la signification de chaque [!UICONTROL wildcard permission] :

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Les utilisateurs peuvent sélectionner [!UICONTROL traits] comme ligne de base pour les [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Les utilisateurs peuvent modifier toutes les [!UICONTROL traits] configurées dans leur compte d’entreprise.
* `VIEW_ALL_TRAITS` - Les utilisateurs peuvent afficher toutes les [!UICONTROL traits] configurées dans leur compte d’entreprise.
* `DELETE_ALL_TRAITS` - Les utilisateurs peuvent supprimer toutes les [!UICONTROL traits] configurées dans leur compte d’entreprise.
* `CREATE_ALL_ALGO_TRAITS` - Les utilisateurs peuvent créer des [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Les utilisateurs peuvent ajouter à [!UICONTROL traits] l’un des [!UICONTROL segments] appartenant à leur entreprise.
* `CREATE_ALL_TRAITS` - Les utilisateurs peuvent créer des [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Les utilisateurs sont autorisés à afficher les [!UICONTROL models] appartenant à leur entreprise.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Les utilisateurs peuvent afficher tous les [!UICONTROL derived signals] appartenant à leur entreprise.
* `CREATE_DERIVED_SIGNALS` - Les utilisateurs peuvent créer des [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Les utilisateurs peuvent modifier tous les [!UICONTROL derived signals] appartenant à leur entreprise.
* `DELETE_DERIVED_SIGNALS` - Les utilisateurs peuvent supprimer tout [!UICONTROL derived signals] appartenant à leur entreprise.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Les utilisateurs peuvent modifier toutes les [!UICONTROL destinations] configurées dans leur compte d’entreprise.
* `CREATE_DESTINATIONS` - Les utilisateurs peuvent créer des [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Les utilisateurs peuvent afficher toutes les [!UICONTROL destinations] configurées dans leur compte d’entreprise.
* `DELETE_ALL_DESTINATIONS` - Les utilisateurs peuvent supprimer toutes les [!UICONTROL destinations] configurées dans leur compte d’entreprise.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Les utilisateurs peuvent tout faire (afficher, créer, modifier, supprimer) sur leur [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Les utilisateurs peuvent tout faire (afficher, créer, modifier, supprimer) sur leurs groupes de test [!UICONTROL Audience Lab].

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Les utilisateurs peuvent créer des segments.
* `DELETE_ALL_SEGMENTS` - Les utilisateurs et utilisatrices peuvent supprimer tous les segments configurés dans leur compte d’entreprise.
* `MAP_ALL_TO_DESTINATIONS` - Les utilisateurs et utilisatrices peuvent mapper n’importe quel segment appartenant à leur entreprise aux destinations.
* `EDIT_ALL_SEGMENTS` - Les utilisateurs et utilisatrices peuvent modifier tous les segments configurés dans leur compte d’entreprise.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Les utilisateurs peuvent sélectionner des segments comme ligne de base pour les modèles.
* `VIEW_ALL_SEGMENTS` - Les utilisateurs et utilisatrices peuvent afficher tous les segments configurés dans leur compte d’entreprise.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Les utilisateurs peuvent afficher tous les signaux capturés dans [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Cas d’utilisation {#use-cases}

### Surveillance de l’accès des utilisateurs {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] peut vous aider à surveiller le statut de connexion des utilisateurs et utilisatrices, ce qui vous permet d’avoir une idée claire des personnes pouvant accéder à votre instance Audience Manager.

Selon les besoins de votre entreprise, vous pouvez activer et désactiver des comptes d’utilisateurs selon vos besoins.

![accès-utilisateur-moniteur](assets/monitor-user-access.png)

### Protection d’accès pour les [!UICONTROL Data Sources] sensibles {#protect-sensitive-data-sources}

Vous pouvez configurer des [!UICONTROL Role-Based Access Control] au niveau des [!UICONTROL trait], des segments et des [!UICONTROL destination], pour chaque groupe d’utilisateurs.

Cette fonctionnalité vous permet de gérer la manière dont vos utilisateurs affichent, créent, lisent, écrivent et modifient des jeux de données spécifiques, et même de restreindre l’accès des utilisateurs à des jeux de données qui ne devraient pas être disponibles pour eux.

![protection-accès](assets/access-protection.png)
