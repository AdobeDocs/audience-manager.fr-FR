---
description: L’Audience Optimization pour les annonceurs peut vous aider à identifier les opportunités de performances potentielles pour les segments d’Audience Manager dans vos campagnes publicitaires payantes. Ces rapports combinent des données de performances de campagne au niveau du journal avec des mesures de segments d’Audience Manager afin d’alimenter les optimisations centrées sur les segments et d’offrir un canal efficace.
seo-description: L’Audience Optimization pour les annonceurs peut vous aider à identifier les opportunités de performances potentielles pour les segments d’Audience Manager dans vos campagnes publicitaires payantes. Ces rapports combinent des données de performances de campagne au niveau du journal avec des mesures de segments d’Audience Manager afin d’alimenter les optimisations centrées sur les segments et d’offrir un canal efficace.
seo-title: Audience Optimization pour les annonceurs
solution: Audience Manager
title: Audience Optimization pour les annonceurs
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 2%

---


# [!UICONTROL Audience Optimization] pour les annonceurs{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] pour les annonceurs peuvent vous aider à identifier les opportunités de performances potentielles pour les segments d’Audience Manager dans vos campagnes de médias payants. Ces rapports combinent des données de performances de campagne au niveau du journal avec des mesures d&#39;Audience Manager [!UICONTROL segment] afin d&#39;alimenter les optimisations centrées sur les segments et d&#39;offrir un mélange efficace de canaux.

## Méthodes d&#39;assimilation des données {#data-ingestion-methods}

Vous pouvez envoyer des données à [!DNL Audience Manager] pour les utiliser dans ces rapports en utilisant l&#39;une de ces méthodes. Parfois, les clients envoient des données selon les deux méthodes. Cela permet de s’assurer que vos rapports contiennent les informations les plus complètes et les plus précises sur un visiteur. Pour utiliser les rapports [!UICONTROL Audience Optimization], vos appels de événement doivent inclure *tous* des paramètres répertoriés dans la documentation [Aperçu et mappages pour les fichiers de métadonnées](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md). Vous pouvez envoyer des données au moyen des méthodes suivantes, répertoriées ci-dessous.

* Appels de pixels : Pour transmettre les paramètres de métadonnées requis à [!DNL Audience Manager], voir [Capture des données de clic Campaign via des appels de pixels](../../../integration/media-data-integration/click-data-pixels.md) et [Capture des données d&#39;impression Campaign via des appels de pixels](../../../integration/media-data-integration/impression-data-pixels.md).

* Fichiers de données : Si vous souhaitez utiliser ces rapports pour analyser vos propres données ou données à partir d’une source qui n’est pas intégrée à [!DNL Audience Manager], vous devez créer et télécharger des fichiers de données et de métadonnées pour ces données. Pour plus d’informations, voir [Fichiers de données pour les rapports d’Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) et [Fichiers de données et de métadonnées pour les rapports d’Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC)  {#rbac}

Le type de rapports auquel vous pouvez vue dépend du groupe [!UICONTROL RBAC] auquel vous êtes affecté. Voir [Administration](../../../features/administration/administration-overview.md) et [Créer un groupe](../../../features/administration/administration-overview.md#create-group) pour plus d’informations.

[!UICONTROL RBAC] les groupes doivent avoir certaines sources de données configurées pour pouvoir vue les  [!UICONTROL Audience Optimization] rapports. Votre [!DNL Audience Manager] consultant va configurer ces [!UICONTROL data sources] pour vous. Plus [!UICONTROL data sources] dans chaque groupe d&#39;utilisateurs [!UICONTROL RBAC], plus les membres du groupe auront accès aux données. Au minimum, votre consultant va configurer au moins l&#39;un des [!UICONTROL data sources] suivants :

* Annonceur [!UICONTROL data source ]
* Marque [!UICONTROL data source]
* Plate-forme [!UICONTROL data source]

Les utilisateurs appartenant à plusieurs groupes d&#39;utilisateurs [!UICONTROL RBAC] peuvent basculer entre la vue de chaque groupe. Les données affichées seront mises à jour pour respecter le groupe sélectionné. Si votre société n’utilise pas [!UICONTROL RBAC], tous les utilisateurs disposent de privilèges d’administrateur et d’un accès à tous les [!UICONTROL data sources] (groupes de conversion).

## Groupes de conversion {#conversion-groups}

Dans les rapports [!UICONTROL Audience Optimization], **[!UICONTROL Conversion Groups]** sont synonymes de [!UICONTROL data sources] qui contiennent au moins une caractéristique de conversion. [!UICONTROL Data sources] qui ne contiennent pas au moins une caractéristique de conversion n’apparaissent pas dans les  [!UICONTROL Audience Optimization] rapports. Vous pouvez vue les caractéristiques de conversion des groupes de conversion dans le rapport [Caractéristiques de conversion reportées](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md).
