---
description: Le rapport Performances des segments compare les segments mappés et non mappés en fonction des impressions et des uniques de segments en temps réel. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé vers une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous souhaitez peut-être envoyer à une destination pour le ciblage.
seo-description: Le rapport Performances des segments compare les segments mappés et non mappés en fonction des impressions et des uniques de segments en temps réel. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé vers une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous souhaitez peut-être envoyer à une destination pour le ciblage.
seo-title: ' Rapport Performances des segments'
solution: Audience Manager
title: ' Rapport Performances des segments'
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


#  Rapport Performances des segments{#segment-performance-report}

Le rapport Performances des segments compare les segments mappés et non mappés en fonction des impressions et des uniques de segments en temps réel.

Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé vers une destination pour le ciblage.

La comparaison de ces différents types de segments dans et entre les rapports permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous souhaitez peut-être envoyer à une destination pour le ciblage.

## Cas d’utilisation {#use-cases}

Avec le [!UICONTROL Segment Performance] rapport, vous pouvez :

* Identifiez les segments d’audience mappés qui génèrent une échelle ou des performances.
* Identifiez les segments non mappés à introduire dans les campagnes futures, en fonction de la contribution d’une audience aux performances passées.

## Utilisation du rapport Performances des segments {#using-segment-performance-report}

Basculez entre **[!UICONTROL Mapped]** et **[!UICONTROL Unmapped]** pour sélectionner les segments mappés à une destination ou non. Sélectionnez **[!UICONTROL All]** pour inclure tous vos segments dans le rapport.

Utilisez les commandes **Plage** de jour et **Date jusqu’au bout** pour ajuster la plage de retour arrière. Notez que les périodes de 7 jours et de 30 jours sont disponibles uniquement pour les dates du dimanche.

Utilisez la **[!UICONTROL Line Item]** liste déroulante pour sélectionner les propriétés Web pour lesquelles vous souhaitez renvoyer des informations.

Dans la **[!UICONTROL Segment Data Source]** liste déroulante, sélectionnez les sources de données contenant les segments à afficher dans le rapport.

Utilisez la **[!UICONTROL Segment]** liste déroulante pour sélectionner les segments à afficher dans le rapport.

>[!IMPORTANT]
>
>Lors de l’activation [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Line Item IDs], comme décrit à l’étape 3 de l’ [importation de fichiers de données DFP dans Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Vous garantissez ainsi que le rapport indique la propriété web comme [!UICONTROL Line Item] au lieu de la propriété [!UICONTROL Line Item ID].

## Interprétation des résultats {#interpreting-results}

Votre [!UICONTROL Segment Performance] rapport pourrait ressembler à celui ci-dessous. Dans votre rapport, cliquez sur une bulle pour afficher les données sous-jacentes. Voir la description des informations supplémentaires dans le tableau ci-dessous.

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
   <td colname="col2"> <p>Nom alphanumérique que vous avez attribué à ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de segment </p> </td> 
   <td colname="col2"> <p>ID unique de ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Élément de ligne </p> </td> 
   <td colname="col2"> <p>Propriété Web pour laquelle vous voyez ce rapport. </p> </td> 
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
   <td colname="col2"> <p>Le taux de clics publicitaires. </p> <p>Cette mesure renvoie le pourcentage d’impressions suivi de clics. Divisez les clics par impressions pour obtenir cette mesure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Population des segments en temps réel </p> </td> 
   <td colname="col2"> <p>Nombre réel de visiteurs uniques affichés en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils étaient vus par <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comment lire les résultats du segment mappé {#read-mapped-segment}

La position de vos segments mappés dans un rapport peut vous en dire beaucoup sur les segments performants et sur les emplacements où vous devrez peut-être apporter des ajustements.

Pour lire le rapport, il est utile de diviser les résultats en quatre sections avec des lignes imaginaires (en rouge) et les catégories affichées dans l'exemple de rapport ci-dessous. Les libellés de l’exemple peuvent vous aider à comprendre les performances des segments et comment répondre à ces résultats.

![](assets/publisher_segment_performance_mapped.png)

## Comment lire les résultats du segment non mappé {#read-unmapped-segment}

L’examen de segments non mappés dans un [!UICONTROL Segment Performance] rapport constitue un excellent moyen de trouver de nouveaux segments que vous n’avez pas pris en compte pour le ciblage. En fait, certains de ces segments peuvent surpasser les segments mappés.

Pour lire ce rapport, il est utile de diviser les résultats en quatre sections avec des lignes imaginaires (en rouge) et des catégories illustrées dans l'exemple de rapport ci-dessous.

![](assets/publisher_segment_performance_unmapped.png)
