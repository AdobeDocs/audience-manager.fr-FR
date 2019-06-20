---
description: Un rapport de tendance renvoie des données de tendance sur les caractéristiques et les segments.
seo-description: Un rapport de tendance renvoie des données de tendance sur les caractéristiques et les segments.
seo-title: Rapports de tendance
solution: Audience Manager
title: Rapports de tendance
uuid: bedbe 7 d 4-7 cbb -4403-9104-312 f 9230 aea 1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Trend Reports{#trend-reports}

Un rapport de tendance renvoie des données de tendance sur les caractéristiques et les segments.

## Aperçu {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] utilise [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) pour étendre les autorisations de groupe d&#39;utilisateurs aux [!UICONTROL Trend] rapports. Les utilisateurs peuvent afficher uniquement les caractéristiques et les segments dans les rapports auxquels ils sont autorisés à accéder. [!UICONTROL RBAC] vous permet de contrôler quelles données de rapport les équipes internes peuvent afficher.

Par exemple, une agence qui gère différents comptes publicitaires peut configurer les autorisations des groupes d&#39;utilisateurs de sorte qu&#39;une équipe qui gère le compte publicitaire A ne puisse pas voir les données de rapport de l&#39;annonceur B.

Run a [!UICONTROL Trend] report when you need to:

* Examinez les données de tendance des tendances par caractéristiques et segments.
* Suivi des tendances de 1, 7, 14, 30, 60 et 90 jours.
* Comparez les tendances des caractéristiques et des segments au temps.
* Identifiez les caractéristiques et les segments performants ou peu performants.
* Exporter des données (format. csv) pour une analyse et un partage plus poussés.

The following illustration provides a high-level overview of key elements in the [!UICONTROL Trend] report.

![](assets/trend_reports.png)

1. Configurez les options suivantes :

   **Type de rapport :** Sélectionnez le type de rapport souhaité (Caractéristique ou Segment).

   **Période :** Spécifiez la plage de dates du rapport (date de début et date de fin).

   **Intervalle d&#39;affichage :** Spécifiez l&#39;intervalle d&#39;affichage (1, 7, 14, 30, 60 et 90 jours).

2. Rechercher une caractéristique ou un segment par nom ou par identifiant.
3. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.
4. Générez le rapport pour l&#39;afficher dans les données sous forme graphique ou exportez le rapport au format CSV.

## Run a Trend Report {#run-trend-report}

This procedure describes how to run a [!UICONTROL Trend] report.

<!-- 

t_working_with_trend_reports.xml

 -->

1. In the **[!UICONTROL Analytics]** dashboard, click **[!UICONTROL Trend Reports]**.
1. From the **[!UICONTROL Report Type]** drop-down list, select the desired type: **[!UICONTROL Trait]** or **[!UICONTROL Segment]**.
1. Cliquez sur les zones de dates pour afficher un calendrier, puis sélectionnez les dates de début et de fin de votre rapport.
1. Spécifiez l&#39;intervalle d&#39;affichage : par 1, 7, 14, 30, 60 ou 90 jours.
1. Rechercher une caractéristique ou un segment par nom ou par identifiant.
1. From the folder list, drag and drop the traits or segments you want to report to the [!UICONTROL Selections] panel on the right side.

   For best performance, run a [!UICONTROL Trend] report on fewer than 20 traits or segments at a time.
1. Click **[!UICONTROL Graph Traits]** or **[!UICONTROL Graph Segments]**, depending on which type of report you are viewing (Traits or Segments).

   Ces options ignorent tous les dossiers et ne graphique que les caractéristiques ou segments sélectionnés individuellement.

   OU

   Click **[!UICONTROL Export to CSV]** to export the trait or segment data and all folders in CSV format for further analysis and sharing. This exports the [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations], and [!UICONTROL Total Trait Population] for all day ranges.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] sont calculés [!UICONTROL Rule-based Traits] uniquement.

1. (Facultatif) Placez le pointeur de la souris sur des caractéristiques ou des segments pour afficher le nombre de visites et la date de chaque point de données.

   Vous pouvez cliquer sur les en-têtes de colonne du tableau pour trier les résultats par ordre croissant ou décroissant.

For [!UICONTROL Trended Trait] reports, zeroes indicate that [!DNL Audience Manager] did not collect data for that day. Les entrées vides indiquent que la caractéristique n&#39;existe pas. L&#39;exemple suivant illustre des exemples d&#39;entrées :

![](assets/trended_data.png)
