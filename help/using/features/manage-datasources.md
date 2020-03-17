---
description: Pour créer une source de données, accédez à   de données > Sources de données > Nouveau et suivez les étapes décrites ici pour chaque section. Des autorisations d’administrateur sont requises pour créer une source de données.
keywords: data sources;manage data source;audience manager data source
seo-description: Pour créer une source de données, accédez à   de données > Sources de données > Nouveau et suivez les étapes décrites ici pour chaque section. Des autorisations d’administrateur sont requises pour créer une source de données.
seo-title: Création d’une source de données
solution: Audience Manager
title: Gestion des sources de données
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

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
   * Utilisez [Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Utilisation des règles [de fusion](../features/profile-merge-rules/merge-rules-start.md)de

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

Ces paramètres déterminent la manière dont une source de données est identifiée, utilisée et partagée. Vous pouvez également activer les  d’erreur pour les fichiers de données entrants. Pour compléter la [!UICONTROL Data Source Settings] section :

1. Sélectionnez une [!UICONTROL Data Source Setting] case à cocher pour appliquer une option à votre source de données.
2. Cliquez sur **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Paramètres de source de données et options de menu](../features/datasources-list-and-settings.md#settings-menu-options)


## Suppression d’une source de données {#delete-data-source}

<!-- t_datasource_delete.xml -->

Supprimez une source de données dont vous n’avez plus besoin.

>[!NOTE]
>
>Veuillez prendre note des restrictions suivantes :
>
>* Vous ne pouvez pas supprimer un [actif ou un paramètre](../features/traits/client-activity-synced-audience-traits.md)synchronisé de source de données.
>* Pour les clients qui utilisent Adobe Analytics :  Gestionnaire de  de ne vous permet pas de supprimer les sources de données créées automatiquement de vos suites de [!DNL Analytics] rapports. Utilisez le service [principal](https://marketing.adobe.com/resources/help/en_US/mcloud/) pour annuler le mappage de ces sources de données.


1. Cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Cochez la case en regard d’une ou de plusieurs sources de données.
Vous pouvez utiliser la [!UICONTROL Search] zone pour localiser les sources de données de votre choix si vous disposez d’un  long.
1. Cliquez sur ![](assets/icon_trash.png), puis confirmez la suppression.