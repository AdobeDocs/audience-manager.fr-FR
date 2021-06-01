---
description: Le rapport Performances des segments compare les segments mappés et non mappés en fonction des impressions et des taux de conversion. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports vous permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous pouvez envoyer à une destination pour le ciblage.
seo-description: Le rapport Performances des segments compare les segments mappés et non mappés en fonction des impressions et des taux de conversion. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports vous permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous pouvez envoyer à une destination pour le ciblage.
seo-title: Rapport de performances sur les segments
solution: Audience Manager
title: Rapport de performances sur les segments
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: Rapports d’Audience Optimization
exl-id: 2cd54b18-6916-4d69-bd65-7b8c8846c446
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# Rapport de performances sur les segments{#segment-performance-report}

Le rapport [!UICONTROL Segment Performance] compare les segments mappés et non mappés en fonction des impressions et des taux de conversion. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports vous permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous pouvez envoyer à une destination pour le ciblage.

## Comment lire les résultats du segment mappé {#read-mapped-segment-results}

Le rapport [!UICONTROL Segment Performance] mappé affiche tous les segments que vous avez créés et envoyés vers une destination à des fins de ciblage. La position de vos segments mappés dans un rapport peut vous en apprendre beaucoup sur les segments qui fonctionnent bien et sur les endroits où vous devrez peut-être apporter des ajustements.

Pour lire le rapport, il est utile de diviser les résultats en 4 sections avec des lignes imaginaires (en rouge) et les catégories affichées dans l&#39;exemple de rapport ci-dessous.

![](assets/mapped-segment-performance.png)

Les libellés de l’exemple et du tableau suivant peuvent vous aider à comprendre les performances des segments et comment répondre à ces résultats.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Indicateur de référencement </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Haut à gauche</b> </p> </td> 
   <td colname="col2"> <p>De bons taux de conversion. </p> <p>Vous pouvez obtenir plus de conversions en augmentant les impressions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Bas à gauche</b> </p> </td> 
   <td colname="col2"> <p>Faibles taux de conversion. </p> <p>Vous pouvez éviter de cibler ces segments. Les segments de cette section sont des candidats idéaux pour la comparaison avec ceux des résultats de segments non mappés. Certains de vos segments non mappés peuvent être plus performants que les segments que vous ciblez déjà. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Haut à droite</b> </p> </td> 
   <td colname="col2"> <p>Une performance forte. Laissez ces segments tranquilles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Bas à droite</b> </p> </td> 
   <td colname="col2"> <p>Faibles taux de conversion et impressions élevées. </p> <p>Les segments de cette section ne sont pas performants. Vous pouvez décaler le budget de ces segments vers les segments dans le quadrant supérieur gauche du rapport. Cela permet de réduire les impressions et peut contribuer à améliorer les taux de conversion pour les segments dans cette section inférieure droite. Comparez également ces segments mappés à vos segments non mappés. Certains de vos segments non mappés peuvent être plus performants que les segments que vous ciblez déjà. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comment lire vos résultats de segment non mappés {#read-unmapped-segment-results}

L’examen des segments non mappés dans un rapport [!UICONTROL Segment Performance] est un excellent moyen de trouver de nouveaux segments que vous n’avez pas pris en compte pour le ciblage. En fait, certains de ces segments peuvent être plus performants que vos segments mappés. En effet, un segment non mappé doit satisfaire à un ensemble de critères de qualification pour être inclus dans ce rapport. Pour être inclus dans ce rapport, un segment non mappé doit :

* Les conversions sont supérieures à la moyenne de tous vos segments mappés.
* Être dans les 100 segments non mappés les plus élevés par taux de conversion.

Pour lire ce rapport, il est utile de diviser les résultats en 4 sections, avec des lignes imaginaires (en rouge) et des catégories affichées dans l&#39;exemple de rapport ci-dessous.

![](assets/unmapped-segment-performance.png)

Dans ce rapport, vous souhaitez simplement vous concentrer sur les segments non mappés dans la section supérieure gauche. Ces segments non mappés présentent des taux de conversion élevés pour un faible niveau d’impression par rapport aux segments des trois autres sections.

>[!NOTE]
>
>Les périodes d’analyse de 7 jours et de 30 jours ne sont disponibles que pour les dates du dimanche **[!UICONTROL Date Through]**.
