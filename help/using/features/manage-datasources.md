---
description: Pour créer une source de données, accédez à Audience Data > Data Sources > Add New et suivez les étapes décrites ici pour chaque section. Des autorisations d’administrateur sont requises pour créer une source de données.
keywords: sources de données;gérer la source de données;source de données audience manager
seo-description: Pour créer une source de données, accédez à Audience Data > Data Sources > Add New et suivez les étapes décrites ici pour chaque section. Des autorisations d’administrateur sont requises pour créer une source de données.
seo-title: Création d’une source de données
solution: Audience Manager
title: Gérer les sources de données
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Sources de données
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 3%

---

# Gérer des [!UICONTROL Data Sources] {#manage-data-sources}

## Créez un [!UICONTROL Data Source] {#create-data-source}

Pour créer un [!UICONTROL data source], accédez à **[!UICONTROL Audience Data > Data Sources > Add New]** et suivez les étapes décrites ici pour chaque section. Des autorisations d’administrateur sont requises pour créer une balise [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Voir [Paramètres de source de données et options de menu](../features/datasources-list-and-settings.md#settings-menu-options) pour obtenir des descriptions de ces différents contrôles.

## [!UICONTROL Data Source] Détails {#details}

Pour terminer la section [!UICONTROL Data Source Details] :

1. Nommez le [!UICONTROL data source].
1. *(Facultatif)* Décrivez le  [!UICONTROL data source]. Une description concise permet de définir le rôle ou l’objectif de [!UICONTROL data source].
1. Fournissez un [!UICONTROL integration code]. En règle générale, [!UICONTROL integration codes] est facultatif. Elles sont requises lorsque vous souhaitez :

   * [Création d’une source de données multi-appareils](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Utilisez le [service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Utilisation de [stratégies de fusion de profils](../features/profile-merge-rules/merge-rules-start.md).

1. Sélectionnez un **[!UICONTROL ID Type]**. [!UICONTROL ID Type] les options disponibles sont les suivantes :

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obligatoire pour créer un  [!UICONTROL Profile Merge Rule]). Remarque : pour certains clients, cette sélection expose les options **[!UICONTROL ID Definition]**.

1. Choisissez une option **[!UICONTROL ID Definition]**. Les options incluent :

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Les ](../features/data-export-controls.md) contrôles d’exportation de données sont des règles de classification facultatives que vous pouvez appliquer à un  [!UICONTROL data source] et à  [!UICONTROL destination]. Elles vous empêchent d’envoyer des données à une [!UICONTROL destination] lorsque cette action enfreint un accord de confidentialité des données ou d’utilisation. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Paramètres {#settings}

Ces paramètres déterminent la manière dont une balise [!UICONTROL data source] est identifiée, utilisée et partagée. Vous pouvez également activer la création de rapports d’erreur pour les fichiers de données entrants. Pour terminer la section [!UICONTROL Data Source Settings] :

1. Cochez une case [!UICONTROL Data Source Setting] pour appliquer une option à votre [!UICONTROL data source].
2. Cliquez sur **[!UICONTROL Save]**.

## Suppression d’une source de données {#delete-data-source}

<!-- t_datasource_delete.xml -->

Supprimez une balise [!UICONTROL data source] dont vous n’avez plus besoin.

>[!NOTE]
>
>Veuillez noter les restrictions suivantes :
>
>* Vous ne pouvez pas supprimer une [audience Principale ou une caractéristique synchronisée de source de données](../features/traits/client-activity-synced-audience-traits.md).
>* Pour les clients qui utilisent Adobe Analytics : L’Audience Manager ne vous permet pas de supprimer des sources de données créées automatiquement à partir de vos suites de rapports [!DNL Analytics]. Utilisez le [service principal](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) pour annuler le mappage de ces sources de données.


1. Cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Cochez la case en regard d’une ou de plusieurs sources de données.
Vous pouvez utiliser la zone [!UICONTROL Search] pour localiser les sources de données souhaitées si vous disposez d’une liste longue.
1. Cliquez sur ![](assets/icon_trash.png), puis confirmez la suppression.


>[!MORELIKETHIS]
>
>* [Paramètres de source de données et options de menu](../features/datasources-list-and-settings.md#settings-menu-options)

