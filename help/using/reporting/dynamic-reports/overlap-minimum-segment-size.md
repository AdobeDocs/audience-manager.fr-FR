---
description: Décrit la taille du segment et les délais de création requis par le processus de mise à jour du rapport de chevauchement.
seo-description: Describes the segment size and creation time requirements required by the Overlap report update process.
seo-title: Overlap Reports  Update Schedule and Minimum Segment Size
solution: Audience Manager
title: 'Rapports de chevauchement : mise à jour du calendrier et de la taille minimale du segment'
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Overlap Reports
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 3%

---

# Rapports de chevauchement : mise à jour de la planification et de la taille minimale du segment{#overlap-reports-update-schedule-and-minimum-segment-size}

Décrit les caractéristiques et la taille du segment, ainsi que le temps de création requis par le processus de mise à jour du rapport de chevauchement.

## Mise à jour de la planification et des exigences {#update-schedule}

Les rapports [!UICONTROL Overlap] sont mis à jour chaque semaine le dimanche. Le prétraitement des rapports commence le samedi. Cela affecte la manière dont les segments nouveaux ou existants apparaissent dans un rapport de chevauchement lundi. À inclure dans un rapport de chevauchement :

* Un segment doit contenir au moins 70 000 utilisateurs en temps réel au total au cours des 14 derniers jours.
* Une caractéristique doit contenir 28 000 [réalisations de caractéristiques uniques](/help/using/features/traits/trait-and-segment-qualification-reference.md) au cours des 14 derniers jours.
* Un segment doit avoir été créé avant 12h00 jeudi UTC (2 jours complets avant le début du processus de mise à jour hebdomadaire du rapport de chevauchement).
* Votre entreprise doit être un client [!DNL Audience Manager] complet. Contactez votre consultant [!DNL Audience Manager] ou l’assistance clientèle pour en savoir plus.

## La taille du segment et/ou le temps de création affectent la création de rapports {#segment-size}

Si un segment ne figure pas dans l’un des rapports [!UICONTROL Overlap], c’est peut-être parce qu’il ne répond pas à ces exigences minimales.

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
   <td colname="col2"> <p>Supposons que vous créiez un segment avant 12h00 jeudi (UTC), mais il contient moins de 70 000 utilisateurs en temps réel au total. Ce segment n’apparaîtra pas dans un <span class="wintitle"> rapport de chevauchement</span> tant qu’il ne répond pas aux exigences de seuil utilisateur. Notez également que le segment doit correspondre au nombre d’utilisateurs requis, ou avant la période d’interruption du jeudi. S’il ne respecte pas la date limite hebdomadaire, le segment apparaîtra dans les <span class="wintitle"> rapports de chevauchement</span> pour la semaine suivant l’exécution des données du dimanche à venir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment créé trop tard</b> </p> </td> 
   <td colname="col2"> <p>Supposons que vous créiez un segment le vendredi et qu’il contienne plus de 70 000 utilisateurs en temps réel au total. Ce segment n’apparaîtra pas dans les <span class="wintitle"> rapports de chevauchement</span> pour la semaine suivante, car il a été créé moins de 2 jours avant la période de mise à jour du rapport. Cependant, le segment apparaîtra dans un <span class="wintitle"> rapport de chevauchement</span> après la prochaine mise à jour hebdomadaire. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Rapport de chevauchement de caractéristiques](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Rapport de chevauchement de segments et de caractéristiques](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Rapport de chevauchement de segments](../../reporting/dynamic-reports/segment-segment-overlap-report.md)
