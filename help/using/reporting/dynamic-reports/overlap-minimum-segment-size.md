---
description: Décrit les exigences en matière de taille de segment et de temps de création requises par le processus de mise à jour du rapport de chevauchement.
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: Calendrier de mise à jour des rapports de chevauchement et taille minimale des segments
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 3%

---

# Rapports de chevauchement : mise à jour du planning et de la taille minimale du segment{#overlap-reports-update-schedule-and-minimum-segment-size}

Décrit les exigences en matière de taille de caractéristique et de segment et de temps de création requises par le processus de mise à jour du rapport de chevauchement.

## Mettre à jour le planning et les exigences {#update-schedule}

[!UICONTROL Overlap] rapports sont mis à jour chaque semaine le dimanche. Le prétraitement des rapports commence le samedi. Cela affecte la façon dont les segments nouveaux ou existants apparaissent dans un rapport de chevauchement le lundi. À inclure dans un rapport de chevauchement :

* Un segment doit contenir au moins 70 000 utilisateurs et utilisatrices en temps réel au total au cours des 14 derniers jours.
* Une caractéristique doit contenir 28 000 [réalisations de caractéristiques uniques](/help/using/features/traits/trait-and-segment-qualification-reference.md) au cours des 14 derniers jours.
* Un segment doit avoir été créé avant 00 h 00, jeudi UTC (2 jours complets avant le début du processus de mise à jour hebdomadaire du rapport de chevauchement).
* Votre entreprise doit être un client Full [!DNL Audience Manager]. Contactez votre consultant [!DNL Audience Manager] ou l’assistance clientèle pour en savoir plus.

## La taille du segment et/ou le temps de création affectent la création de rapports {#segment-size}

Si vous ne voyez pas de segment dans l’un des rapports [!UICONTROL Overlap], c’est peut-être parce que le segment ne répond pas à ces exigences minimales.

<table id="table_BE2937C1FA314BBDBD1D026321D6E6B1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cas d’utilisation </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Taille Du Segment Trop Petite</b> </p> </td> 
   <td colname="col2"> <p>Supposons que vous créiez un segment avant 00 h 00, jeudi UTC, mais qu’il contienne moins de 70 000 utilisateurs au total en temps réel. Ce segment n’apparaîtra dans un rapport de chevauchement de <span class="wintitle"> que s’il répond </span> conditions requises pour le seuil utilisateur. Notez également que le segment doit correspondre au nombre d’utilisateurs requis au moment de la période limite du jeudi ou avant cette date. S’il ne respecte pas l’échéance hebdomadaire, le segment s’affiche dans les rapports de chevauchement <span class="wintitle"> pour la semaine suivant </span>’exécution des données de dimanche à venir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment Créé Trop Tard</b> </p> </td> 
   <td colname="col2"> <p>Supposons que vous créiez un segment le vendredi et qu’il contienne plus de 70 000 utilisateurs au total en temps réel. Ce segment n’apparaîtra pas dans les <span class="wintitle"> rapports de chevauchement</span> pour la semaine suivante, car il a été créé moins de 2 jours avant la période de mise à jour du rapport. Cependant, le segment apparaîtra dans un rapport de chevauchement <span class="wintitle"> après </span> prochaine mise à jour hebdomadaire. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Rapport de chevauchement de caractéristiques](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Rapport de chevauchement de segments et de caractéristiques](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Rapport de chevauchement de segments](../../reporting/dynamic-reports/segment-segment-overlap-report.md)
