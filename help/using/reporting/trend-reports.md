---
description: Un rapport Tendance renvoie des données de tendance sur les caractéristiques et les segments.
seo-description: A Trend report returns trend data on traits and segments.
seo-title: Trend Reports
solution: Audience Manager
title: Rapports de tendances
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
feature: General & Trend Reports
exl-id: 3373f413-cc8f-49c7-9b4e-34b39e0efc38
source-git-commit: 42f9b32edcde423369f7e8254b04fdc6162130d0
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# Rapports de tendances{#trend-reports}

Un rapport Tendance renvoie des données de tendance sur les caractéristiques et les segments.

## Présentation {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utilise [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les autorisations des groupes d’utilisateurs aux rapports [!UICONTROL Trend]. Les utilisateurs ne peuvent afficher que les caractéristiques et les segments dans les rapports qu’ils sont autorisés à consulter. [!UICONTROL RBAC] fonctionnalité vous permet de contrôler les données de rapport que les équipes internes peuvent afficher.

Par exemple, une agence qui gère différents comptes d’annonceurs peut configurer des autorisations de groupe d’utilisateurs afin qu’une équipe qui gère le compte de l’annonceur A ne puisse pas voir les données de rapports de l’annonceur B.

Exécutez un rapport [!UICONTROL Trend] lorsque vous devez :

* Examinez les données de tendance par caractéristiques et segments.
* Suivez les tendances par intervalles de 1, 7, 14, 30, 60 et 90 jours.
* Comparez les tendances des caractéristiques et des segments au fil du temps.
* Identifiez les segments et les caractéristiques de performances forts ou faibles.
* Exportez les données (format .csv) pour les analyser et les partager plus en détail.

L’illustration suivante présente de manière générale les éléments clés du rapport [!UICONTROL Trend].

![](assets/trend_reports.png)

1. Configurez les options suivantes :
   **Type de rapport :** sélectionnez le type de rapport souhaité (caractéristique ou segment).
   **Période :** spécifiez la période du rapport (date de début et date de fin).
   **Intervalle d’affichage :** spécifiez l’intervalle d’affichage (intervalles de 1, 7, 14, 30, 60 et 90 jours).
1. Recherchez une caractéristique ou un segment par nom ou ID.
1. Dans la liste des dossiers, faites glisser et déposez les caractéristiques ou les segments dont vous souhaitez créer un rapport dans le panneau [!UICONTROL Selections] sur le côté droit.
1. Générez le rapport à afficher sous forme graphique ou exportez-le au format CSV.

## Exécution d’un rapport de tendances {#run-trend-report}

Cette procédure décrit comment exécuter un rapport [!UICONTROL Trend].

<!-- 

t_working_with_trend_reports.xml

 -->

1. Dans le tableau de bord de la **[!UICONTROL Analytics]**, cliquez sur **[!UICONTROL Trend Reports]**.
1. Dans la liste déroulante **[!UICONTROL Report Type]** , sélectionnez le type souhaité : **[!UICONTROL Trait]** ou **[!UICONTROL Segment]**.
1. Cliquez sur les cases de date pour afficher un calendrier, puis sélectionnez les dates de début et de fin de votre rapport.
1. Spécifiez l’intervalle d’affichage : par 1, 7, 14, 30, 60 ou 90 jours.
1. Recherchez une caractéristique ou un segment par nom ou ID.
1. Dans la liste des dossiers, faites glisser et déposez les caractéristiques ou les segments dont vous souhaitez créer un rapport dans le panneau [!UICONTROL Selections] sur le côté droit.
   * Pour de meilleures performances, exécutez un rapport [!UICONTROL Trend] sur moins de 20 caractéristiques ou segments à la fois.
1. Cliquez sur **[!UICONTROL Graph Traits]** ou **[!UICONTROL Graph Segments]**, selon le type de rapport que vous consultez (Caractéristiques ou Segments). Ces options ignorent tous les dossiers et graphiques et ne sélectionnent que les caractéristiques ou segments sélectionnés individuellement.

   Ou

   Cliquez sur **[!UICONTROL Export to CSV]** pour exporter les données de caractéristique ou de segment et tous les dossiers au format CSV pour une analyse et un partage plus approfondis. Cette opération exporte les [!UICONTROL Unique Trait Realizations], les [!UICONTROL Total Trait Realizations] et les [!UICONTROL Total Trait Population] pour toutes les périodes.

   >[!NOTE]
   >
   >Les [!UICONTROL Total Trait Realizations] sont calculés pour les [!UICONTROL Rule-based Traits] uniquement.

1. (Facultatif) Placez le pointeur de la souris sur des caractéristiques ou des segments individuels pour afficher le nombre de visites et la date de chaque point de données. Vous pouvez cliquer sur les en-têtes des colonnes du tableau pour trier les résultats par ordre croissant ou décroissant.

## Résultats du rapport de tendances pour les caractéristiques {#trend-report-results-traits}

Les filtres ci-dessous sont disponibles lorsque vous exécutez un [!UICONTROL Trend Report] et sélectionnez **[!UICONTROL Trait]** comme type de rapport.

Lors du filtrage des résultats par [!UICONTROL Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de visiteurs anonymes de votre appareil qui ont ajouté la caractéristique à leur profil au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] est le nombre total de réalisations de caractéristiques anonymes dans la période sélectionnée.
* [!UICONTROL Total Trait Population] est le nombre de visiteurs anonymes de votre appareil qui ont cette caractéristique sur leur profil.

Lors du filtrage des résultats par [!UICONTROL Cross-Device ID] :

* [!UICONTROL Unique Trait Realizations] est le nombre de vos visiteurs authentifiés qui ont ajouté la caractéristique à leur profil, au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] est le nombre total de réalisations de caractéristiques authentifiées au cours de la période sélectionnée.
* [!UICONTROL Total Trait Population] est le nombre de vos visiteurs authentifiés qui ont cette caractéristique sur leur profil.

![trends-report-traits](assets/trend-report-traits.png)

Les zéros indiquent que [!DNL Audience Manager] n’a pas collecté de données pour ce jour-là. Les entrées vides indiquent que la caractéristique n’existait pas.

Regardez la vidéo ci-dessous pour un aperçu détaillé du fonctionnement des mesures inter-appareils.

[Compréhension des mesures inter-appareils dans Audience Manager](https://experienceleague.adobe.com/en/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager)

## Résultats du rapport de tendances pour les segments {#segment-report-results-traits}

Les filtres ci-dessous sont disponibles lorsque vous exécutez un [!UICONTROL Trend Report] et sélectionnez **[!UICONTROL Segments]** comme type de rapport.

* **[!UICONTROL Real-time Segment Population]** : nombre de visiteurs qualifiés pour le segment au cours de la période sélectionnée.
* **[!UICONTROL Total Segment Population]** : nombre total de visiteurs et visiteuses qualifiés pour le segment.

![tendancerapports-segments](assets/trend-report-segments.png)
