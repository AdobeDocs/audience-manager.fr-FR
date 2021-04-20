---
description: Le rapport Chevauchement segment/unité publicitaire s’affiche sous la forme d’un graphique à chaleur qui présente les chevauchements élevés et faibles entre vos unités publicitaires et vos segments d’Audience Manager.
seo-description: Le rapport Chevauchement segment/unité publicitaire s’affiche sous la forme d’un graphique à chaleur qui présente les chevauchements élevés et faibles entre vos unités publicitaires et vos segments d’Audience Manager.
seo-title: Segmentation vers le chevauchement d’unité publicitaire
solution: Audience Manager
title: Segmentation vers le chevauchement d’unité publicitaire
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
feature: Audience Optimization Reports
exl-id: 6c7cf2e6-8ed4-42de-92ee-0df90940f441
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---

# Segmentation vers le chevauchement d’unité publicitaire{#segment-to-ad-unit-overlap}

Le rapport Chevauchement segment/unité publicitaire s’affiche sous la forme d’un graphique à chaleur qui présente les chevauchements élevés et faibles entre vos unités publicitaires et vos segments d’Audience Manager.

## Cas d’utilisation {#use-cases}

Le rapport [!UICONTROL Segment to Ad Unit Overlap] vous permet de comprendre quelles audiences visitent vos propriétés Web. Le rapport affiche le chevauchement entre les membres de vos segments [!DNL Audience Manager] et le nombre de visiteurs de vos propriétés Web. Un chevauchement plus élevé signifie que de nombreux membres d’un segment visitent votre propriété Web.

## Utilisation du rapport Chevauchement de segment vers l’unité publicitaire {#using-the-report}

Utilisez les commandes **[!UICONTROL Top N Ad Units]** et **[!UICONTROL Top N Segments]** pour sélectionner le nombre d&#39;unités publicitaires et de segments souhaité pour le chevauchement. Vous pouvez sélectionner un nombre maximum de 100 éléments pour chacun d’eux.

Utilisez les commandes **Plage de jour** et **Date jusqu&#39;à** pour ajuster la plage de recherche en amont. Notez que les périodes de 7 et 30 jours de recherche en arrière ne sont disponibles que pour les dates du dimanche.

Utilisez les zones **[!UICONTROL Segment Name]** et **[!UICONTROL Ad Unit]** pour filtrer l&#39;un des segments et unités publicitaires.

>[!IMPORTANT]
>
>Lorsque vous activez [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Ad Unit IDs], comme décrit à l&#39;étape 3 de [Importer des fichiers de données Google Ad Manager (anciennement DFP) dans l&#39;Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Vous assurez ainsi que le rapport indique la propriété web sous la forme [!UICONTROL Ad Unit] au lieu de [!UICONTROL Ad Unit ID].

## Interprétation des résultats {#interpreting-results}

Votre rapport [!UICONTROL Segment to Ad Unit Overlap] peut ressembler à celui ci-dessous. Passez la souris sur une cellule pour obtenir plus d’informations sur ce chevauchement particulier. Voir la description des informations supplémentaires dans le tableau ci-dessous.

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
   <td colname="col2"> <p>Nom de votre article de stock. Par exemple, il peut s’agir de l’un de vos sites Web ou d’un article de votre site Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre de segments uniques en temps réel</span> </p> </td> 
   <td colname="col2"> <p>Nombre de visiteurs uniques vus en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils étaient vus par <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre d'unités publicitaires uniques</span> </p> </td> 
   <td colname="col2"> <p>Nombre de vos visiteurs pour cette unité publicitaire spécifique. Ces informations sont extraites des journaux Google Ad Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre de chevauchements uniques</span> </p> </td> 
   <td colname="col2"> <p>Membres de votre segment qui ont été exposés à l’élément d’unité publicitaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Pourcentage de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>Le chevauchement entre les populations d’unités publicitaires et de segments. Il s'agit du <span class="wintitle"> nombre de valeurs uniques de chevauchement </span>, exprimé en pourcentage des <span class="wintitle"> segments en temps réel </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
