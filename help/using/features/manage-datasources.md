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
source-git-commit: bda66cb9aaee3a40ae64dda100f42b88696a027e
workflow-type: tm+mt
source-wordcount: '403'
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

Pour terminer la section [!UICONTROL Data Source Details], renseignez les champs suivants :

1. **[!UICONTROL Name]** : attribuez un nom à la source de données.
1. **[!UICONTROL Description]** (facultatif) : entrez une description pour votre source de données afin de vous aider à définir le rôle ou l’objectif de la source de données.
1. **[!UICONTROL Integration Code]** (facultatif) : saisissez un code d’intégration. Ces codes sont requis lorsque vous souhaitez :
   * [Créez une source de données multi-appareils](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Utilisez le [service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr).
   * Utilisation des [stratégies de fusion de profils](../features/profile-merge-rules/merge-rules-start.md).
1. **[!UICONTROL Namespace]** (lecture seule) : ce champ est en lecture seule et est généré automatiquement lors de l’enregistrement de la source de données. Si vous souhaitez exporter des segments d’Audience Manager vers Experience Platform, vous devez créer un [espace de noms d’identité](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=fr#manage-namespaces) correspondant dans Experience Platform, en utilisant la valeur générée automatiquement comme espace de noms [symbole d’identité](https://experienceleague.adobe.com/fr/docs/experience-platform/identity/features/namespaces#components-of-a-namespace) dans Experience Platform.
1. **[!UICONTROL ID Type]** : sélectionnez le type d’ID que cette source de données contiendra :
   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obligatoire pour créer un [!UICONTROL Profile Merge Rule]). Remarque : pour certains clients, cette sélection expose les options **[!UICONTROL ID Definition]**.
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
>* Pour les clients utilisant Adobe Analytics : l’Audience Manager ne vous permet pas de supprimer les sources de données créées automatiquement de vos suites de rapports [!DNL Analytics]. Utilisez le [Core Service](https://experienceleague.adobe.com/fr/docs/core-services/interface/services/customer-attributes/attributes) pour démapper ces sources de données.

1. Cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Cochez la case en regard d’une ou de plusieurs sources de données.
Vous pouvez utiliser la zone [!UICONTROL Search] pour localiser les sources de données souhaitées si vous disposez d’une liste longue.
1. Cliquez sur ![](assets/icon_trash.png), puis confirmez la suppression.


>[!MORELIKETHIS]
>
>* [Paramètres de Source de données et options de menu](../features/datasources-list-and-settings.md#settings-menu-options)
