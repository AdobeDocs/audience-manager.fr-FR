---
description: Le rapport de chevauchement du segment à l'unité publicitaire s'affiche sous la forme d'un graphique à chaud qui met en évidence les chevauchements élevés et faibles entre les segments d'unités publicitaires et d'Audience Manager.
seo-description: Le rapport de chevauchement du segment à l'unité publicitaire s'affiche sous la forme d'un graphique à chaud qui met en évidence les chevauchements élevés et faibles entre les segments d'unités publicitaires et d'Audience Manager.
seo-title: Segment au chevauchement d'unités publicitaires
solution: Audience Manager
title: Segment au chevauchement d'unités publicitaires
uuid: aaa 20163-58 aa -42 c 9-8 f 72-a 1 dfb 0 d 20 e 57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Segment to Ad Unit Overlap{#segment-to-ad-unit-overlap}

Le rapport de chevauchement du segment à l&#39;unité publicitaire s&#39;affiche sous la forme d&#39;un graphique à chaud qui met en évidence les chevauchements élevés et faibles entre les segments d&#39;unités publicitaires et d&#39;Audience Manager.

## Cas d’utilisation {#use-cases}

With the [!UICONTROL Segment to Ad Unit Overlap] report, you can understand which audiences visit your web properties. The report displays the overlap between members of your [!DNL Audience Manager] segments and the number of visitors to your web properties. Un chevauchement plus élevé signifie que de nombreux membres d&#39;un segment visitent votre propriété Web.

## Using the Segment to Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Ad Units]** and **[!UICONTROL Top N Segments]** controls to select your desired number of ad units and segments for the overlap. Vous pouvez sélectionner un nombre maximum de 100 éléments pour chacun d&#39;eux.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Notez que les périodes de recherche de 7 et 30 jours ne sont disponibles que pour les dates dimanche.

Use the **[!UICONTROL Segment Name]** and the **[!UICONTROL Ad Unit]** boxes to filter any of segments and ad units.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Segment to Ad Unit Overlap] report could look similar to the one below. Passez la souris sur une cellule pour obtenir plus d&#39;informations sur ce chevauchement particulier. Voir Descriptions pour obtenir des informations supplémentaires dans le tableau sous l&#39;exemple de rapport.

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
   <td colname="col1"> <p><span class="wintitle"> Unité d'annonce </span> </p> </td> 
   <td colname="col2"> <p>Nom de l'élément de stock. Par exemple, il peut s'agir de l'un de vos sites Web ou d'un article sur votre site Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment réel - Nombre unique de fois</span> </p> </td> 
   <td colname="col2"> <p>The number of unique visitors seen in real-time for the specified time range and who were qualified for the segment at the moment they were seen by <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre de valeurs uniques d'unité publicitaire</span> </p> </td> 
   <td colname="col2"> <p>Nombre de visiteurs pour cette unité d'annonce spécifique. Ces informations sont extraites des journaux DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Chevauchement des valeurs uniques</span> </p> </td> 
   <td colname="col2"> <p>Membres de votre segment qui étaient exposés à l'article de l'unité publicitaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Pourcentage de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>Chevauchement entre les populations d'annonces et les populations de segments. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Segment Real Time Uniques</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

