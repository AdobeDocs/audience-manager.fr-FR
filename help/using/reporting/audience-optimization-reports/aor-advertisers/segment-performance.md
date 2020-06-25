---
description: Le rapport Performances des segments compare les segments mappés et non mappés par impressions et taux de conversion. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous pouvez souhaiter envoyer à une destination pour le ciblage.
seo-description: Le rapport Performances des segments compare les segments mappés et non mappés par impressions et taux de conversion. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous pouvez souhaiter envoyer à une destination pour le ciblage.
seo-title: Rapport de performances des segments
solution: Audience Manager
title: Rapport de performances des segments
uuid: 5156a4c7-831d-4a95-a1be-eb516f0d91b7
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 0%

---


# Rapport de performances des segments{#segment-performance-report}

Le [!UICONTROL Segment Performance] rapport compare les segments mappés et non mappés par impressions et taux de conversion. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous pouvez souhaiter envoyer à une destination pour le ciblage.

## Comment lire les résultats de votre segment mappé {#read-mapped-segment-results}

Le [!UICONTROL Segment Performance] rapport mappé affiche tous les segments que vous avez créés et envoyés à une destination pour le ciblage.La position de vos segments mappés dans un rapport peut vous en dire beaucoup sur les segments qui fonctionnent bien et sur les endroits où vous devrez peut-être effectuer certains ajustements.

Pour lire le rapport, il permet de diviser les résultats en 4 sections avec des lignes imaginaires (en rouge) et les catégories affichées dans l&#39;exemple de rapport ci-dessous.

![](assets/mapped-segment-performance.png)

Les libellés de l’exemple et du tableau suivant peuvent vous aider à comprendre les performances des segments et comment répondre à ces résultats.

<table id="table_A29253B30DFA4CD7B3B7C320DE0BDEA4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Position </th> 
   <th colname="col2" class="entry"> Indications de placement </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Haut gauche</b> </p> </td> 
   <td colname="col2"> <p>Bons taux de conversion. </p> <p>Vous pouvez obtenir plus de conversions en augmentant les impressions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>En bas à gauche</b> </p> </td> 
   <td colname="col2"> <p>Basses taux de conversion. </p> <p>Vous pouvez éviter de cibler ces segments. Les segments de cette section présentent de bons candidats pour la comparaison avec ceux des résultats des segments non mappés. Certains de vos segments non mappés peuvent être plus performants que les segments que vous ciblez déjà. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>En haut à droite</b> </p> </td> 
   <td colname="col2"> <p>Performances fortes. Laissez ces segments tranquilles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>En bas à droite</b> </p> </td> 
   <td colname="col2"> <p>taux de conversion faibles et impressions élevées. </p> <p>Les segments de cette section ne sont pas performants. Vous pouvez décaler le budget de ces segments vers les segments dans le quadrant supérieur gauche du rapport. Cela permet de réduire les impressions et peut aider à améliorer les taux de conversion des segments dans cette section en bas à droite. En outre, comparez ces segments mappés à vos segments non mappés. Certains de vos segments non mappés peuvent être plus performants que les segments que vous ciblez déjà. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comment lire les résultats des segments non mappés {#read-unmapped-segment-results}

La recherche de segments non mappés dans un [!UICONTROL Segment Performance] rapport constitue un excellent moyen de trouver de nouveaux segments que vous n’avez pas pris en compte pour le ciblage. En fait, certains de ces segments peuvent être plus performants que vos segments mappés. En effet, un segment non mappé doit satisfaire à un ensemble de critères de qualification pour être inclus dans ce rapport. Pour être inclus dans ce rapport, un segment non mappé doit :

* Les conversions sont supérieures à la moyenne de tous les segments mappés.
* Être dans les 100 premiers segments non mappés par taux de conversion.

Pour lire ce rapport, il est utile de diviser les résultats en 4 sections avec des lignes imaginaires (en rouge) et des catégories illustrées dans l&#39;exemple de rapport ci-dessous.

![](assets/unmapped-segment-performance.png)

Dans ce rapport, vous souhaitez simplement vous concentrer sur les segments non mappés dans la section supérieure gauche. Ces segments non mappés présentent des taux de conversion élevés pour un faible niveau d’impression par rapport aux segments des trois autres sections.

>[!NOTE]
>
>Les périodes de 7 jours et 30 jours de recherche en arrière ne sont disponibles que pour les **[!UICONTROL Date Through]** dates du dimanche.
