---
description: Le rapport Tendance des segments renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé vers une destination pour le ciblage. Comparez les tendances et le volume pour les mesures sélectionnées afin d’obtenir une meilleure image du comportement de vos audiences au fil du temps.
seo-description: Le rapport Tendance des segments renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé vers une destination pour le ciblage. Comparez les tendances et le volume pour les mesures sélectionnées afin d’obtenir une meilleure image du comportement de vos audiences au fil du temps.
seo-title: Rapport Tendance des segments
solution: Audience Manager
title: Rapport Tendance des segments
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Rapport Tendance des segments{#segment-trend-report}

Le rapport Tendance des segments renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps.

Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé vers une destination pour le ciblage.

Comparez les tendances et le volume pour les mesures sélectionnées afin d’obtenir une meilleure image du comportement de vos audiences au fil du temps.

## Cas d’utilisation {#use-cases}

Utilisez le [!UICONTROL Segment Trend] rapport pour valider les performances d’un segment dans le temps et pour identifier les tendances en fonction de performances ou d’une échelle élevées.

Grâce à ce rapport, vous pouvez déterminer quelles propriétés Web présentent une diminution ou une augmentation défectueuse et résoudre les problèmes si nécessaire. Ce rapport constitue l’étape suivante après avoir identifié votre public intéressé par le [!UICONTROL Segment Performance] rapport, afin de vous assurer que les performances fortes ou mauvaises que vous avez vues dans l’ [!UICONTROL Segment Performance] onglet sont cohérentes au fil du temps.

## Utilisation du rapport de tendance des segments {#using-the-report}

Basculez entre **[!UICONTROL Mapped]** et **[!UICONTROL Unmapped]** pour sélectionner les segments mappés à une destination ou non. Sélectionnez **[!UICONTROL All]** pour inclure tous vos segments dans le rapport.

Réglez la fenêtre de recherche arrière à l’aide du **[!UICONTROL Date Through]** curseur.

Cliquez sur l’un des segments sous le **[!UICONTROL Date Through]** curseur pour afficher l’option permettant de conserver uniquement ce segment dans le rapport ou de l’exclure.

Utilisez la **[!UICONTROL Line Item]** liste déroulante pour sélectionner les propriétés de votre portefeuille pour lesquelles vous souhaitez renvoyer des informations.

Dans la **[!UICONTROL Segment Data Source]** liste déroulante, sélectionnez les sources de données contenant les segments à afficher dans le rapport.

Utilisez la **[!UICONTROL Segment]** liste déroulante pour sélectionner les segments à afficher dans le rapport.

>[!IMPORTANT]
>
>Lors de l’activation [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Line Item] les ID, comme décrit à l’étape 3 de l’ [importation des fichiers de données DFP dans Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ce faisant, vous assurez que le rapport indique la propriété web comme [!UICONTROL Line Item] propriété web et non comme [!UICONTROL Line Item] ID.

## Interprétation des résultats {#interpreting-results}

Le [!UICONTROL Segment Trend] rapport renvoie des données dans un graphique linéaire pour un intervalle de 14 jours uniquement. Dans cet exemple, le rapport affiche les tendances d’impression et de clics publicitaires pour un ensemble de segments mappés et non mappés.

Passez la souris sur une ligne pour obtenir plus d’informations sur cette tendance de segment spécifique. Voir la description des informations supplémentaires dans le tableau ci-dessous.

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
   <td colname="col1"> <p><span class="wintitle"> Élément de ligne</span> </p> </td> 
   <td colname="col2"> <p>Propriété Web pour laquelle vous voyez ce rapport. </p> </td> 
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
   <td colname="col2"> <p>Le taux de clics publicitaires. Cette mesure renvoie le pourcentage d’impressions suivi de clics. Divisez les clics par impressions pour obtenir cette mesure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Uniques de segments</span> </p> </td> 
   <td colname="col2"> <p>Nombre de membres du segment, au cours des 30 derniers jours. </p> </td> 
  </tr> 
 </tbody> 
</table>
