---
description: Le rapport Performances des segments compare les segments mappés et non mappés par impressions et taux de conversion. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé, mais que vous n’avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports vous permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous souhaitez peut-être envoyer à une destination pour le ciblage.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and conversion rates. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Rapport sur les performances des segments
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Audience Optimization Reports
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---

# Rapport sur les performances des segments{#segment-performance-report}

Le rapport [!UICONTROL Segment Performance] compare les segments mappés et non mappés par impressions et taux de conversion. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé, mais que vous n’avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports vous permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous souhaitez peut-être envoyer à une destination pour le ciblage.

## Comment lire les résultats des segments mappés {#read-mapped-segment-results}

Le rapport [!UICONTROL Segment Performance] mappés affiche tous les segments que vous avez créés et envoyés vers une destination pour le ciblage. La position de vos segments mappés dans un rapport peut vous en dire beaucoup sur les segments qui se portent bien et sur ceux pour lesquels vous devrez peut-être effectuer des ajustements.

Pour lire le rapport, il est utile de diviser les résultats en 4 sections avec des lignes imaginaires (en rouge) et les catégories affichées dans l’exemple de rapport ci-dessous.

![](assets/mapped-segment-performance.png)

Les libellés de l’exemple et du tableau suivant peuvent vous aider à comprendre les performances des segments et comment répondre à ces résultats.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Indicateurs d’emplacement </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>En haut à gauche</b> </p> </td> 
   <td colname="col2"> <p>De bons taux de conversion. </p> <p>Vous pouvez obtenir plus de conversions en augmentant les impressions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>En Bas À Gauche</b> </p> </td> 
   <td colname="col2"> <p>Taux de conversion faibles. </p> <p>Vous pouvez éviter de cibler ces segments. Les segments de cette section sont de bons candidats pour la comparaison avec ceux des résultats de segments non mappés. Certains de vos segments non mappés peuvent être plus performants que les segments que vous ciblez déjà. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>En haut à droite</b> </p> </td> 
   <td colname="col2"> <p>De bonnes performances. Ne touchez pas à ces segments. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>En bas à droite</b> </p> </td> 
   <td colname="col2"> <p>Taux de conversion faibles et impressions élevées. </p> <p>Les segments de cette section n’ont pas de bonnes performances. Vous pouvez réaffecter le budget de ces segments vers les segments du quadrant supérieur gauche du rapport. Cela permet de réduire le nombre d’impressions et d’améliorer les taux de conversion des segments dans cette section inférieure droite. Comparez également ces segments mappés à vos segments non mappés. Certains de vos segments non mappés peuvent être plus performants que les segments que vous ciblez déjà. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comment lire les résultats des segments non mappés {#read-unmapped-segment-results}

L’examen des segments non mappés dans un rapport [!UICONTROL Segment Performance] est un excellent moyen de trouver de nouveaux segments que vous n’avez pas pris en compte pour le ciblage. En fait, certains de ces segments peuvent surpasser vos segments mappés. En effet, un segment non mappé doit répondre à un ensemble de critères de qualification pour être inclus dans ce rapport. Pour être inclus dans ce rapport, un segment non mappé doit :

* Ont des conversions supérieures à la moyenne de tous vos segments mappés.
* Faire partie des 100 premiers segments non mappés par taux de conversion.

Pour lire ce rapport, il est utile de diviser les résultats en 4 sections avec des lignes imaginaires (en rouge) et des catégories affichées dans l’exemple de rapport ci-dessous.

![](assets/unmapped-segment-performance.png)

Dans ce rapport, vous souhaitez simplement vous concentrer sur ces segments non mappés dans la section supérieure gauche. Ces segments non mappés présentent des taux de conversion élevés pour un faible niveau d’impressions par rapport aux segments des trois autres sections.

>[!NOTE]
>
>Les périodes de recherche en amont de 7 jours et 30 jours ne sont disponibles que pour les dates du dimanche **[!UICONTROL Date Through]**.
