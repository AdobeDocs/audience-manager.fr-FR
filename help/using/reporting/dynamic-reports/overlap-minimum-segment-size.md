---
description: Décrit les exigences en matière de taille et heure de création requises par le processus de mise à jour du rapport de chevauchement.
seo-description: Décrit les exigences en matière de taille et heure de création requises par le processus de mise à jour du rapport de chevauchement.
seo-title: Les rapports de chevauchement mettent à jour la planification et la taille minimale du segment
solution: Audience Manager
title: Les rapports de chevauchement mettent à jour la planification et la taille minimale du segment
uuid: 35 c 1 cb 39-e 28 d -4 d 20-88 c 9-5 ff 4 fe 154 e 9 e
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Overlap Reports: Update Schedule and Minimum Segment Size{#overlap-reports-update-schedule-and-minimum-segment-size}

Décrit les exigences en matière de taille et heure de création requises par le processus de mise à jour du rapport de chevauchement.

## Update Schedule and Requirements {#update-schedule}

[!UICONTROL Overlap] les rapports sont mis à jour chaque semaine le dimanche. Le prétraitement des rapports commence le samedi. Cela affecte la manière dont les segments nouveaux ou existants apparaissent dans un rapport de chevauchement le lundi. Pour être inclus dans un rapport de chevauchement :

* Un segment doit contenir au moins 70 000 utilisateurs en temps réel au cours des 14 derniers jours. Read more about [Minimum Unique Visitor Requirements for Traits and Segments](../../reporting/report-sampling.md#data-sampling-ratio).
* Un segment doit avoir été créé avant MIDI le jeudi UTC (2 jours complets avant le début du processus de mise à jour hebdomadaire du rapport de chevauchement).
* Your company must be a Full [!DNL Audience Manager] customer. Please contact your [!DNL Audience Manager] consultant or Customer Care to find out more.

## Segment Size and/or Creation Time Affects Reporting {#segment-size}

If you do not see a segment in one of the [!UICONTROL Overlap] reports, it may be because the segment does not meet these minimum requirements.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Taille de segment trop petite</b> </p> </td> 
   <td colname="col2"> <p>Imaginons que vous créiez un segment avant MIDI avant MIDI, mais qu'il contienne moins de 70 000 utilisateurs en temps réel. This segment won't appear in an <span class="wintitle"> Overlap Report</span> until it meets the user threshold requirements. Remarque : le segment doit également correspondre au nombre d'utilisateurs requis pour la période de coupure du jeudi. If it does not meet the weekly deadline, the segment will appear in the <span class="wintitle"> Overlap Reports</span> for the week after the upcoming Sunday data run. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment créé trop tard</b> </p> </td> 
   <td colname="col2"> <p>Imaginons que vous créiez un segment le vendredi et qu'il contienne plus de 70 000 utilisateurs en temps réel. This segment won't appear in the <span class="wintitle"> Overlap Reports</span> for the next week because it was created less than 2 days prior to the report update period. However, the segment will appear in an <span class="wintitle"> Overlap Report</span> after the next weekly update. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Rapport de chevauchement de caractéristiques](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Rapport de chevauchement de segments et de caractéristiques](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Rapport de chevauchement de segments](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

