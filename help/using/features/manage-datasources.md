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
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 2%

---

# Gérer des [!UICONTROL Data Sources] {#manage-data-sources}

## Créez un [!UICONTROL Data Source] {#create-data-source}

Pour créer une [!UICONTROL data source], accédez à **[!UICONTROL Audience Data > Data Sources > Add New]** et suivez les étapes décrites ici pour chaque section. Des autorisations d’administrateur sont requises pour créer une [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Voir [Paramètres de source de données et options de menu](../features/datasources-list-and-settings.md#settings-menu-options) pour obtenir des descriptions de ces différents contrôles.

## [!UICONTROL Data Source] Détails {#details}

Pour terminer la [!UICONTROL Data Source Details] section :

1. Attribuez un nom au [!UICONTROL data source].
1. *(Facultatif)* Décrivez la variable [!UICONTROL data source]. Une description concise vous permet de définir le rôle ou l’objectif de la fonction [!UICONTROL data source].
1. Fournissez un [!UICONTROL integration code]. En général, [!UICONTROL integration codes] sont facultatives. Elles sont requises lorsque vous souhaitez :

   * [Création d’une source de données multi-appareils](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Utilisez la variable [Service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Utilisation de [Stratégies de fusion de profils](../features/profile-merge-rules/merge-rules-start.md).

1. Choisissez une **[!UICONTROL ID Type]**. [!UICONTROL ID Type] les options disponibles sont les suivantes :

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obligatoire pour créer une [!UICONTROL Profile Merge Rule]). Remarque : pour certains clients, cette sélection expose la variable **[!UICONTROL ID Definition]** options.

   >[!NOTE]
   >
   >Pour chaque organisation configurée pour Audience Manager et Experience Platform, même si le partage de segments n’est pas configuré entre les deux applications, lorsque vous créez une source de données multi-appareils, une [namespace d’identité](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) est créé dans Experience Platform.

1. Choisissez une **[!UICONTROL ID Definition]** . Les options incluent :

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Contrôles des exportations de données](../features/data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à un [!UICONTROL data source] et [!UICONTROL destination]. Ils vous empêchent d’envoyer des données à un [!UICONTROL destination] lorsque cette action enfreint un accord de confidentialité des données ou d’utilisation. Ignorer cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Paramètres {#settings}

Ces paramètres déterminent comment une [!UICONTROL data source] est identifié, utilisé et partagé. Vous pouvez également activer la création de rapports d’erreur pour les fichiers de données entrants. Pour terminer la [!UICONTROL Data Source Settings] section :

1. Sélectionnez une [!UICONTROL Data Source Setting] pour appliquer une option à votre [!UICONTROL data source].
2. Cliquez sur **[!UICONTROL Save]**.

## Suppression d’une source de données {#delete-data-source}

<!-- t_datasource_delete.xml -->

Suppression d’une [!UICONTROL data source] que vous n&#39;avez plus besoin.

>[!NOTE]
>
>Veuillez noter les restrictions suivantes :
>
>* Vous ne pouvez pas supprimer une [Principale audience ou caractéristique synchronisée de la source de données](../features/traits/client-activity-synced-audience-traits.md).
>* Pour les clients qui utilisent Adobe Analytics : L’Audience Manager ne vous permet pas de supprimer les sources de données créées automatiquement de votre [!DNL Analytics] suites de rapports. Utilisez la variable [Core Service](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) pour annuler le mappage de ces sources de données.


1. Cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Cochez la case en regard d’une ou de plusieurs sources de données.
Vous pouvez utiliser la variable [!UICONTROL Search] pour localiser les sources de données souhaitées si vous disposez d’une liste longue.
1. Cliquez sur  ![](assets/icon_trash.png), puis confirmez la suppression.


>[!MORELIKETHIS]
>
>* [Paramètres de source de données et options de menu](../features/datasources-list-and-settings.md#settings-menu-options)

