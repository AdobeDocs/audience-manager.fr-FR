---
description: Pour créer une source de données, accédez à Données d'audience > Sources de données > Ajouter nouveau et suivez les étapes de chaque section décrite ici. Les autorisations d'administrateur sont requises pour créer une source de données.
keywords: cdf ; flux de données personnalisé
seo-description: Pour créer une source de données, accédez à Données d'audience > Sources de données > Ajouter nouveau et suivez les étapes de chaque section décrite ici. Les autorisations d'administrateur sont requises pour créer une source de données.
seo-title: Création d'une source de données
solution: Audience Manager
title: Création d'une source de données
uuid: 4 df 65 bcb -9 ad 9-4 b 72-a 71 e -8918 b 43 d 4850
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

To create a new data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. Les autorisations d&#39;administrateur sont requises pour créer une source de données.

<!-- create-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. Nommez la source de données.
1. *(Facultatif)* Décrivez la source de données. Une description concise permet de définir le rôle ou le rôle de la source de données.
1. Fournissez un code d&#39;intégration. En règle générale, les codes d&#39;intégration sont facultatifs. Ils sont obligatoires lorsque vous voulez :

   * [Créez une source de données sur plusieurs périphériques](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Use the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Work with [Profile Merge Rules](../features/profile-merge-rules/merge-rules-start.md).

1. Choose an **[!UICONTROL ID Type]**. Les options Type d&#39;ID incluent :

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Requis pour créer un [!UICONTROL Profile Merge Rule]). Note, for some customers, this selection exposes the **[!UICONTROL ID Definition]** options.

1. Choose an **[!UICONTROL ID Definition]** option. Les options incluent :

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Contrôles des exportations de données {#export-controls}

[Les contrôles d&#39;exportation de données](../features/data-export-controls.md) sont des règles de classification facultatives que vous pouvez appliquer à une source de données et à une destination. Elles vous empêchent d&#39;envoyer des données à une destination lorsque cette action enfreint un accord de confidentialité ou d&#39;utilisation des données. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Ces paramètres déterminent comment une source de données est identifiée, utilisée et partagée. Vous pouvez également activer la création de rapports d&#39;erreur pour les fichiers de données entrants. To complete the [!UICONTROL Data Source Settings] section:

1. Select a [!UICONTROL Data Source Setting] check box to apply an option to your data source.
2. Cliquez sur **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Paramètres de source de données et options de menu](../features/datasources-list-and-settings.md#settings-menu-options)


## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Supprimez une source de données dont vous n&#39;avez plus besoin.

>[!NOTE]
>
>Veuillez noter les restrictions suivantes :
>
>* You cannot delete an [Active Audience or Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md).
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your [!DNL Analytics] report suites. Use the [Core Service](https://marketing.adobe.com/resources/help/en_US/mcloud/) to unmap these data sources.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. Cochez la case en regard d&#39;une ou de plusieurs sources de données.
You can use the [!UICONTROL Search] box to locate the desired data sources if you have a long list.
1. Click  ![](assets/icon_trash.png), then confirm the deletion.