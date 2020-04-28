---
description: Un rapport de tendance renvoie des données de tendance sur les caractéristiques et les segments.
seo-description: Un rapport de tendance renvoie des données de tendance sur les caractéristiques et les segments.
seo-title: Rapports de tendances
solution: Audience Manager
title: Rapports de tendances
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 760818663ff3eb32c6de876c756697e1d9034369

---


# Rapports de tendances{#trend-reports}

Un rapport de tendance renvoie des données de tendance sur les caractéristiques et les segments.

## Aperçu {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utilise [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les autorisations des groupes d’utilisateurs aux [!UICONTROL Trend] rapports. Les utilisateurs ne peuvent voir que les caractéristiques et les segments dans le  qu’ils ont les autorisations d’ de. [!UICONTROL RBAC] permet de contrôler les  de données que les équipes internes sont en mesure de .

Par exemple, une agence qui gère différents comptes d’annonceurs peut configurer des autorisations de groupe d’utilisateurs afin qu’une équipe qui gère le compte de l’annonceur A ne puisse pas voir les données  de l’annonceur B.

Exécutez un [!UICONTROL Trend] rapport lorsque vous devez :

* Examinez les données de tendance par caractéristiques et par segments.
* Effectuez le suivi des tendances par intervalles de 1, 7, 14, 30, 60 et 90 jours.
* Comparez les tendances des caractéristiques et des segments au fil du temps.
* Identifiez les caractéristiques et les segments de performance forts ou médiocres.
* Exportez les données (format .csv) pour  plus de  et de partage.

L’illustration suivante présente un aperçu général des éléments clés du [!UICONTROL Trend] rapport.

![](assets/trend_reports.png)

1. Configurez les options suivantes :
   **Type de rapport :** Sélectionnez le type de rapport souhaité (Caractéristique ou Segment).
   **Période :** Spécifiez la plage de dates du rapport (date  du et date de fin).
   **Intervalle d’affichage :** Spécifiez l’intervalle d’affichage (intervalles de 1, 7, 14, 30, 60 et 90 jours).
1. Recherchez une caractéristique ou un segment par nom ou par ID.
1. A partir du  du dossier, faites glisser et déposez les caractéristiques ou les segments à rapporter dans le [!UICONTROL Selections] panneau de droite.
1. Générez le rapport pour l’afficher sous forme graphique ou exportez-le au format CSV.

## Run a Trend Report {#run-trend-report}

Cette procédure décrit l’exécution d’un [!UICONTROL Trend] rapport.

<!-- 

t_working_with_trend_reports.xml

 -->

1. Dans le **[!UICONTROL Analytics]** , cliquez sur **[!UICONTROL Trend Reports]**.
1. Dans le  **[!UICONTROL Report Type]** déroulant, sélectionnez le type de votre choix : **[!UICONTROL Trait]** ou **[!UICONTROL Segment]**.
1. Cliquez sur les zones de dates pour afficher un calendrier, puis sélectionnez les dates de début et de fin du rapport.
1. Spécifiez l’intervalle d’affichage : par 1, 7, 14, 30, 60 ou 90 jours.
1. Recherchez une caractéristique ou un segment par nom ou par ID.
1. A partir du  du dossier, faites glisser et déposez les caractéristiques ou les segments à rapporter dans le [!UICONTROL Selections] panneau de droite.
   * Pour de meilleures performances, exécutez un [!UICONTROL Trend] rapport sur moins de 20 caractéristiques ou segments à la fois.
1. Cliquez sur **[!UICONTROL Graph Traits]** ou **[!UICONTROL Graph Segments]**, selon le type de rapport affiché (Caractéristiques ou Segments). Ces options ignorent tous les dossiers et graphiques uniquement les caractéristiques ou segments sélectionnés individuellement.

   OU

   Cliquez sur **[!UICONTROL Export to CSV]** pour exporter les données de caractéristiques ou de segments et tous les dossiers au format CSV afin d’ plus loin la  et le partage. Cette option exporte les données [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]et [!UICONTROL Total Trait Population] pour toutes les plages de jours.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sont calculées pour [!UICONTROL Rule-based Traits] uniquement.

1. (Facultatif) Placez le pointeur de la souris sur des caractéristiques ou des segments individuels pour afficher le nombre de visites et la date de chaque point de données. Vous pouvez cliquer sur les en-têtes de colonne dans le tableau pour trier les résultats par ordre croissant ou décroissant.

## Résultats des rapports de tendances pour les caractéristiques {#trend-report-results-traits}

Les  ci-dessous sont disponibles lorsque vous exécutez un rapport [!UICONTROL Trend Report] et sélectionnez **[!UICONTROL Trait]** comme type de rapport.

Lors du filtrage des résultats par [!UICONTROL Device ID]:

* [!UICONTROL Unique Trait Realizations] est le nombre de vos de périphériques anonymes qui ont ajouté la caractéristique à leur  de au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] est le nombre total de réalisations de caractéristiques de la souris anonyme au cours de la période sélectionnée.
* [!UICONTROL Total Trait Population] est le nombre de vos de périphériques anonymes qui ont cette caractéristique sur leur  de.

Lors du filtrage des résultats par [!UICONTROL Cross-Device ID]:

* [!UICONTROL Unique Trait Realizations] est le nombre de vos authentifiés qui ont ajouté la caractéristique à leur  de, au cours de la période sélectionnée.
* [!UICONTROL Total Trait Realization] est le nombre total de réalisations de caractéristiques authentifiées au cours de la période sélectionnée.
* [!UICONTROL Total Trait Population] est le nombre de vos authentifiés qui ont cette caractéristique sur leur  de.

![tendance-rapport-caractéristiques](assets/trend-report-traits.png)

Les zéros indiquent que les données [!DNL Audience Manager] n’ont pas été collectées pour cette journée. Les entrées vierges indiquent que le trait n&#39;existait pas.

## Résultats des rapports de tendances pour les segments {#segment-report-results-traits}

Les  ci-dessous sont disponibles lorsque vous exécutez un rapport [!UICONTROL Trend Report] et sélectionnez **[!UICONTROL Segments]** comme type de rapport.

* **[!UICONTROL Real-time Segment Population]**: nombre de qualifiés pour le segment au cours de la période sélectionnée.
* **[!UICONTROL Total Segment Population]**: nombre total de qualifiés pour le segment.

![segments-rapports-tendances](assets/trend-report-segments.png)