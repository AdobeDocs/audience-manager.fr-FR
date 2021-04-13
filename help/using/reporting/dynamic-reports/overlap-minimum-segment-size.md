---
description: Décrit la taille du segment et le temps de création requis par le processus de mise à jour du rapport de chevauchement.
seo-description: Décrit la taille du segment et le temps de création requis par le processus de mise à jour du rapport de chevauchement.
seo-title: Planification de la mise à jour des rapports de chevauchement et taille minimale du segment
solution: Audience Manager
title: Planification de la mise à jour des rapports de chevauchement et taille minimale du segment
uuid: 35c1cb39-e28d-4d20-88c9-5ff4fe154e9e
feature: Rapports de chevauchement
exl-id: 89fa9d92-8676-4706-9fab-22c35763b218
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 5%

---

# Rapports de chevauchement : mise à jour des plannings et des tailles de segment minimum{#overlap-reports-update-schedule-and-minimum-segment-size}

Décrit la caractéristique, la taille du segment et les exigences en termes de temps de création requises par le processus de mise à jour du rapport sur le chevauchement.

## Mettre à jour le calendrier et les exigences {#update-schedule}

[!UICONTROL Overlap] les rapports sont mis à jour chaque semaine le dimanche. Le prétraitement des rapports commence le samedi. Cela a une incidence sur la façon dont les segments nouveaux ou existants apparaissent dans un rapport de chevauchement le lundi. À inclure dans un rapport de chevauchement :

* Un segment doit contenir au moins 70 000 utilisateurs en temps réel au total au cours des 14 derniers jours.
* Une caractéristique doit contenir 28 000 [réalisations de caractéristiques uniques](/help/using/features/traits/trait-and-segment-qualification-reference.md) au cours des 14 derniers jours.
* Un segment doit avoir été créé avant 12h00 le jeudi UTC (2 jours complets avant le début du processus de mise à jour hebdomadaire du rapport de chevauchement).
* Votre société doit être un client complet [!DNL Audience Manager]. Veuillez contacter votre [!DNL Audience Manager] consultant ou le service à la clientèle pour en savoir plus.

## Taille du segment et/ou heure de création affecte le Rapports {#segment-size}

Si un segment ne figure pas dans l&#39;un des rapports [!UICONTROL Overlap], c&#39;est peut-être parce qu&#39;il ne répond pas à ces exigences minimales.

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
   <td colname="col2"> <p>Supposons que vous créiez un segment avant 12h00 le jeudi UTC, mais qu’il contienne moins de 70 000 utilisateurs en temps réel au total. Ce segment n’apparaîtra pas dans un rapport de chevauchement <span class="wintitle"> </span> tant qu’il ne répond pas aux exigences de seuil utilisateur. Notez également que le segment doit répondre au nombre d’utilisateurs requis le jeudi ou avant la période de coupure. S’il ne respecte pas l’échéance hebdomadaire, le segment s’affichera dans les <span class="wintitle"> Rapports de chevauchement</span> pour la semaine suivant l’exécution des données du dimanche à venir. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment créé trop tard</b> </p> </td> 
   <td colname="col2"> <p>Supposons que vous créiez un segment le vendredi et qu’il contienne plus de 70 000 utilisateurs en temps réel au total. Ce segment n'apparaîtra pas dans les rapports de chevauchement <span class="wintitle"> pour la semaine suivante, car il a été créé moins de 2 jours avant la période de mise à jour du rapport. </span> Cependant, le segment apparaîtra dans un rapport de chevauchement <span class="wintitle"> </span> après la prochaine mise à jour hebdomadaire. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Rapport de chevauchement de caractéristiques](../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report)
>* [Rapport de chevauchement de segments et de caractéristiques](../../reporting/dynamic-reports/segment-trait-overlap-report.md)
>* [Rapport de chevauchement de segments](../../reporting/dynamic-reports/segment-segment-overlap-report.md)

