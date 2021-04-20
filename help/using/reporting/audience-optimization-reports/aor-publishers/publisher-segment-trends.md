---
description: Le rapport Tendance des segments renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. Comparez les tendances et le volume des mesures sélectionnées pour obtenir une meilleure idée du comportement de vos audiences au fil du temps.
seo-description: Le rapport Tendance des segments renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. Comparez les tendances et le volume des mesures sélectionnées pour obtenir une meilleure idée du comportement de vos audiences au fil du temps.
seo-title: Rapport de tendances sur les segments
solution: Audience Manager
title: Rapport de tendances sur les segments
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization Reports
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 3%

---

# Rapport de tendances sur les segments{#segment-trend-report}

Le rapport Tendance des segments renvoie des données sur les impressions et les taux de clics publicitaires des segments mappés et non mappés au fil du temps.

Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage.

Comparez les tendances et le volume des mesures sélectionnées pour obtenir une meilleure idée du comportement de vos audiences au fil du temps.

## Cas d’utilisation {#use-cases}

Utilisez le rapport [!UICONTROL Segment Trend] pour valider les performances d’un segment dans le temps et pour identifier les tendances en fonction de performances ou d’une échelle élevées.

Grâce à ce rapport, vous pouvez déterminer quelles propriétés Web présentent une augmentation de creux ou d’erreurs et résoudre les problèmes si nécessaire. Ce rapport constitue l’étape suivante après avoir identifié votre audience d’intérêt pour le rapport [!UICONTROL Segment Performance], afin de vous assurer que les performances élevées ou médiocres que vous avez constatées dans l’onglet [!UICONTROL Segment Performance] sont cohérentes au fil du temps.

## Utilisation du rapport de tendance des segments {#using-the-report}

Basculez entre **[!UICONTROL Mapped]** et **[!UICONTROL Unmapped]** pour sélectionner les segments mappés ou non à une destination. Sélectionnez **[!UICONTROL All]** pour inclure tous vos segments dans le rapport.

Réglez la fenêtre de recherche arrière à l&#39;aide du curseur **[!UICONTROL Date Through]**.

Cliquez sur l’un des segments sous le curseur **[!UICONTROL Date Through]** pour afficher l’option permettant de conserver uniquement ce segment dans le rapport ou de l’exclure.

Utilisez la liste déroulante **[!UICONTROL Line Item]** pour sélectionner les propriétés de votre portefeuille pour lesquelles vous souhaitez renvoyer des informations.

Dans la liste déroulante **[!UICONTROL Segment Data Source]**, sélectionnez les sources de données contenant les segments à afficher dans le rapport.

Utilisez la liste déroulante **[!UICONTROL Segment]** pour sélectionner les segments à afficher dans le rapport.

>[!IMPORTANT]
>
>Lors de l’activation de [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour les [!UICONTROL Line Item] identifiants, comme décrit à l’étape 3 de [Importer des fichiers de données Google Ad Manager (anciennement DFP) en Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Vous assurez ainsi que le rapport indique la propriété web sous la forme [!UICONTROL Line Item] au lieu de l&#39;identifiant [!UICONTROL Line Item].

## Interprétation des résultats {#interpreting-results}

Le rapport [!UICONTROL Segment Trend] renvoie des données sur un graphique linéaire pour un intervalle de 14 jours seulement. Dans cet exemple, le rapport affiche les tendances d’impression et de clics publicitaires pour un ensemble de segments mappés et non mappés.

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
