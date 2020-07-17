---
description: Pour créer une source de données, accédez à Audience Data > Data Sources > Ajouter New et suivez les étapes décrites ici pour chaque section. Les autorisations d’administrateur sont requises pour créer une source de données.
keywords: data sources;manage data source;audience manager data source
seo-description: Pour créer une source de données, accédez à Audience Data > Data Sources > Ajouter New et suivez les étapes décrites ici pour chaque section. Les autorisations d’administrateur sont requises pour créer une source de données.
seo-title: Création d’une source de données
solution: Audience Manager
title: Gérer les sources de données
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 5%

---


# Gérer des [!UICONTROL Data Sources] {#manage-data-sources}

## Créez un [!UICONTROL Data Source] {#create-data-source}

Pour créer une nouvelle section [!UICONTROL data source], accédez à **[!UICONTROL Audience Data > Data Sources > Add New]** et suivez les étapes décrites ici. Les autorisations d’administrateur sont requises pour créer un [!UICONTROL data source]fichier.

<!-- create-datasource.xml -->

>[!TIP]
>
>Voir Paramètres de la source de [données et Options](../features/datasources-list-and-settings.md#settings-menu-options) de menu pour obtenir des descriptions de ces différents contrôles.

## [!UICONTROL Data Source] Détails {#details}

Pour compléter la [!UICONTROL Data Source Details] section :

1. Nommez le [!UICONTROL data source].
1. *(Facultatif)* Décrivez le [!UICONTROL data source]. Une description concise vous permet de définir le rôle ou l’objectif de la [!UICONTROL data source]variable.
1. Fournissez un [!UICONTROL integration code]. En règle générale, [!UICONTROL integration codes] elles sont facultatives. Ils sont nécessaires lorsque vous souhaitez :

   * [Créez une source](../features/profile-merge-rules/merge-rules-start.md#create-data-source)de données sur plusieurs périphériques.
   * Use the [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/fr-FR/id-service/using/home.html).
   * Utilisation des règles [de fusion](../features/profile-merge-rules/merge-rules-start.md)de Profil.

1. Choisis un **[!UICONTROL ID Type]**. [!UICONTROL ID Type] sont disponibles :

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Obligatoire pour créer un [!UICONTROL Profile Merge Rule]). Remarque : pour certains clients, cette sélection expose les **[!UICONTROL ID Definition]** options.

1. Choose an **[!UICONTROL ID Definition]** option. Les options incluent :

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Les contrôles](../features/data-export-controls.md) d’exportation de données sont des règles de classification facultatives que vous pouvez appliquer à un [!UICONTROL data source] et [!UICONTROL destination]. Ils vous empêchent d’envoyer des données à un [!UICONTROL destination] utilisateur lorsque cette action enfreint un accord de confidentialité ou d’utilisation des données. Ignorez cette section si vous n’utilisez pas [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Paramètres {#settings}

Ces paramètres déterminent comment un [!UICONTROL data source] fichier est identifié, utilisé et partagé. Vous pouvez également activer le rapports d’erreur pour les fichiers de données entrants. Pour compléter la [!UICONTROL Data Source Settings] section :

1. Cochez une [!UICONTROL Data Source Setting] case pour appliquer une option à votre [!UICONTROL data source]application.
2. Cliquez sur **[!UICONTROL Save]**.

## Suppression d’une source de données {#delete-data-source}

<!-- t_datasource_delete.xml -->

Supprimez un [!UICONTROL data source] objet dont vous n’avez plus besoin.

>[!NOTE]
>
>Veuillez prendre note des restrictions suivantes :
>
>* Vous ne pouvez pas supprimer une Audience [active ou une caractéristique](../features/traits/client-activity-synced-audience-traits.md)synchronisée de source de données.
>* Pour les clients qui utilisent Adobe Analytics : L&#39;Audience Manager ne vous permet pas de supprimer les sources de données créées automatiquement à partir de vos [!DNL Analytics] Report Suites. Utilisez le service [](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) principal pour annuler le mappage de ces sources de données.


1. Cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Cochez la case en regard d’une ou de plusieurs sources de données.
Vous pouvez utiliser la [!UICONTROL Search] zone pour localiser les sources de données de votre choix si votre liste est longue.
1. Cliquez sur ![](assets/icon_trash.png), puis confirmez la suppression.


>[!MORELIKETHIS]
>
>* [Paramètres de source de données et options de menu](../features/datasources-list-and-settings.md#settings-menu-options)