---
description: Le rapport Tendance des segments renvoie des données sur les impressions et les taux de clics des segments mappés et non mappés au fil du temps. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé, mais que vous n’avez pas envoyé à une destination pour le ciblage. Comparez les tendances et le volume des mesures sélectionnées afin d’obtenir une meilleure vue d’ensemble du comportement de vos audiences au fil du temps.
seo-description: The Segment Trend report returns data on impressions and click-through rates of mapped and unmapped segments over time. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Compare trends and volume for your selected metrics to get a better picture of how your audiences behave over time.
seo-title: Segment Trend Report
solution: Audience Manager
title: Rapport Tendance des segments
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 0%

---

# Rapport Tendance des segments{#segment-trend-report}

Le rapport Tendance des segments renvoie des données sur les impressions et les taux de clics des segments mappés et non mappés au fil du temps.

Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé, mais que vous n’avez pas envoyé à une destination pour le ciblage.

Comparez les tendances et le volume des mesures sélectionnées afin d’obtenir une meilleure vue d’ensemble du comportement de vos audiences au fil du temps.

## Cas d’utilisation {#use-cases}

Utilisez le rapport [!UICONTROL Segment Trend] pour valider les performances d’un segment au fil du temps et identifier les tendances en fonction de performances ou d’une échelle élevées.

Avec ce rapport, vous pouvez comprendre quelles propriétés web affichent une augmentation négative ou défectueuse et procéder à un dépannage si nécessaire. Ce rapport est l’étape suivante après l’identification de l’audience qui vous intéresse dans le rapport [!UICONTROL Segment Performance]. Elle vise à vous assurer que les performances médiocres ou élevées constatées dans l’onglet [!UICONTROL Segment Performance] sont cohérentes au fil du temps.

## Utilisation du rapport Tendance des segments {#using-the-report}

Basculez entre **[!UICONTROL Mapped]** et **[!UICONTROL Unmapped]** pour sélectionner les segments mappés ou non à une destination. Sélectionnez **[!UICONTROL All]** pour inclure tous les segments dans le rapport.

Ajustez la fenêtre rétroactive avec le curseur **[!UICONTROL Date Through]**.

Cliquez sur l’un des segments sous le curseur de **[!UICONTROL Date Through]** pour afficher l’option permettant de ne conserver que ce segment dans le rapport ou de l’exclure.

Utilisez la liste déroulante **[!UICONTROL Line Item]** pour sélectionner les propriétés de votre portfolio pour lesquelles vous souhaitez renvoyer des informations.

Dans la liste déroulante **[!UICONTROL Segment Data Source]** , sélectionnez les sources de données contenant les segments que vous souhaitez afficher dans le rapport.

Utilisez la liste déroulante **[!UICONTROL Segment]** pour sélectionner les segments à afficher dans le rapport.

>[!IMPORTANT]
>
>Lors de l’activation d’[!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour les identifiants [!UICONTROL Line Item], comme décrit à l’étape 3 de la section [Importer des fichiers de données Google Ad Manager (anciennement DFP) dans Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ce faisant, vous vous assurez que le rapport détaille la propriété web sous la forme [!UICONTROL Line Item] au lieu de l’ID de [!UICONTROL Line Item].

## Interprétation des résultats {#interpreting-results}

Le rapport [!UICONTROL Segment Trend] renvoie des données dans un graphique linéaire pour un intervalle de 14 jours uniquement. Dans cet exemple, le rapport affiche les tendances d’impression et de clic publicitaire pour un ensemble de segments mappés et non mappés.

Passez la souris sur une ligne pour obtenir plus d’informations sur cette tendance de segment spécifique. Voir les descriptions pour les informations supplémentaires dans le tableau sous l’exemple de rapport.

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
   <td colname="col1"> <p><span class="wintitle"> Segment </span> </p> </td> 
   <td colname="col2"> <p>Nom alphanumérique attribué à ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> l’identifiant de segment </span> </p> </td> 
   <td colname="col2"> <p>Identifiant unique de ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Élément de ligne </span> </p> </td> 
   <td colname="col2"> <p>Propriété web pour laquelle ce rapport s’affiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Clics</span> </p> </td> 
   <td colname="col2"> <p>Nombre de fois où les membres de cette caractéristique ont cliqué sur des éléments de votre propriété web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>Nombre de fois où les membres de cette caractéristique ont été exposés à votre inventaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Taux de clic publicitaire. Cette mesure indique le pourcentage d’impressions suivies de clics. Divisez les clics par les impressions pour obtenir cette mesure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> des segments uniques</span> </p> </td> 
   <td colname="col2"> <p>Nombre de membres du segment au cours des 30 derniers jours. </p> </td> 
  </tr> 
 </tbody> 
</table>
