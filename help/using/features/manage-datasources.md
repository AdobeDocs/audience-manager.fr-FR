---
description: Pour créer une source de données, accédez à Audience Data > Data Sources > Ajouter New et suivez les étapes décrites ici pour chaque section. Les autorisations d’administrateur sont requises pour créer une source de données.
keywords: data sources;manage data source;audience manager data source
seo-description: Pour créer une source de données, accédez à Audience Data > Data Sources > Ajouter New et suivez les étapes décrites ici pour chaque section. Les autorisations d’administrateur sont requises pour créer une source de données.
seo-title: Création d’une source de données
solution: Audience Manager
title: Gérer les sources de données
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

Pour créer une source de données, accédez à **[!UICONTROL Audience Data > Data Sources > Add New]** et suivez les étapes décrites dans cette section. Les autorisations d’administrateur sont requises pour créer une source de données.

<!-- create-datasource.xml -->

>[!TIP]
>
>Voir Paramètres de la source de [données et Options](../features/datasources-list-and-settings.md#settings-menu-options) de menu pour obtenir des descriptions de ces différents contrôles.

## Détails de la source de données {#details}

Pour compléter la [!UICONTROL Data Source Details] section :

1. Nommez la source de données.
1. *(Facultatif)* Décrivez la source de données. Une description concise vous permet de définir le rôle ou l’objectif de la source de données.
1. Fournissez un code d’intégration. En règle générale, les codes d’intégration sont facultatifs. Ils sont nécessaires lorsque vous souhaitez :

   * [Créez une source](../features/profile-merge-rules/merge-rules-start.md#create-data-source)de données sur plusieurs périphériques.
   * Utilisez le service [d’identité](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform.
   * Utilisation des règles [de fusion](../features/profile-merge-rules/merge-rules-start.md)de Profil.

1. Choisis un **[!UICONTROL ID Type]**. Les options de type d’ID sont les suivantes :

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obligatoire pour créer un [!UICONTROL Profile Merge Rule]). Remarque : pour certains clients, cette sélection expose les **[!UICONTROL ID Definition]** options.

1. Choose an **[!UICONTROL ID Definition]** option. Les options incluent :

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Contrôles des exportations de données {#export-controls}

[Les contrôles](../features/data-export-controls.md) d’exportation de données sont des règles de classification facultatives que vous pouvez appliquer à une source de données et à une destination. Ils vous empêchent d’envoyer des données vers une destination lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Ces paramètres déterminent comment une source de données est identifiée, utilisée et partagée. Vous pouvez également activer le rapports d’erreur pour les fichiers de données entrants. Pour compléter la [!UICONTROL Data Source Settings] section :

1. Cochez une [!UICONTROL Data Source Setting] case pour appliquer une option à votre source de données.
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
>* Vous ne pouvez pas supprimer une Audience [active ou une caractéristique](../features/traits/client-activity-synced-audience-traits.md)synchronisée de source de données.
>* Pour les clients qui utilisent Adobe Analytics : Audience Manager ne vous permet pas de supprimer les sources de données créées automatiquement à partir de vos suites de [!DNL Analytics] rapports. Utilisez le service [](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) principal pour annuler le mappage de ces sources de données.


1. Cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Cochez la case en regard d’une ou de plusieurs sources de données.
Vous pouvez utiliser la [!UICONTROL Search] zone pour localiser les sources de données de votre choix si votre liste est longue.
1. Cliquez sur ![](assets/icon_trash.png), puis confirmez la suppression.