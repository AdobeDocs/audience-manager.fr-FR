---
description: Le rapport de chevauchement d'unités publicitaires s'affiche sous la forme d'un diagramme à chaud qui met en évidence les chevauchements élevés et faibles entre vos unités publicitaires.
seo-description: Le rapport de chevauchement d'unités publicitaires s'affiche sous la forme d'un diagramme à chaud qui met en évidence les chevauchements élevés et faibles entre vos unités publicitaires.
seo-title: Chevauchement d'unités publicitaires
solution: Audience Manager
title: Chevauchement d'unités publicitaires
uuid: e 4467 e 81-acbf -474 e-b 501-89 d 57395651 f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ad Unit Overlap{#ad-unit-overlap}

**[!UICONTROL Ad Unit Overlap]** Le rapport s&#39;affiche sous la forme d&#39;un graphique à chaud qui met en surbrillance les zones hautes et basses entre les unités publicitaires.

## Cas d’utilisation {#use-cases}

With the **[!UICONTROL Ad Unit Overlap]** report, you can gain insight into where your audience overlaps across your web properties. Le rapport tient compte des 100 principales propriétés liées et vous montre le chevauchement entre ces deux propriétés.

## Using the Ad Unit Overlap Report {#using-the-report}

Use the **[!UICONTROL Top N Base Ad Units]** and **[!UICONTROL Top N Overlapping Ad Units]** controls to select your desired number of ad units for the overlap. Vous pouvez sélectionner un nombre maximum de 100 éléments pour chacun d&#39;eux.

Use the **Day Range** and **Date Through** controls to adjust your look-back range. Notez que les périodes de recherche de 7 et 30 jours ne sont disponibles que pour les dates dimanche.

Use the **[!UICONTROL Base Ad Unit]** and the **[!UICONTROL Overlap Ad Unit]** controls to select which of your ad units you want to display in the overlap report.

>[!IMPORTANT]
>
>When enabling [!UICONTROL Audience Optimization for Publishers], you must include descriptive metadata for [!UICONTROL Ad Unit IDs], as described in Step 3 of [Import DFP Data Files Into Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). By doing this, you assure that the report details the web property as [!UICONTROL Ad Unit] instead of the [!UICONTROL Ad Unit ID].

## Interpreting the Results {#interpreting-results}

Your [!UICONTROL Ad Unit Overlap] report could look similar to the one below. Passez la souris sur une cellule pour obtenir plus d&#39;informations sur ce chevauchement particulier. Voir Descriptions pour obtenir des informations supplémentaires dans le tableau sous l&#39;exemple de rapport.

![](assets/publisher_ad_unit_overlap.png)

<table id="table_22340F45B1B94D3796174CB30A60E212"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Élément </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Chevauchement de l'unité publicitaire</span> </p> </td> 
   <td colname="col2"> <p>Nom de l'élément de stock. Par exemple, il peut s'agir de l'un de vos sites Web ou d'un article sur votre site Web. Dans l'image ci-dessus, les unités d'annonce de base sont les articles 9 à 18. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Unité de base de l'annonce</span> </p> </td> 
   <td colname="col2"> <p>Nom de l'élément de stock. Par exemple, il peut s'agir de l'un de vos sites Web ou d'un article sur votre site Web. Dans l'image ci-dessus, les unités d'annonce de base sont les articles 1 à 8. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Chevauchement du nombre d'unités publicitaires</span> </p> </td> 
   <td colname="col2"> <p>Nombre de vos utilisateurs qui ont visité les articles d'unité publicitaire 9 à 18. Ces informations sont extraites des journaux DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre d'unités de publicité de base</span> </p> </td> 
   <td colname="col2"> <p>Nombre de vos utilisateurs qui ont visité les articles d'unité publicitaire 1 à 8. Ces informations sont extraites des journaux DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Chevauchement des valeurs uniques</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Pourcentage de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>The overlap between your users who have visited a <span class="wintitle"> Base Ad Unit</span> and <span class="wintitle"> Overlap Ad Unit</span>. This is the <span class="wintitle"> Overlap Uniques Count</span>, expressed as a percentage of the <span class="wintitle"> Base Ad Unit</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
