---
description: Décrit la taille du segment et le temps de création requis par le processus de mise à jour du rapport de chevauchement.
seo-description: Décrit la taille du segment et le temps de création requis par le processus de mise à jour du rapport de chevauchement.
seo-title: Planification de la mise à jour des rapports de chevauchement et taille minimale du segment
solution: Audience Manager
title: Planification de la mise à jour des rapports de chevauchement et taille minimale du segment
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Rapports de chevauchement : Mettre à jour le calendrier et la taille minimale du segment{#overlap-reports-update-schedule-and-minimum-segment-size}

Décrit la taille du segment et le temps de création requis par le processus de mise à jour du rapport de chevauchement.

## Mise à jour du calendrier et des exigences {#update-schedule}

[!UICONTROL Overlap] les rapports sont mis à jour chaque semaine le dimanche. Le prétraitement des rapports commence le samedi. Cela affecte la manière dont les segments nouveaux ou existants apparaissent dans un rapport de chevauchement lundi. À inclure dans un rapport de chevauchement :

* Un segment doit contenir au moins 70 000 utilisateurs en temps réel au total au cours des 14 derniers jours. En savoir plus sur les exigences [minimales de visiteurs uniques pour les caractéristiques et les segments](../../reporting/report-sampling.md#data-sampling-ratio).
* Un segment doit avoir été créé avant 12h00 le jeudi (2 jours complets avant le début du processus de mise à jour hebdomadaire du rapport de chevauchement).
* Votre entreprise doit être un [!DNL Audience Manager] client complet. Contactez votre [!DNL Audience Manager] consultant ou le service à la clientèle pour en savoir plus.

## La taille du segment et/ou le temps de création affectent la création de rapports {#segment-size}

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
   <td colname="col2"> <p>Supposons que vous créiez un segment avant 12h00 le jeudi, mais qu’il contienne moins de 70 000 utilisateurs en temps réel au total. Ce segment n’apparaîtra pas dans un rapport <span class="wintitle"></span> de chevauchement tant qu’il ne répond pas aux exigences de seuil utilisateur. Notez également que le segment doit répondre au nombre d’utilisateurs requis le ou avant la période de coupure du jeudi. S’il ne respecte pas l’échéance hebdomadaire, le segment apparaît dans les rapports <span class="wintitle"></span> de chevauchement pour la semaine qui suit l’exécution des données du dimanche à venir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment créé trop tard</b> </p> </td> 
   <td colname="col2"> <p>Supposons que vous créiez un segment le vendredi et qu’il contienne plus de 70 000 utilisateurs en temps réel au total. Ce segment n’apparaîtra pas dans les rapports <span class="wintitle"></span> de chevauchement pour la semaine suivante, car il a été créé moins de 2 jours avant la période de mise à jour du rapport. Toutefois, le segment apparaîtra dans un rapport <span class="wintitle"> de chevauchement</span> après la prochaine mise à jour hebdomadaire. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Rapport de chevauchement de caractéristiques](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Rapport de chevauchement de segments et de caractéristiques](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Rapport de chevauchement de segments](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

