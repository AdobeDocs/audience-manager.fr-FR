---
description: Le rapport Performances des segments compare les segments mappés et non mappés selon les impressions et les uniques de segments en temps réel. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous pouvez souhaiter envoyer à une destination pour le ciblage.
seo-description: Le rapport Performances des segments compare les segments mappés et non mappés selon les impressions et les uniques de segments en temps réel. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous pouvez souhaiter envoyer à une destination pour le ciblage.
seo-title: Rapport de performances sur les segments
solution: Audience Manager
title: Rapport de performances des segments pour les éditeurs
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Rapports d'optimisation des audiences
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
translation-type: tm+mt
source-git-commit: f5efd2d5032cb6d9fcceaee72d849a9dedcce698
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 2%

---

# Rapport de performances sur les segments{#segment-performance-report}

Le rapport Performances des segments compare les segments mappés et non mappés selon les impressions et les uniques de segments en temps réel.

Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage.

La comparaison de ces différents types de segments dans et entre les rapports permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous pouvez souhaiter envoyer à une destination pour le ciblage.

## Cas d’utilisation {#use-cases}

Avec le rapport [!UICONTROL Segment Performance], vous pouvez :

* Identifiez les segments d’audiences mappés qui génèrent de l’échelle ou des performances.
* Identifiez les segments non mappés à introduire dans les campagnes futures, en fonction de la contribution d’une audience aux performances passées.

## Utilisation du rapport de performances des segments {#using-segment-performance-report}

Basculez entre **[!UICONTROL Mapped]** et **[!UICONTROL Unmapped]** pour sélectionner les segments mappés ou non à une destination. Sélectionnez **[!UICONTROL All]** pour inclure tous vos segments dans le rapport.

Utilisez les commandes **Plage de jour** et **Date jusqu&#39;à** pour ajuster la plage de recherche en amont. Notez que les périodes de 7 et 30 jours de recherche en arrière ne sont disponibles que pour les dates du dimanche.

Utilisez la liste déroulante **[!UICONTROL Line Item]** pour sélectionner les propriétés Web pour lesquelles vous souhaitez renvoyer des informations.

Dans la liste déroulante **[!UICONTROL Segment Data Source]**, sélectionnez les sources de données contenant les segments à afficher dans le rapport.

Utilisez la liste déroulante **[!UICONTROL Segment]** pour sélectionner les segments à afficher dans le rapport.

>[!IMPORTANT]
>
>Lorsque vous activez [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Line Item IDs], comme décrit à l&#39;étape 3 de [Importer des fichiers de données Google Ad Manager (anciennement DFP) dans l&#39;Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Vous assurez ainsi que le rapport indique la propriété web sous la forme [!UICONTROL Line Item] au lieu de [!UICONTROL Line Item ID].

## Interprétation des résultats {#interpreting-results}

Votre rapport [!UICONTROL Segment Performance] peut ressembler à celui ci-dessous. Dans votre rapport, cliquez sur une bulle pour vue des données sous-jacentes. Voir la description des informations supplémentaires dans le tableau ci-dessous.

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
   <td colname="col1"> <p>Article de ligne </p> </td> 
   <td colname="col2"> <p>Propriété Web pour laquelle ce rapport s’affiche. </p> </td> 
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
   <td colname="col2"> <p>Le taux de clics publicitaires. </p> <p>Cette mesure représente le pourcentage d’impressions suivies de clics. Diviser les clics par impressions pour obtenir cette mesure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Population des segments en temps réel </p> </td> 
   <td colname="col2"> <p>Nombre réel de visiteurs uniques vus en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils étaient vus par <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comment lire les résultats de votre segment mappé {#read-mapped-segment}

La position de vos segments mappés dans un rapport peut vous en dire beaucoup sur les segments qui fonctionnent bien et sur les emplacements où vous devrez peut-être effectuer certains ajustements.

Pour lire le rapport, il est utile de diviser les résultats en quatre sections avec des lignes imaginaires (en rouge) et les catégories affichées dans l&#39;exemple de rapport ci-dessous. Les libellés de l’exemple peuvent vous aider à comprendre les performances des segments et comment répondre à ces résultats.

![](assets/publisher_segment_performance_mapped.png)

## Comment lire les résultats de votre segment non mappé {#read-unmapped-segment}

L’examen de segments non mappés dans un rapport [!UICONTROL Segment Performance] constitue un excellent moyen de trouver de nouveaux segments que vous n’avez pas pris en compte pour le ciblage. En fait, certains de ces segments peuvent être plus performants que vos segments mappés.

Pour lire ce rapport, il est utile de diviser les résultats en quatre sections avec des lignes imaginaires (en rouge) et des catégories illustrées dans l&#39;exemple de rapport ci-dessous.

![](assets/publisher_segment_performance_unmapped.png)
