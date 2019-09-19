---
description: L’optimisation de l’audience pour les annonceurs peut vous aider à identifier les opportunités de performances potentielles pour les segments d’Audience Manager dans vos campagnes de médias payants. Ces rapports combinent les données de performances de campagne au niveau du journal avec les mesures de segments d’Audience Manager pour informer les optimisations centrées sur les segments et une combinaison efficace de canaux.
seo-description: L’optimisation de l’audience pour les annonceurs peut vous aider à identifier les opportunités de performances potentielles pour les segments d’Audience Manager dans vos campagnes de médias payants. Ces rapports combinent les données de performances de campagne au niveau du journal avec les mesures de segments d’Audience Manager pour informer les optimisations centrées sur les segments et une combinaison efficace de canaux.
seo-title: Optimisation de l’audience pour les annonceurs
solution: Audience Manager
title: Optimisation de l’audience pour les annonceurs
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

L’optimisation de l’audience pour les annonceurs peut vous aider à identifier les opportunités de performances potentielles pour les segments d’Audience Manager dans vos campagnes de médias payants. Ces rapports combinent les données de performances de campagne au niveau du journal avec les mesures de segments d’Audience Manager pour informer les optimisations centrées sur les segments et une combinaison efficace de canaux.

## Méthodes d'assimilation des données {#data-ingestion-methods}

Vous pouvez envoyer des données à [!DNL Audience Manager] utiliser dans ces rapports par l’une de ces méthodes. Parfois, les clients envoient des données par les deux méthodes. Cela permet de s’assurer que vos rapports contiennent les informations les plus complètes et les plus précises sur un visiteur. Pour utiliser les [!UICONTROL Audience Optimization] rapports, vos appels d’événement doivent inclure *tous les* paramètres répertoriés dans la documentation [Aperçu et Mappages des fichiers](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) de métadonnées. Vous pouvez envoyer des données par les méthodes suivantes, répertoriées ci-dessous.

* Appels de pixels : Pour transmettre les paramètres de métadonnées requis, reportez-vous aux sections [!DNL Audience Manager] Capture des données de clic de campagne par appels [de pixels et](../../../integration/media-data-integration/click-data-pixels.md) Capture des données d’impression de campagne par appels [](../../../integration/media-data-integration/impression-data-pixels.md)de pixels.

* Fichiers de données : Si vous souhaitez utiliser ces rapports pour analyser vos propres données ou données à partir d’une source non intégrée [!DNL Audience Manager], vous devez créer et télécharger des fichiers de données et de métadonnées pour ces données. Pour plus d’informations, voir Fichiers de [données pour les rapports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) d’optimisation de l’audience et Fichiers de [données et de métadonnées pour les rapports](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)d’optimisation de l’audience.

## Contrôles d’accès basés sur les rôles (RBAC) {#rbac}

Le type de rapports que vous pouvez afficher dépend du [!UICONTROL RBAC] groupe auquel vous êtes affecté. Pour plus d’informations, voir [Administration](../../../features/administration/administration-overview.md) et [Création d’un groupe](../../../features/administration/administration-overview.md#create-group) .

[!UICONTROL RBAC] les groupes doivent avoir certaines sources de données configurées pour afficher les [!UICONTROL Audience Optimization] rapports. Votre [!DNL Audience Manager] consultant va configurer ces sources de données pour vous. Plus le nombre de sources de données de chaque [!UICONTROL RBAC] groupe d’utilisateurs est élevé, plus les membres du groupe auront accès aux données. Au minimum, votre consultant va configurer au moins une des sources de données suivantes :

* Source de données du publicitaire
* Source de données de marque
* Source de données de plateforme

Les utilisateurs appartenant à plusieurs groupes [!UICONTROL RBAC] d’utilisateurs peuvent basculer entre les vues de chaque groupe. Les données affichées seront mises à jour pour respecter le groupe sélectionné. Si votre société ne l’utilise pas [!UICONTROL RBAC], tous les utilisateurs disposent de droits d’administrateur et d’un accès à toutes les sources de données (groupes de conversion).

## Groupes de conversion {#conversion-groups}

Dans les [!UICONTROL Audience Optimization] rapports, **[!UICONTROL Conversion Groups]** sont synonymes de sources de données qui contiennent au moins une caractéristique de conversion. Les sources de données qui ne contiennent pas au moins une caractéristique de conversion n’apparaissent pas dans les [!UICONTROL Audience Optimization] rapports. Vous pouvez afficher les caractéristiques de conversion des groupes de conversion dans le rapport Caractéristiques [de conversion](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) rapportées.
