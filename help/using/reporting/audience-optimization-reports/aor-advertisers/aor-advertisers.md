---
description: Audience Optimization pour les annonceurs peut vous aider à identifier les opportunités de performances potentielles pour les segments d’Audience Manager dans vos campagnes médias payantes. Ces rapports combinent les données de performances de campagne au niveau du journal avec les mesures de segment d’Audience Manager afin d’informer les optimisations centrées sur les segments et un mix de canaux efficace.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization pour les annonceurs
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---

# [!UICONTROL Audience Optimization] pour les annonceurs{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] pour les annonceurs peut vous aider à identifier les opportunités de performances potentielles pour les segments d’Audience Manager dans vos campagnes médias payantes. Ces rapports combinent les données de performances de campagne au niveau du journal avec les mesures de [!UICONTROL segment] d’Audience Manager afin d’informer les optimisations centrées sur les segments et un bouquet de canaux efficace.

## Méthodes d’ingestion de données {#data-ingestion-methods}

Vous pouvez envoyer des données à [!DNL Audience Manager] pour les utiliser dans ces rapports par l’une de ces méthodes. Parfois, les clients envoient des données par les deux méthodes. Cela permet de s’assurer que vos rapports contiennent les informations les plus complètes et les plus précises sur un visiteur. Pour utiliser les rapports [!UICONTROL Audience Optimization], vos appels d’événement doivent inclure *tous* les paramètres répertoriés dans la documentation [Présentation et mappages des fichiers de métadonnées](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md). Vous pouvez envoyer des données par le biais des méthodes suivantes répertoriées ci-dessous.

* Appels de pixel : pour transmettre les paramètres de métadonnées requis à [!DNL Audience Manager], voir [Capture de données de clics Campaign via des appels de pixel](../../../integration/media-data-integration/click-data-pixels.md) et [Capture de données d’impressions Campaign via des appels de pixel](../../../integration/media-data-integration/impression-data-pixels.md).

* Fichiers de données : si vous souhaitez utiliser ces rapports pour analyser vos propres données ou les données d’une source qui n’est pas intégrée à [!DNL Audience Manager], vous devez créer et charger des données et des fichiers de métadonnées pour ces données. Pour plus d’informations, voir [Fichiers de données pour les rapports Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) et [Fichiers de données et de métadonnées pour les rapports Audience Optimization](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Le type de rapports que vous pouvez afficher dépend du groupe de [!UICONTROL RBAC] auquel vous êtes affecté. Voir [Administration](../../../features/administration/administration-overview.md) et [Création d’un groupe](../../../features/administration/administration-overview.md#create-group) pour plus d’informations.

Des sources de données doivent être configurées pour que les groupes de [!UICONTROL RBAC] puissent afficher les rapports [!UICONTROL Audience Optimization]. Votre consultant [!DNL Audience Manager] configurera ces [!UICONTROL data sources] pour vous. Plus il y a d’[!UICONTROL data sources] dans chaque groupe d’utilisateurs [!UICONTROL RBAC], plus ces membres du groupe auront accès aux données. Au minimum, votre consultant configurera au moins l’une des [!UICONTROL data sources] suivantes :

* [!UICONTROL data source] de l’annonceur
* Brand [!UICONTROL data source]
* [!UICONTROL data source] de la plateforme

Les utilisateurs appartenant à plusieurs groupes d’utilisateurs [!UICONTROL RBAC] peuvent basculer entre les vues de chaque groupe. Les données affichées seront mises à jour pour respecter le groupe sélectionné. Si votre société n’utilise pas [!UICONTROL RBAC], tous les utilisateurs disposeront de droits d’administrateur et d’accès à tous les [!UICONTROL data sources] (groupes de conversion).

## Groupes de conversion {#conversion-groups}

Dans les rapports [!UICONTROL Audience Optimization], **[!UICONTROL Conversion Groups]** sont synonymes d’[!UICONTROL data sources] contenant au moins une caractéristique de conversion. Les [!UICONTROL Data sources] qui ne contiennent pas au moins une caractéristique de conversion n’apparaissent pas dans les rapports [!UICONTROL Audience Optimization]. Vous pouvez afficher les caractéristiques de conversion des groupes de conversion dans le rapport [Caractéristiques de conversion signalées](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md).
