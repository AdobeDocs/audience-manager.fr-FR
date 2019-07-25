---
description: Le rapport Tendance de segment renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n'avez pas envoyé à une destination pour le ciblage. Comparez les tendances et le volume des mesures sélectionnées pour obtenir une meilleure image du comportement des audiences au fil du temps.
seo-description: Le rapport Tendance de segment renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n'avez pas envoyé à une destination pour le ciblage. Comparez les tendances et le volume des mesures sélectionnées pour obtenir une meilleure image du comportement des audiences au fil du temps.
seo-title: Rapport de tendance des segments
solution: Audience Manager
title: Rapport de tendance des segments
uuid: f 84 e 8 d 0 a -74 e 5-430 c-b 61 c-efb 696 faee 93
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Trend Report{#segment-trend-report}

Le rapport Tendance de segment renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps.

Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n'avez pas envoyé à une destination pour le ciblage.

Comparez les tendances et le volume des mesures sélectionnées pour obtenir une meilleure image du comportement des audiences au fil du temps.

## Cas d’utilisation {#use-cases}

Use the [!UICONTROL Segment Trend] report to validate a segment's performance over time and to pinpoint trends based on strong performance or scale.

Grâce à ce rapport, vous pouvez comprendre les propriétés Web qui montrent un creux ou une erreur incorrecte et dépanner le cas échéant. This report is the next step after you identify your audience of interest in the [!UICONTROL Segment Performance] report, to ensure that the strong or poor performance you saw in the [!UICONTROL Segment Performance] tab is consistent over time.

## Using the Segment Trend Report {#using-the-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Adjust the look-back window with the **[!UICONTROL Date Through]** slider.

Click any of the segments under the **[!UICONTROL Date Through]** slider to bring up the option to keep only that segment in the report or exclude it.

Use the **[!UICONTROL Line Item]** drop-down box to select the properties in your portfolio for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item] IDs, as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item] ID.

## Interpreting the Results {#interpreting-results}

The [!UICONTROL Segment Trend] report returns data in a line graph for a 14-day interval only. Dans cet exemple, le rapport montre les tendances d'impression et de clic publicitaire pour un ensemble de segments mappés et non mappés.

Passez la souris sur une ligne pour obtenir plus d'informations sur cette tendance de segment particulière. Voir Descriptions pour obtenir des informations supplémentaires dans le tableau sous l'exemple de rapport.

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment</span> </p> </td> 
   <td colname="col2"> <p>Nom alphanumérique affecté à ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID de segment</span> </p> </td> 
   <td colname="col2"> <p>Identifiant unique de ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Elément</span> </p> </td> 
   <td colname="col2"> <p>Propriété web pour laquelle vous voyez ce rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Clics</span> </p> </td> 
   <td colname="col2"> <p>Nombre de fois où des membres de cette caractéristique ont cliqué sur des éléments de votre propriété Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>Nombre de fois où des membres de cette caractéristique ont été exposés à votre inventaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Le taux de clics publicitaires. Cette mesure indique le pourcentage d'impressions suivies par des clics. Divisez les clics par impressions pour obtenir cette mesure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segments uniques</span> </p> </td> 
   <td colname="col2"> <p>Nombre de membres du segment, au cours des 30 derniers jours. </p> </td> 
  </tr> 
 </tbody> 
</table>
