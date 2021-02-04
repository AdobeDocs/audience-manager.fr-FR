---
description: Les options du menu Administration vous permettent de créer des utilisateurs d’Audience Manager et de les affecter à des groupes. Vous pouvez également définir des limites de vue (caractéristiques, segments, destinations et modèles).
keywords: rbac;RBAC;rôle-based;role-based;role-based contrôles d'accès
seo-description: Les options du menu Administration vous permettent de créer des utilisateurs d’Audience Manager et de les affecter à des groupes. Vous pouvez également définir des limites de vue (caractéristiques, segments, destinations et modèles).
seo-title: Administration
solution: Audience Manager
title: Administration
topic: DIL API
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
translation-type: tm+mt
source-git-commit: 55cb69bad1f369ed3b58bece54aebdca4b14f7a7
workflow-type: tm+mt
source-wordcount: '1203'
ht-degree: 2%

---


# [!UICONTROL Administration] (Commandes RBAC)  {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> La gestion des comptes utilisateur passe au [Admin Console](https://helpx.adobe.com/fr/enterprise/using/admin-console.html). Pour début la migration des utilisateurs, nous demandons à tous les clients Audiences Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Audience Manager de la migration des utilisateurs vers le Admin Console](admin-console-migration.md).
> 
> Une fois que tous les clients ont migré, les sections de gestion des utilisateurs de ce document disparaîtront.


Les options du menu [!UICONTROL Administration] vous permettent de créer des utilisateurs d&#39;Audience Manager et de les affecter à des groupes. Vous pouvez également définir des limites de vue (caractéristiques, segments, destinations et modèles).

Les clients d&#39;entreprise qui utilisent [!DNL Audience Manager] ont besoin d&#39;une plateforme de data Management pour toutes leurs données, mais doivent être en mesure de contrôler la visibilité des différents éléments de données sur des unités commerciales spécifiques. Pour ce faire, vous pouvez utiliser des autorisations de groupe, également appelées [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] utilise des groupes pour attribuer des autorisations. Les autorisations ne sont pas attribuées au niveau de l’utilisateur. Les permissions de groupe sont liées aux objets ([!UICONTROL traits], aux segments, etc.) et aux actions que vous pouvez effectuer sur ces objets (modification, vue, etc.). Ces commandes sont également disponibles via les API REST d’Audience Manager. Voir [Gestion des utilisateurs](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Gestion des groupes](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) et [Gestion des autorisations](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) méthodes API.

## Créer des utilisateurs {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> La gestion des comptes utilisateur passe au [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Pour début la migration des utilisateurs, nous demandons à tous les clients Audiences Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Audience Manager de la migration des utilisateurs vers le Admin Console](admin-console-migration.md).
> 
> Une fois que tous les clients ont migré, la section de gestion des utilisateurs de ce document disparaîtra.

Créez des utilisateurs dans [!DNL Audience Manager] et spécifiez les détails utilisateur, l’état de connexion et l’affectation d’utilisateurs à des groupes.

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Cliquez sur ![](assets/icon_add.png) pour afficher la page [!UICONTROL Create New User].
1. Sous **[!UICONTROL User Details]**, renseignez les champs suivants :
   * **[!UICONTROL Username]:** Indiquez un nom d’utilisateur unique pour l’Audience Manager.
   * **[!UICONTROL First Name]:** indiquez le prénom de l’utilisateur.
   * **[!UICONTROL Last Name]:** indiquez le nom de famille de l’utilisateur.
   * **[!UICONTROL Email Address]:** indiquez l’adresse électronique de l’utilisateur. [!DNL Audience Manager] n’envoie pas de notification régulière aux utilisateurs. [!DNL Audience Manager] les administrateurs ont accès aux adresses électroniques des utilisateurs et peuvent envoyer manuellement des messages électroniques aux utilisateurs si nécessaire. Par exemple, si un utilisateur oublie son mot de passe, l’adresse électronique indiquée dans ce champ est utilisée pour envoyer un mot de passe temporaire et des instructions pour réinitialiser le mot de passe.
   * **[!UICONTROL Phone Number]:** indiquez le numéro de téléphone de l’utilisateur.
   * **[!UICONTROL Is Admin]:** Indiquez si cet utilisateur est un  [!DNL Audience Manager] administrateur. Les administrateurs peuvent gérer les utilisateurs (créer, modifier, etc.) et les groupes (créer, attribuer des autorisations, etc.). Les utilisateurs non administrateurs ne peuvent contrôler que leurs propres profils d’utilisateurs, y compris la modification de leurs adresses électroniques et la réinitialisation de leurs propres mots de passe. Pour plus d’informations, voir [Modifier les paramètres de votre compte](../../features/administration/edit-account-settings.md).
1. Sous **[!UICONTROL Login]**, sélectionnez un état :
   * **[!UICONTROL Active]:utilisateurs**  Principaux peuvent accéder  [!DNL Audience Manager] et disposer des autorisations accordées par l’appartenance à un groupe.
   * **[!UICONTROL Deactivated]: les utilisateurs**  désactivés ne peuvent pas accéder  [!DNL Audience Manager] et ne disposent d’aucune autorisation. Si vous désactivez des utilisateurs, leurs informations d’utilisateur restent dans [!DNL Audience Manager] et vous pouvez les réactiver simplement, si nécessaire. Si vous supprimez des utilisateurs, vous devez les recréer s’ils doivent réutiliser [!DNL Audience Manager] à l’avenir.
   * **[!UICONTROL Expired]:** le mot de passe d’un utilisateur est plus vieux que 90 jours.
   * **[!UICONTROL Pending]:** L’utilisateur dispose d’un mot de passe temporaire, soit après la réinitialisation d’un mot de passe, soit en tant que nouveau compte, et il n’a pas encore défini de mot de passe permanent.
   * **[!UICONTROL Locked Out]:** 5 tentatives de connexion incorrectes verrouilleront un utilisateur.
1. Sous **[!UICONTROL Assigned Groups]**, dans la liste déroulante, sélectionnez les groupes auxquels vous souhaitez affecter cet utilisateur.
Pour plus d’informations sur les groupes et les autorisations, voir [Création d’un groupe](../../features/administration/administration-overview.md#create-group).
1. Cliquez sur **[!UICONTROL Save]**.

## Créez un [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> La gestion des comptes utilisateur passe au [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Pour début la migration des utilisateurs, nous conseillons à tous les clients Audiences Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Audience Manager de la migration des utilisateurs vers le Admin Console](admin-console-migration.md).
> 
> Une fois que tous les clients ont migré, cette section disparaîtra.

Un *groupe* est un ensemble d&#39;utilisateurs qui partagent des droits d&#39;accès aux objets [!UICONTROL destination], [!UICONTROL segment] et [!UICONTROL trait]. Vous pouvez limiter les groupes à des objets uniques ou leur donner un large accès à des combinaisons d’objets différents.

<!-- t_create_groups.xml -->

Création d’un groupe:

1. Cliquez sur **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Cliquez sur ![](assets/icon_add.png) pour ouvrir la page [!UICONTROL Group Settings].
3. Dans [!UICONTROL Group Details]:
   * Nommez le groupe.
   * Fournissez une brève description du groupe.
4. Dans [!UICONTROL Group Members], cliquez sur un utilisateur à partir des options **[!UICONTROL Add Users]** pour les ajouter au groupe.
5. Dans [!UICONTROL Group Permissions], sélectionnez une [caractéristique](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md) ou [destination](../../features/destinations/destinations.md) dans **[!UICONTROL Add Object]**.
Cette opération ouvre une fenêtre d&#39;autorisations pour l&#39;objet sélectionné.
6. Cochez la case correspondant aux autorisations que vous souhaitez que les membres du groupe possèdent.
7. *(Facultatif)* Attribuez des  [autorisations de carte ](../../features/administration/administration-overview.md#wild-card-permissions) générique au groupe.
8. Cliquez sur **[!UICONTROL Save Group]**.

## Comprendre [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> La gestion des comptes utilisateur passe au [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Pour début la migration des utilisateurs, nous conseillons à tous les clients Audiences Manager de prendre immédiatement les mesures nécessaires décrites dans cet article : [Audience Manager de la migration des utilisateurs vers le Admin Console](admin-console-migration.md).
> 
> Une fois que tous les clients ont migré, cette section disparaîtra.

Simplifiez la gestion des droits de groupe avec [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] donnent aux membres du groupe un accès automatique à chaque source de données associée à une source  [!UICONTROL segment],  [!UICONTROL destination] ou  [!UICONTROL trait]. Par comparaison, les autorisations régulières vous permettent uniquement d&#39;affecter [!UICONTROL data sources] spécifique à l&#39;un de ces objets. Et, lorsque vous ajoutez de nouvelles [!UICONTROL data sources], les membres du groupe n&#39;ont pas accès à ces nouvelles sources.

Vous devez ouvrir les autorisations de groupe et affecter ces nouvelles [!UICONTROL data sources] au groupe. [!UICONTROL Wild Card Permissions] évitez ce processus de  [!UICONTROL data source] mise à jour manuelle. Les groupes avec [!UICONTROL Wild Card Permissions] ont accès à [!UICONTROL data sources] nouveau  sans autorisation explicite.

![](assets/wild-card.png)

Vous trouverez ci-dessous une description de ce que signifie chaque [!UICONTROL wildcard permission] :

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Les utilisateurs peuvent sélectionner  [!UICONTROL traits] comme ligne de base pour  [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Les utilisateurs peuvent modifier toutes les  [!UICONTROL traits] configurations de leur compte de société.
* `VIEW_ALL_TRAITS` - Les utilisateurs peuvent vue tous les éléments  [!UICONTROL traits] configurés dans leur compte de société.
* `DELETE_ALL_TRAITS` - Les utilisateurs peuvent supprimer tous les éléments  [!UICONTROL traits] configurés dans leur compte de société.
* `CREATE_ALL_ALGO_TRAITS` - Les utilisateurs peuvent créer  [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Les utilisateurs peuvent ajouter n&#39;importe quelle  [!UICONTROL traits] appartenance à leur société à  [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Les utilisateurs peuvent créer  [!UICONTROL traits].

**[!UICONTROL Reports]**

* `PTRREPORTS` - Ceci  [!UICONTROL wildcard permission] fait référence à des fonctionnalités obsolètes et sera supprimé sous peu de l&#39;interface utilisateur de l&#39;Audience Manager.

**[!UICONTROL Models]**

* `VIEW_MODELS` - Les utilisateurs ont la permission de vue  [!UICONTROL models] appartenant à leur société.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Les utilisateurs peuvent vue tous les  [!UICONTROL derived signals] membres de leur société.
* `CREATE_DERIVED_SIGNALS` - Les utilisateurs peuvent créer  [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Les utilisateurs peuvent modifier tous les éléments  [!UICONTROL derived signals] appartenant à leur société.
* `DELETE_DERIVED_SIGNALS` - Les utilisateurs peuvent supprimer n&#39;importe quel  [!UICONTROL derived signals] membre de leur société.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Les utilisateurs peuvent modifier toutes les  [!UICONTROL destinations] configurations de leur compte de société.
* `CREATE_DESTINATIONS` - Les utilisateurs peuvent créer  [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Les utilisateurs peuvent vue tous les éléments  [!UICONTROL destinations] configurés dans leur compte de société.
* `DELETE_ALL_DESTINATIONS` - Les utilisateurs peuvent supprimer tous les éléments  [!UICONTROL destinations] configurés dans leur compte de société.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Les utilisateurs peuvent tout faire (vue, créer, modifier, supprimer) sur leur  [!UICONTROL Tag Containers]site.

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Les utilisateurs peuvent tout faire (vue, créer, modifier, supprimer) sur leurs groupes de  [!UICONTROL Audience Lab] tests.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Les utilisateurs peuvent créer des segments.
* `DELETE_ALL_SEGMENTS` - Les utilisateurs peuvent supprimer tous les segments configurés dans leur compte de société.
* `MAP_ALL_TO_DESTINATIONS` - Les utilisateurs peuvent mapper n’importe quel segment appartenant à leur société vers des destinations.
* `EDIT_ALL_SEGMENTS` - Les utilisateurs peuvent modifier tous les segments configurés dans leur compte de société.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Les utilisateurs peuvent sélectionner des segments comme référence pour les modèles.
* `VIEW_ALL_SEGMENTS` - Les utilisateurs peuvent vue tous les segments configurés dans leur compte de société.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Les utilisateurs peuvent vue tous les signaux capturés dans le  [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Cas d’utilisation {#use-cases}

### Contrôle de l&#39;accès utilisateur {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] peut vous aider à surveiller l’état de connexion de l’utilisateur, en vous donnant une idée claire de qui peut accéder à votre instance d’Audience Manager.

En fonction des besoins de votre entreprise, vous pouvez activer et désactiver les comptes d’utilisateurs si nécessaire.

![moniteur-accès-utilisateur](assets/monitor-user-access.png)

### Assurer la protection d&#39;accès pour les [!UICONTROL Data Sources] {#protect-sensitive-data-sources} sensibles

Vous pouvez configurer [!UICONTROL Role-Based Access Control] au niveau [!UICONTROL trait], segment et [!UICONTROL destination], pour chaque groupe d’utilisateurs.

Cette fonctionnalité vous permet de gérer la manière dont vos utilisateurs vue, créent, lisent, écrivent et modifient des jeux de données spécifiques, et même de limiter l&#39;accès des utilisateurs aux jeux de données qui ne devraient pas leur être accessibles.

![protection d&#39;accès](assets/access-protection.png)
