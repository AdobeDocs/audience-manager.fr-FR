---
description: Le rapport de chevauchement de segments et d’unités publicitaires s’affiche sous forme d’un graphique à chaleur qui présente les chevauchements élevés et faibles entre vos unités publicitaires et vos segments d’Audience Manager.
seo-description: Le rapport de chevauchement de segments et d’unités publicitaires s’affiche sous forme d’un graphique à chaleur qui présente les chevauchements élevés et faibles entre vos unités publicitaires et vos segments d’Audience Manager.
seo-title: Segmentation vers le chevauchement d’unité publicitaire
solution: Audience Manager
title: Segmentation vers le chevauchement d’unité publicitaire
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Rapports d’Audience Optimization
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---

# Segmentation vers le chevauchement d’unité publicitaire{#segment-to-ad-unit-overlap}

Le rapport de chevauchement de segments et d’unités publicitaires s’affiche sous forme d’un graphique à chaleur qui présente les chevauchements élevés et faibles entre vos unités publicitaires et vos segments d’Audience Manager.

## Cas d’utilisation {#use-cases}

Grâce au rapport [!UICONTROL Segment to Ad Unit Overlap], vous pouvez déterminer les audiences qui visitent vos propriétés web. Le rapport affiche le chevauchement entre les membres de vos segments [!DNL Audience Manager] et le nombre de visiteurs sur vos propriétés web. Un chevauchement plus élevé signifie que de nombreux membres d’un segment visitent votre propriété web.

## Utilisation du rapport de chevauchement Segment vers unité publicitaire {#using-the-report}

Utilisez les contrôles **[!UICONTROL Top N Ad Units]** et **[!UICONTROL Top N Segments]** pour sélectionner le nombre d’unités publicitaires et de segments souhaité pour le chevauchement. Vous pouvez sélectionner un nombre maximal de 100 éléments pour chaque élément.

Utilisez les commandes **Période** et **Date d’expiration** pour ajuster la période d’analyse. Notez que les périodes d’analyse de 7 et 30 jours ne sont disponibles que pour les dates du dimanche.

Utilisez les zones **[!UICONTROL Segment Name]** et **[!UICONTROL Ad Unit]** pour filtrer les segments et les unités publicitaires.

>[!IMPORTANT]
>
>Lors de l’activation de [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Ad Unit IDs], comme décrit à l’étape 3 de la section [Importation de fichiers de données Google Ad Manager (anciennement DFP) dans l’Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Vous pouvez ainsi vous assurer que le rapport présente la propriété web sous la forme [!UICONTROL Ad Unit] au lieu de [!UICONTROL Ad Unit ID].

## Interprétation des résultats {#interpreting-results}

Votre rapport [!UICONTROL Segment to Ad Unit Overlap] pourrait ressembler à celui ci-dessous. Passez la souris sur une cellule pour obtenir plus d’informations sur ce chevauchement particulier. Consultez les descriptions des informations supplémentaires dans le tableau ci-dessous de l’exemple de rapport.

![](assets/publisher_segment_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unité publicitaire  </span> </p> </td> 
   <td colname="col2"> <p>Nom de votre article de stock. Il peut s’agir, par exemple, de l’un de vos sites web ou d’un article de votre site web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre de segments uniques en temps réel</span> </p> </td> 
   <td colname="col2"> <p>Nombre de visiteurs uniques affichés en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils ont été vus par <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre unique d’unités publicitaires</span> </p> </td> 
   <td colname="col2"> <p>Nombre de visiteurs pour cette unité publicitaire spécifique. Ces informations sont extraites des journaux Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre unique de chevauchements</span> </p> </td> 
   <td colname="col2"> <p>Les membres de votre segment qui ont été exposés à l’élément de l’unité publicitaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Pourcentage de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>Chevauchement entre les populations d’unités d’annonces et de segments. Il s’agit du <span class="wintitle"> nombre de valeurs uniques de chevauchement</span>, exprimé en pourcentage des <span class="wintitle"> valeurs uniques en temps réel du segment</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
