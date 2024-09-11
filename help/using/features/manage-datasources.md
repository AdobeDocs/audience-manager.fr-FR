---
description: Pour créer une source de données, accédez à Audience Data > Data Sources > Add New et suivez les étapes décrites ici pour chaque section. Des autorisations d’administrateur sont requises pour créer une source de données.
keywords: sources de données;gérer la source de données;source de données audience manager
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Gérer les sources de données
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: e41dddd022b6fa02cab3e16bd21536d41584975f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Gérer [!UICONTROL Data Sources] {#manage-data-sources}

## Créer un [!UICONTROL Data Source] {#create-data-source}

Pour créer un [!UICONTROL data source], accédez à **[!UICONTROL Audience Data > Data Sources > Add New]** et suivez les étapes de chaque section décrite ici. Des autorisations d’administrateur sont requises pour créer un [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Voir [Paramètres de Source de données et options de menu](../features/datasources-list-and-settings.md#settings-menu-options) pour obtenir des descriptions de ces différents contrôles.

## [!UICONTROL Data Source] Détails {#details}

Pour terminer la section [!UICONTROL Data Source Details] :

1. Nommez le [!UICONTROL data source].
1. *(Facultatif)* Décrivez le [!UICONTROL data source]. Une description concise vous permet de définir le rôle ou l’objectif de [!UICONTROL data source].
1. Fournissez un [!UICONTROL integration code]. En règle générale, [!UICONTROL integration codes] est facultatif. Elles sont requises lorsque vous souhaitez :

   * [Créez une source de données multi-appareils](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Utilisez le [service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Utilisation des [stratégies de fusion de profils](../features/profile-merge-rules/merge-rules-start.md).

1. Sélectionnez un **[!UICONTROL ID Type]**. [!UICONTROL ID Type] options incluent :

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obligatoire pour créer un [!UICONTROL Profile Merge Rule]). Remarque : pour certains clients, cette sélection expose les options **[!UICONTROL ID Definition]**.

   >[!NOTE]
   >
   >Pour chaque organisation configurée pour l’Audience Manager et l’Experience Platform, même si aucun partage de segment n’est configuré entre les deux applications, lorsque vous créez une source de données multi-appareils, un [espace de noms d’identité](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) correspondant est créé dans Experience Platform.

1. Choisissez une option **[!UICONTROL ID Definition]**. Les options incluent :

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Les contrôles des exportations de données](../features/data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à un [!UICONTROL data source] et à un [!UICONTROL destination]. Elles vous empêchent d’envoyer des données à un [!UICONTROL destination] lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Paramètres {#settings}

Ces paramètres déterminent la manière dont un [!UICONTROL data source] est identifié, utilisé et partagé. Vous pouvez également activer la création de rapports d’erreur pour les fichiers de données entrants. Pour terminer la section [!UICONTROL Data Source Settings] :

1. Cochez une case [!UICONTROL Data Source Setting] pour appliquer une option à votre [!UICONTROL data source].
2. Cliquez sur **[!UICONTROL Save]**.

## Suppression d’une Source de données {#delete-data-source}

<!-- t_datasource_delete.xml -->

Supprimez un [!UICONTROL data source] dont vous n’avez plus besoin.

>[!NOTE]
>
>Veuillez noter les restrictions suivantes :
>
>* Vous ne pouvez pas supprimer une [audience active ou caractéristique synchronisée du Source de données](../features/traits/client-activity-synced-audience-traits.md).
>* Pour les clients utilisant Adobe Analytics : l’Audience Manager ne vous permet pas de supprimer les sources de données créées automatiquement de vos suites de rapports [!DNL Analytics]. Utilisez le [Core Service](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes) pour démapper ces sources de données.

1. Cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Cochez la case en regard d’une ou de plusieurs sources de données.
Vous pouvez utiliser la zone [!UICONTROL Search] pour localiser les sources de données souhaitées si vous disposez d’une liste longue.
1. Cliquez sur ![](assets/icon_trash.png), puis confirmez la suppression.


>[!MORELIKETHIS]
>
>* [Paramètres de Source de données et options de menu](../features/datasources-list-and-settings.md#settings-menu-options)
