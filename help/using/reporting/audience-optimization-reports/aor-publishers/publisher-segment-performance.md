---
description: Le rapport Performance des segments compare les segments mappés et non mappés par impressions et Réel - Segments de segments uniques. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n'avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports permet d'optimiser les campagnes existantes et de rechercher des segments ignorés que vous souhaitez envoyer à une destination pour le ciblage.
seo-description: Le rapport Performance des segments compare les segments mappés et non mappés par impressions et Réel - Segments de segments uniques. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n'avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports permet d'optimiser les campagnes existantes et de rechercher des segments ignorés que vous souhaitez envoyer à une destination pour le ciblage.
seo-title: Rapport Performance des segments
solution: Audience Manager
title: Rapport Performance des segments
uuid: c 9 a 1 e 9 ad -4 f 3 f -4334-a 3 ff -0 f 241 c 7303 c 4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment Performance Report{#segment-performance-report}

Le rapport Performance des segments compare les segments mappés et non mappés par impressions et Réel - Segments de segments uniques.

Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n&#39;avez pas envoyé à une destination pour le ciblage.

La comparaison de ces différents types de segments dans et entre les rapports permet d&#39;optimiser les campagnes existantes et de rechercher des segments ignorés que vous souhaitez envoyer à une destination pour le ciblage.

## Cas d’utilisation {#use-cases}

With the [!UICONTROL Segment Performance] report, you can:

* Identifiez les segments d&#39;audience mappés qui génèrent des échelles ou des performances.
* Identifiez les segments non mappés à introduire dans les campagnes futures, en fonction de la contribution d&#39;un public aux performances passées.

## Using the Segment Performance Report {#using-segment-performance-report}

Toggle between **[!UICONTROL Mapped]** and **[!UICONTROL Unmapped]** to select segments that are mapped to a destination or not. Select **[!UICONTROL All]** to include all your segments in the report.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Notez que les périodes de recherche de 7 et 30 jours ne sont disponibles que pour les dates dimanche.

Use the **[!UICONTROL Line Item]** drop-down box to select the web properties for which you want to return information.

In the **[!UICONTROL Segment Data Source]** drop-down box, select the data sources containing the segments you want to see in the report.

Use the **[!UICONTROL Segment]** drop-down box to select which segments you want to see in the report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Line Item IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Line Item] instead of the [!UICONTROL Line Item ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Segment Performance] report could look similar to the one below. Dans le rapport, cliquez sur une bulle pour afficher les données sous-jacentes. Voir Descriptions pour obtenir des informations supplémentaires dans le tableau sous l&#39;exemple de rapport.

![](assets/publisher_segment_performance.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Segment </p> </td> 
   <td colname="col2"> <p>Nom alphanumérique affecté à ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de segment </p> </td> 
   <td colname="col2"> <p>Identifiant unique de ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elément </p> </td> 
   <td colname="col2"> <p>Propriété web pour laquelle vous voyez ce rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Clics </p> </td> 
   <td colname="col2"> <p>Nombre de fois où des membres de cette caractéristique ont cliqué sur des éléments de votre propriété Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impressions </p> </td> 
   <td colname="col2"> <p>Nombre de fois où des membres de cette caractéristique ont été exposés à votre inventaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Le taux de clics publicitaires. </p> <p>Cette mesure indique le pourcentage d'impressions suivies par des clics. Divisez les clics par impressions pour obtenir cette mesure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Population de segments en temps réel </p> </td> 
   <td colname="col2"> <p>The actual number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## How to Read Your Mapped Segment Results {#read-mapped-segment}

La position de vos segments mappés dans un rapport peut vous indiquer un grand nombre de segments performants et où vous devrez effectuer certains ajustements.

Pour lire le rapport, il est utile de diviser les résultats en quatre sections avec des lignes imaginaires (en rouge) et des catégories illustrées dans l&#39;exemple de rapport ci-dessous. Les étiquettes dans l&#39;exemple peuvent vous aider à comprendre les performances des segments et à réagir à ces résultats.

![](assets/publisher_segment_performance_mapped.png)

## How to Read Your Unmapped Segment Results {#read-unmapped-segment}

Looking at unmapped segments in a [!UICONTROL Segment Performance] report is a great way to find new segments you haven&#39;t considered for targeting. En fait, certains de ces segments peuvent dépasser les segments mappés.

Pour lire ce rapport, il est utile de diviser les résultats en quatre sections avec des lignes imaginaires (en rouge) et des catégories illustrées dans l&#39;exemple de rapport ci-dessous.

![](assets/publisher_segment_performance_unmapped.png)
