---
description: Le rapport Performances des segments compare les segments mappés et non mappés par impression et par unité de segments en temps réel. Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage. La comparaison de ces différents types de segments dans et entre les rapports vous permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous pouvez envoyer à une destination pour le ciblage.
seo-description: The Segment Performance report compares mapped and unmapped segments by impressions and Real-Time Segment Uniques. A mapped segment is a segment you create and send to a destination for targeting. An unmapped segment is a segment that you've created but have not sent to a destination for targeting. Comparing these different segment types within and between reports helps you optimize existing campaigns and find overlooked segments that you may want to send to a destination for targeting.
seo-title: Segment Performance Report
solution: Audience Manager
title: Rapport de performances des segments pour les éditeurs
uuid: c9a1e9ad-4f3f-4334-a3ff-0f241c7303c4
feature: Audience Optimization Reports
exl-id: 0cc10399-5737-4d82-a1f6-9561e024054d
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---

# Rapport de performances sur les segments{#segment-performance-report}

Le rapport Performances des segments compare les segments mappés et non mappés par impression et par unité de segments en temps réel.

Un segment mappé est un segment que vous créez et envoyez à une destination pour le ciblage. Un segment non mappé est un segment que vous avez créé mais que vous n’avez pas envoyé à une destination pour le ciblage.

La comparaison de ces différents types de segments dans et entre les rapports vous permet d’optimiser les campagnes existantes et de trouver les segments négligés que vous pouvez envoyer à une destination pour le ciblage.

## Cas d’utilisation {#use-cases}

Avec le rapport [!UICONTROL Segment Performance], vous pouvez :

* Identifiez les segments d’audience mappés qui génèrent une échelle ou des performances.
* Identifiez les segments non mappés à introduire dans les futures campagnes, en fonction de la contribution d’une audience aux performances antérieures.

## Utilisation du rapport de performances des segments {#using-segment-performance-report}

Basculez entre **[!UICONTROL Mapped]** et **[!UICONTROL Unmapped]** pour sélectionner les segments mappés ou non à une destination. Sélectionnez **[!UICONTROL All]** pour inclure tous vos segments dans le rapport.

Utilisez les commandes **Plage du jour** et **Date jusqu’à** pour ajuster la plage de recherche arrière. Notez que les périodes d’analyse de 7 et 30 jours ne sont disponibles que pour les dates du dimanche.

Utilisez la liste déroulante **[!UICONTROL Line Item]** pour sélectionner les propriétés web pour lesquelles vous souhaitez renvoyer des informations.

Dans la liste déroulante **[!UICONTROL Segment Data Source]**, sélectionnez les sources de données contenant les segments que vous souhaitez voir dans le rapport.

Utilisez la liste déroulante **[!UICONTROL Segment]** pour sélectionner les segments que vous souhaitez voir dans le rapport.

>[!IMPORTANT]
>
>Lors de l’activation de [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Line Item IDs], comme décrit à l’étape 3 de la section [ Importation de fichiers de données Google Ad Manager (anciennement DFP) dans l’Audience Manager ](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Ce faisant, vous pouvez vous assurer que le rapport détaille la propriété web en [!UICONTROL Line Item] au lieu de [!UICONTROL Line Item ID].

## Interprétation des résultats {#interpreting-results}

Votre rapport [!UICONTROL Segment Performance] pourrait ressembler à celui ci-dessous. Dans votre rapport, cliquez sur une bulle pour afficher les données sous-jacentes. Consultez les descriptions des informations supplémentaires dans le tableau ci-dessous de l’exemple de rapport.

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
   <td colname="col1"> <p>Identifiant de segment </p> </td> 
   <td colname="col2"> <p>Identifiant unique de ce segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Élément de ligne </p> </td> 
   <td colname="col2"> <p>La propriété web pour laquelle ce rapport s’affiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Clics </p> </td> 
   <td colname="col2"> <p>Nombre de fois où des membres de cette caractéristique ont cliqué sur des éléments de votre propriété web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impressions </p> </td> 
   <td colname="col2"> <p>Nombre de fois où des membres de cette caractéristique ont été exposés à votre inventaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CTR </p> </td> 
   <td colname="col2"> <p>Taux de clics. </p> <p>Cette mesure représente le pourcentage d’impressions suivies par les clics. Divisez les clics par impressions pour obtenir cette mesure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Population des segments en temps réel </p> </td> 
   <td colname="col2"> <p>Nombre réel de visiteurs uniques affichés en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils ont été vus par l’Audience Manager <span class="keyword"></span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Comment lire les résultats des segments mappés {#read-mapped-segment}

La position des segments mappés dans un rapport peut vous indiquer de nombreuses informations sur les segments qui fonctionnent bien et où vous devrez peut-être effectuer quelques ajustements.

Pour lire le rapport, il est utile de diviser les résultats en quatre sections avec des lignes imaginaires (en rouge) et les catégories affichées dans l&#39;exemple de rapport ci-dessous. Les libellés de l’exemple peuvent vous aider à comprendre les performances des segments et comment répondre à ces résultats.

![](assets/publisher_segment_performance_mapped.png)

## Comment lire les résultats des segments non mappés {#read-unmapped-segment}

L’examen des segments non mappés dans un rapport [!UICONTROL Segment Performance] est un excellent moyen de trouver de nouveaux segments que vous n’avez pas pris en compte pour le ciblage. En fait, certains de ces segments peuvent être plus performants que vos segments mappés.

Pour lire ce rapport, il est utile de diviser les résultats en quatre sections avec des lignes imaginaires (en rouge) et des catégories affichées dans l&#39;exemple de rapport ci-dessous.

![](assets/publisher_segment_performance_unmapped.png)
