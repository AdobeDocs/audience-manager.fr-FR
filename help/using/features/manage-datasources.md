---
description: Pour créer une source de données, accédez à Données d’audience > Sources de données > Ajouter nouveau et suivez les étapes décrites ici pour chaque section. Des autorisations d’administrateur sont requises pour créer une source de données.
keywords: source de données;gérer la source de données;source de données Audience Manager
seo-description: Pour créer une source de données, accédez à Données d’audience > Sources de données > Ajouter nouveau et suivez les étapes décrites ici pour chaque section. Des autorisations d’administrateur sont requises pour créer une source de données.
seo-title: Create a Data Source
solution: Audience Manager
title: Manage Data Sources
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: 9e1abb305c66a4adf6a42a7873144222491692f9

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

Pour créer une source de données, accédez à **[!UICONTROL Audience Data > Data Sources > Add New]** et suivez les étapes de chaque section décrite ici. Des autorisations d’administrateur sont requises pour créer une source de données.

<!-- create-datasource.xml -->

>[!TIP]
>
>Voir Paramètres de source de [données et Options](../features/datasources-list-and-settings.md#settings-menu-options) de menu pour obtenir des descriptions de ces différents contrôles.

## Détails de la source de données {#details}

Pour compléter la [!UICONTROL Data Source Details] section :

1. Nommez la source de données.
1. *(Facultatif)* Décrivez la source de données. Une description concise permet de définir le rôle ou l’objectif de la source de données.
1. Fournissez un code d’intégration. En règle générale, les codes d’intégration sont facultatifs. Elles sont requises lorsque vous souhaitez :

   * [Créez une source](../features/profile-merge-rules/merge-rules-start.md#create-data-source)de données sur plusieurs périphériques.
   * Utilisez le service [d’ID](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud.
   * Utilisation des règles [de fusion de](../features/profile-merge-rules/merge-rules-start.md)profil.

1. Choisissez un **[!UICONTROL ID Type]**. Les options de type d’ID sont les suivantes :

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obligatoire pour créer une [!UICONTROL Profile Merge Rule]). Remarque : pour certains clients, cette sélection expose les **[!UICONTROL ID Definition]** options.

1. Choose an **[!UICONTROL ID Definition]** option. Les options incluent :

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Contrôles des exportations de données {#export-controls}

[Les contrôles](../features/data-export-controls.md) d’exportation de données sont des règles de classification facultatives que vous pouvez appliquer à une source de données et à une destination. Elles vous empêchent d’envoyer des données vers une destination lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Ces paramètres déterminent la manière dont une source de données est identifiée, utilisée et partagée. Vous pouvez également activer la création de rapports d’erreurs pour les fichiers de données entrants. Pour compléter la [!UICONTROL Data Source Settings] section :

1. Select a  check box to apply an option to your data source.[!UICONTROL Data Source Setting]
2. Cliquez sur **[!UICONTROL Save]**.

>[!MORE_LIKE_THIS]
>
>* [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options)


## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Delete a data source that you no longer need.

>[!NOTE]
>
>Please note the following restrictions:
>
>* You cannot delete an [Active Audience or Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md).
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your  report suites. [!DNL Analytics] Use the [Core Service](https://marketing.adobe.com/resources/help/en_US/mcloud/) to unmap these data sources.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. Cochez la case en regard d’une ou de plusieurs sources de données.
You can use the [!UICONTROL Search] box to locate the desired data sources if you have a long list.
1. Click  ![](assets/icon_trash.png), then confirm the deletion.