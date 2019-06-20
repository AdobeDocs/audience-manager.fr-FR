---
description: Un rapport Général renvoie des données de performances sur les caractéristiques, les segments et les destinations.
seo-description: Un rapport Général dans Audience Manager renvoie des données de performances sur les caractéristiques, les segments et les destinations.
seo-title: Rapports généraux dans Audience Manager
solution: Audience Manager
title: Rapports généraux
uuid: 0 cea 75 a 0-969 e -4 ee 3-971 a -60 b 911711 e 52
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# General Reports{#general-reports}

A [!UICONTROL General] report returns performance data on traits, segments, and destinations.

## Aperçu {#general-reports-overview}

<!-- 

c_general_reports.xml

 -->

[!DNL Audience Manager] utilise [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les autorisations de groupe d&#39;utilisateurs aux [!UICONTROL General] rapports. Les utilisateurs peuvent afficher uniquement les caractéristiques et les segments dans les rapports auxquels ils sont autorisés à accéder. [!UICONTROL RBAC] vous permet de contrôler quelles données de rapport les équipes internes peuvent afficher. Par exemple, une agence qui gère différents comptes publicitaires peut configurer les autorisations des groupes d&#39;utilisateurs de sorte qu&#39;une équipe qui gère le compte publicitaire A ne puisse pas voir les données de rapport de l&#39;annonceur B.

Run a [!UICONTROL General] report when you need to:

* Examinez les performances par caractéristique, segment ou destination.
* Observe les impressions (total et unique) aux intervalles 1, 7, 14, 30, 60, 90-jours et durée de vie.
* Examinez le nombre total et le nombre de chargements uniques.
* Comparaison des performances des segments et des caractéristiques.
* Identifiez les caractéristiques et les segments performants ou médiocres, analysez la demande ou comparez les données de charge/feu à des rapports tiers.
* Exporter des données (format. csv) pour une analyse et un partage plus poussés.

The following illustration provides a high-level overview of key elements in the [!UICONTROL General] report.

![](assets/general_reports.png)

1. Configurez les options suivantes :

   * **Type de rapport :** Sélectionnez le type de rapport souhaité (Caractéristique, Segment ou Destination).

   * **Pour les dates par :** Spécifiez la plage de dates du rapport.

2. Recherchez une caractéristique, un segment ou une destination par nom ou par identifiant.
3. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
4. Générez le rapport à afficher dans un tableau exportable.

## Run a General Report {#run-general-report}

This section describes how to run a [!UICONTROL General] report and set time and other performance options.

<!-- 

t_run_general_report.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL General Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: Trait, Segment, or Destination.
1. *Conditionnel* Cliquez sur la zone de date pour afficher un calendrier, puis sélectionnez la date de fin de votre rapport si vous souhaitez spécifier une date autre que aujourd&#39;hui.
1. Recherchez une caractéristique, un segment ou une destination par nom ou par identifiant.
1. From the folder list, drag and drop the traits, segments, or destinations you want to report to the [!UICONTROL Selections] panel on the right side.
1. Cliquez sur **[!UICONTROL Run Report]**.

   Les résultats s&#39;affichent dans un tableau exportable. Cliquez sur les en-têtes de colonne pour trier les résultats par ordre croissant ou décroissant.
1. Select the desired option button at the top of the report to filter data by performance ( [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], or [!UICONTROL Total Trait Population]) or by time (1, 7, 14, 30, 60, 90-day range or lifetime).

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sont calculés [!UICONTROL Rule-based Traits] uniquement.

1. *Clic facultatif***[!UICONTROL Export to CSV]**. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

## General Reports Results Explained {#general-reports-explained}

The numbers in the [!UICONTROL General Reports] are generated directly from our [!UICONTROL User Profile Store]. The results reflect the number of users that [!DNL Audience Manager] contained in the backend at the time these reporting numbers were generated.

* Ces nombres n&#39;incluent pas les ID de visiteur avec un trafic excessif. Le trafic provenant de robots est filtré avant d&#39;atteindre notre système principal. En outre, le trafic de robots est ignoré lors d&#39;une tâche de nettoyage hebdomadaire dans le serveur principal.
* If you onboard data via inbound processing keyed off the [!DNL Audience Manager] UUID, and these IDs include users that are no longer active in our system, these inactive [!DNL Audience Manager] UUIDs never reach the [!UICONTROL User Profile Store] and are not reported.
* [!UICONTROL Total Trait Realizations] sont calculés [!UICONTROL Rule-based Traits] uniquement.

## General Reports Results for Traits {#general-report-results-traits}

The metrics below are available when you run a General report and select **[!UICONTROL Trait]** as the report type:

**Realizations de caractéristiques uniques**

This metric represents the unique number of [Audience Manager Unique User IDs (UUID)](../reference/ids-in-aam.md) that qualified for the trait in your selected time range. Par exemple, si un utilisateur se rend trois fois sur votre page d&#39;accueil sur la 1 ère page, vous verrez une réalisation de caractéristique unique.

**Realizations de caractéristiques totales**

Cette mesure représente la quantité totale de caractéristiques déclenchées pour la caractéristique dans la période sélectionnée. Par exemple, si un utilisateur a visité votre page d&#39;accueil, puis a navigué vers vos actualités techniques et vos nouvelles sections de sports, elles apparaissent dans le rapport général sous la forme de trois realizations de caractéristiques totales et d&#39;une concrétisation unique.

**Population totale de caractéristiques**

Cette mesure représente la quantité totale des UUID Audience Manager actuellement qualifiés pour la caractéristique. Utilisez ce nombre pour comprendre le nombre total d&#39;utilisateurs que vous pouvez utiliser pour la segmentation et le ciblage. Typically, users remain part of a trait for [120 days](../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval). Par exemple, un utilisateur qui consulte votre page d&#39;accueil trois fois aujourd&#39;hui et qui ne revient jamais après, restera comme un utilisateur dans cette population tous les jours jusqu&#39;à 120 jours. Au bout de 120 jours, elles seront supprimées de la population. Read our [Trait Qualification Reference](../features/traits/trait-qualification-reference.md) for more examples on the difference between Unique Trait Realizations and Total Trait Population.

L&#39;illustration ci-dessous montre les résultats d&#39;exécution d&#39;un rapport général pour le type de rapport Caractéristique.

![](assets/general_reports_metrics.png)

## General Reports Results for Segments {#general-report-results-segments}

The metrics below are available when you run a General report and select **[!UICONTROL Segment]** as the report type:

**Population de segments en temps réel**

Cette mesure représente le nombre réel de visiteurs uniques vus en temps réel pour la période spécifiée et qui ont été qualifiés pour le segment au moment où ils ont été vus par Audience Manager.

**Population totale de segments**

Cette mesure représente le nombre total d&#39;UUID Audience Manager qui sont qualifiés pour le segment au cours de la période de recherche que vous avez sélectionnée. Votre population de segment total 1 jour représente la base d&#39;utilisateurs la plus précise pour le ciblage.

>[!NOTE]
>
>Select **[!UICONTROL Include Destination Mappings]** to see a breakdown of segment population for activated destinations.

L&#39;illustration ci-dessous montre les résultats d&#39;exécution d&#39;un rapport général pour le type de rapport Segment.

![](assets/general_reports_segment_metrics.png)

## General Reports Results for Destinations {#general-report-results-destinations}

The metrics below are available when you run a General report and select **[!UICONTROL Destination]** as the report type:

**Population de segments en temps réel**

Cette mesure représente le nombre réel de visiteurs uniques vus en temps réel pour la période spécifiée et qui ont été qualifiés pour le segment au moment où ils ont été vus par Audience Manager.

**Population totale de segments**

Cette mesure représente le nombre total d&#39;UUID Audience Manager appartenant à un segment dans la période de recherche, qui ont été envoyés à une destination.

L&#39;illustration ci-dessous montre les résultats d&#39;exécution d&#39;un rapport général pour le type de rapport Destinations.

![](assets/general_reports_destinations.png)
