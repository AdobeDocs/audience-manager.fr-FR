---
description: Le rapport Chevauchement segment/unité publicitaire s’affiche sous la forme d’un graphique thermique qui met en évidence les chevauchements élevés et faibles entre vos unités publicitaires et les segments d’Audience Manager.
seo-description: Le rapport Chevauchement segment/unité publicitaire s’affiche sous la forme d’un graphique thermique qui met en évidence les chevauchements élevés et faibles entre vos unités publicitaires et les segments d’Audience Manager.
seo-title: Chevauchement de segment vers l’unité publicitaire
solution: Audience Manager
title: Chevauchement de segment vers l’unité publicitaire
uuid: aaa20163-58aa-42c9-8f72-a1dfb0d20e57
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Chevauchement de segment vers l’unité publicitaire{#segment-to-ad-unit-overlap}

Le rapport Chevauchement segment/unité publicitaire s’affiche sous la forme d’un graphique thermique qui met en évidence les chevauchements élevés et faibles entre vos unités publicitaires et les segments d’Audience Manager.

## Cas d’utilisation {#use-cases}

Le [!UICONTROL Segment to Ad Unit Overlap] rapport vous permet de comprendre les audiences qui visitent vos propriétés Web. Le rapport affiche le chevauchement entre les membres de vos [!DNL Audience Manager] segments et le nombre de visiteurs de vos propriétés Web. Un chevauchement plus important signifie que de nombreux membres d’un segment visitent votre propriété Web.

## Utilisation du rapport Chevauchement de segment vers une unité publicitaire {#using-the-report}

Utilisez les commandes **[!UICONTROL Top N Ad Units]** et **[!UICONTROL Top N Segments]** pour sélectionner le nombre d’unités publicitaires et de segments souhaité pour le chevauchement. Vous pouvez sélectionner un nombre maximum de 100 éléments pour chaque élément.

Utilisez les commandes **Plage** de jour et **Date jusqu’au bout** pour ajuster la plage de retour arrière. Notez que les périodes de 7 jours et de 30 jours sont disponibles uniquement pour les dates du dimanche.

Utilisez les **[!UICONTROL Segment Name]** zones et les **[!UICONTROL Ad Unit]** zones pour filtrer les segments et les unités publicitaires.

>[!IMPORTANT]
>
>Lors de l’activation [!UICONTROL Audience Optimization for Publishers], vous devez inclure des métadonnées descriptives pour [!UICONTROL Ad Unit IDs], comme décrit à l’étape 3 de l’ [importation de fichiers de données DFP dans Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Vous garantissez ainsi que le rapport indique la propriété web comme [!UICONTROL Ad Unit] au lieu de la propriété [!UICONTROL Ad Unit ID].

## Interprétation des résultats {#interpreting-results}

Votre [!UICONTROL Segment to Ad Unit Overlap] rapport pourrait ressembler à celui ci-dessous. Passez la souris sur une cellule pour obtenir plus d’informations sur ce chevauchement particulier. Voir la description des informations supplémentaires dans le tableau ci-dessous.

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
   <td colname="col1"> <p><span class="wintitle"> Unité publicitaire </span> </p> </td> 
   <td colname="col2"> <p>Nom de votre article de stock. Par exemple, il peut s’agir de l’un de vos sites Web ou d’un article de votre site Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre de segments uniques en temps réel</span> </p> </td> 
   <td colname="col2"> <p>Nombre de visiteurs uniques affichés en temps réel pendant la période spécifiée et qui étaient qualifiés pour le segment au moment où ils étaient vus par <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre d'unités publicitaires uniques</span> </p> </td> 
   <td colname="col2"> <p>Nombre de visiteurs pour cette unité publicitaire spécifique. Ces informations sont extraites des journaux DFP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Nombre de chevauchements uniques</span> </p> </td> 
   <td colname="col2"> <p>Membres de votre segment qui ont été exposés à l’élément d’unité publicitaire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Pourcentage de chevauchement</span> </p> </td> 
   <td colname="col2"> <p>Le chevauchement entre les populations d’unités publicitaires et de segments. Il s’agit du nombre <span class="wintitle"> unique de chevauchement des</span>segments, exprimé en pourcentage des <span class="wintitle"></span>segments en temps réel. </p> </td> 
  </tr> 
 </tbody> 
</table>

