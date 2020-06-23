---
description: L'optimisation des Audiences pour les annonceurs peut vous aider à identifier les opportunités de performances potentielles pour les segments d'Audience Manager dans vos campagnes de médias payants. Ces rapports combinent des données de performances de campagne au niveau du journal avec des mesures de segments d’Audience Manager afin d’alimenter les optimisations centrées sur les segments et d’offrir un canal efficace.
seo-description: L'optimisation des Audiences pour les annonceurs peut vous aider à identifier les opportunités de performances potentielles pour les segments d'Audience Manager dans vos campagnes de médias payants. Ces rapports combinent des données de performances de campagne au niveau du journal avec des mesures de segments d’Audience Manager afin d’alimenter les optimisations centrées sur les segments et d’offrir un canal efficace.
seo-title: Optimisation des Audiences pour les annonceurs
solution: Audience Manager
title: Optimisation des Audiences pour les annonceurs
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: 9326b61f27f6c529567ab9b26694998f0b5dafb3
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---


# [!UICONTROL Audience Optimization] pour les annonceurs{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] pour les annonceurs peuvent vous aider à identifier les opportunités de performances potentielles pour les segments d’Audience Manager dans vos campagnes de médias payants. Ces rapports combinent des données de performances de campagne au niveau du journal avec des [!UICONTROL segment] mesures d’Audience Manager afin d’alimenter les optimisations centrées sur les segments et d’offrir une combinaison de canaux efficace.

## Méthodes d&#39;assimilation des données {#data-ingestion-methods}

Vous pouvez envoyer des données à [!DNL Audience Manager] utiliser dans ces rapports par l&#39;une de ces méthodes. Parfois, les clients envoient des données selon les deux méthodes. Cela permet de s’assurer que vos rapports contiennent les informations les plus complètes et les plus précises sur un visiteur. Pour utiliser les [!UICONTROL Audience Optimization] rapports, vos appels de événement doivent inclure *tous les* paramètres répertoriés dans la documentation [Aperçu et Mappages des fichiers](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) de métadonnées. Vous pouvez envoyer des données au moyen des méthodes suivantes, répertoriées ci-dessous.

* Appels de pixels : Pour transmettre les paramètres de métadonnées requis pour [!DNL Audience Manager] voir [Capture des données de clic Campaign via des appels](../../../integration/media-data-integration/click-data-pixels.md) en pixels et [Capture des données d’impression Campaign via des appels](../../../integration/media-data-integration/impression-data-pixels.md)en pixels.

* Fichiers de données : Si vous souhaitez utiliser ces rapports pour analyser vos propres données ou celles provenant d’une source qui n’est pas intégrée à [!DNL Audience Manager], vous devez créer et télécharger des fichiers de données et de métadonnées pour ces données. Pour plus d’informations, voir Fichiers de [données pour les rapports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) d’optimisation des Audiences et Fichiers de [données et de métadonnées pour les rapports](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)d’optimisation des Audiences.

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Le type de rapports que vous pouvez vue dépend du [!UICONTROL RBAC] groupe auquel vous êtes affecté. Voir [Administration](../../../features/administration/administration-overview.md) et [création d’un groupe](../../../features/administration/administration-overview.md#create-group) pour plus d’informations.

[!UICONTROL RBAC] les groupes doivent avoir certaines sources de données configurées pour pouvoir vue les [!UICONTROL Audience Optimization] rapports. Votre [!DNL Audience Manager] consultant va les configurer [!UICONTROL data sources] pour vous. Plus [!UICONTROL data sources] dans chaque groupe d’ [!UICONTROL RBAC] utilisateurs, plus ces membres ont accès aux données. Au minimum, votre consultant doit configurer au moins l&#39;un des éléments [!UICONTROL data sources]:

* Annonceur [!UICONTROL data source ]
* Marque [!UICONTROL data source]
* Plate-forme [!UICONTROL data source]

Les utilisateurs appartenant à plusieurs groupes d’ [!UICONTROL RBAC] utilisateurs peuvent basculer entre la vue de chaque groupe. Les données affichées seront mises à jour pour respecter le groupe sélectionné. Si votre société n’utilise pas [!UICONTROL RBAC], tous les utilisateurs disposent de privilèges d’administrateur et d’un accès à tous les utilisateurs [!UICONTROL data sources] (groupes de conversion).

## Groupes de conversion {#conversion-groups}

Dans les [!UICONTROL Audience Optimization] rapports, **[!UICONTROL Conversion Groups]** sont synonymes [!UICONTROL data sources] qui contiennent au moins une caractéristique de conversion. [!UICONTROL Data sources] qui ne contiennent pas au moins une caractéristique de conversion n’apparaissent pas dans les [!UICONTROL Audience Optimization] rapports. Vous pouvez vue les caractéristiques de conversion des groupes de conversion dans le rapport Caractéristiques [de conversion](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) reportées.
