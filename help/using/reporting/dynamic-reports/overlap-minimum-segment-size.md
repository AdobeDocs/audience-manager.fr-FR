---
description: Décrit la taille du segment et le temps de création requis par le processus de mise à jour du rapport de chevauchement.
seo-description: Décrit la taille du segment et le temps de création requis par le processus de mise à jour du rapport de chevauchement.
seo-title: Planification de la mise à jour des rapports de chevauchement et taille minimale du segment
solution: Audience Manager
title: Planification de la mise à jour des rapports de chevauchement et taille minimale du segment
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 3%

---


# Rapports de chevauchement : Mettre à jour le calendrier et la taille minimale du segment{#overlap-reports-update-schedule-and-minimum-segment-size}

Décrit la taille du segment et le temps de création requis par le processus de mise à jour du rapport de chevauchement.

## Mettre à jour le calendrier et les exigences {#update-schedule}

[!UICONTROL Overlap] les rapports sont mis à jour chaque semaine le dimanche. Le prétraitement des rapports commence le samedi. Cela a une incidence sur la façon dont les segments nouveaux ou existants apparaissent dans un rapport de chevauchement le lundi. À inclure dans un rapport de chevauchement :

* Un segment doit contenir au moins 70 000 utilisateurs en temps réel au total au cours des 14 derniers jours. En savoir plus sur la [configuration Visiteur unique minimale requise pour les caractéristiques et les segments](../../reporting/report-sampling.md#data-sampling-ratio).
* Un segment doit avoir été créé avant 12h00 le jeudi UTC (2 jours complets avant le début du processus de mise à jour hebdomadaire du rapport de chevauchement).
* Votre société doit être un [!DNL Audience Manager] client complet. Contactez votre [!DNL Audience Manager] conseiller ou le service à la clientèle pour en savoir plus.

## La taille du segment et/ou l&#39;heure de création affectent le Rapports {#segment-size}

Si un segment ne figure pas dans l’un des [!UICONTROL Overlap] rapports, c’est peut-être parce qu’il ne répond pas à ces exigences minimales.

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
   <td colname="col2"> <p>Supposons que vous créiez un segment avant 12h00 le jeudi UTC, mais qu’il contienne moins de 70 000 utilisateurs en temps réel au total. Ce segment n’apparaîtra pas dans un rapport <span class="wintitle"> de chevauchement</span> tant qu’il ne répond pas aux exigences de seuil utilisateur. Notez également que le segment doit répondre au nombre d’utilisateurs requis le jeudi ou avant la période de coupure. S’il ne respecte pas l’échéance hebdomadaire, le segment apparaîtra dans les rapports <span class="wintitle"> de chevauchement</span> pour la semaine suivant l’exécution des données du dimanche à venir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment créé trop tard</b> </p> </td> 
   <td colname="col2"> <p>Supposons que vous créiez un segment le vendredi et qu’il contienne plus de 70 000 utilisateurs en temps réel au total. Ce segment n’apparaîtra pas dans les rapports <span class="wintitle"> de chevauchement</span> pour la semaine suivante, car il a été créé moins de 2 jours avant la période de mise à jour du rapport. Cependant, le segment s’affichera dans un rapport <span class="wintitle"></span> de chevauchement après la prochaine mise à jour hebdomadaire. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Rapport de chevauchement de caractéristiques](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Rapport de chevauchement de segments et de caractéristiques](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Rapport de chevauchement de segments](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

