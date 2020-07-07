---
description: Le rapport Tendance des segments renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. Comparez les tendances et le volume des mesures sélectionnées pour obtenir une meilleure idée du comportement de vos audiences au fil du temps.
seo-description: Le rapport Tendance des segments renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. Comparez les tendances et le volume des mesures sélectionnées pour obtenir une meilleure idée du comportement de vos audiences au fil du temps.
seo-title: Rapport de tendances sur les segments
solution: Audience Manager
title: Rapport de tendances sur les segments
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 3%

---


# Rapport de tendances sur les segments{#segment-trend-report}

Le rapport Tendance des segments renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps.

Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage.

Comparez les tendances et le volume des mesures sélectionnées pour obtenir une meilleure idée du comportement de vos audiences au fil du temps.

## Cas d’utilisation {#use-cases}

Utilisez le [!UICONTROL Segment Trend] rapport pour valider les performances d’un segment au fil du temps et pour identifier les tendances en fonction de performances ou d’une échelle élevées.

Grâce à ce rapport, vous pouvez déterminer quelles propriétés Web présentent une augmentation de creux ou d’erreurs et résoudre les problèmes si nécessaire. Ce rapport constitue l’étape suivante après avoir identifié votre audience d’intérêt pour le [!UICONTROL Segment Performance] rapport, afin de vous assurer que les performances élevées ou médiocres que vous avez constatées dans l’ [!UICONTROL Segment Performance] onglet sont cohérentes au fil du temps.

## Utilisation du rapport de tendance des segments {#using-the-report}

Basculez entre **[!UICONTROL Mapped]** et **[!UICONTROL Unmapped]** pour sélectionner les segments qui sont mappés ou non à une destination. Sélectionnez **[!UICONTROL All]** pour inclure tous vos segments dans le rapport.

Réglez la fenêtre de recherche arrière à l’aide du **[!UICONTROL Date Through]** curseur.

Cliquez sur l’un des segments sous le **[!UICONTROL Date Through]** curseur pour afficher l’option permettant de conserver ou d’exclure uniquement ce segment dans le rapport.

Utilisez la **[!UICONTROL Line Item]** liste déroulante pour sélectionner les propriétés de votre portefeuille pour lesquelles vous souhaitez renvoyer des informations.

Dans la **[!UICONTROL Segment Data Source]** liste déroulante, sélectionnez les sources de données contenant les segments à afficher dans le rapport.

Utilisez la **[!UICONTROL Segment]** liste déroulante pour sélectionner les segments à afficher dans le rapport.

>[!IMPORTANT]
>
>Lors de l’activation [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Line Item] les identifiants, comme décrit à l’étape 3 de l’étape [Importer des fichiers de données Google Ad Manager (anciennement DFP) dans l’Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ce faisant, vous assurez que le rapport détaille la propriété web en tant que propriété [!UICONTROL Line Item] et non en tant qu’ [!UICONTROL Line Item] identifiant.

## Interprétation des résultats {#interpreting-results}

Le [!UICONTROL Segment Trend] rapport renvoie des données sur un graphique linéaire pour un intervalle de 14 jours seulement. Dans cet exemple, le rapport affiche les tendances d’impression et de clics publicitaires pour un ensemble de segments mappés et non mappés.

Passez la souris sur une ligne pour obtenir plus d’informations sur cette tendance de segment particulière. Voir la description des informations supplémentaires dans le tableau ci-dessous.

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
   <td colname="col2"> <p>Nom alphanumérique que vous avez attribué à ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> ID de segment</span> </p> </td> 
   <td colname="col2"> <p>ID unique de ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Article de ligne</span> </p> </td> 
   <td colname="col2"> <p>Propriété Web pour laquelle ce rapport s’affiche. </p> </td> 
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
   <td colname="col2"> <p>Le taux de clics publicitaires. Cette mesure représente le pourcentage d’impressions suivies de clics. Divisez les clics selon les impressions pour obtenir cette mesure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Uniques de segments</span> </p> </td> 
   <td colname="col2"> <p>Nombre de membres du segment, au cours des 30 derniers jours. </p> </td> 
  </tr> 
 </tbody> 
</table>
