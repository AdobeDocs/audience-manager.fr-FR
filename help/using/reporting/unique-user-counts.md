---
description: Décrit la variation des totaux d’utilisateurs uniques entre les rapports pour la même caractéristique et la même période.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Comptage des utilisateurs uniques dans les rapports de chevauchement et généraux
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
TQID: https://experienceleague.adobe.com/zQamEx1r5buK4Q4FN-meT3l-8-j3f9Q5Kw2RtO0iPQ8
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6cid: ec0be1ae-7ea9-4f62-869a-963a97d2edc1
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 1%

---

# Comptage des utilisateurs uniques dans les rapports de chevauchement et généraux{#counting-unique-users-in-overlap-and-general-reports}

Cette page décrit la variation des totaux d’utilisateurs uniques entre les rapports pour la même caractéristique et la même période.

<!-- 

c_unique_user_counts.xml

 -->

## Rapport de chevauchement : nombre d’utilisateurs uniques

Les rapports de chevauchement comptabilisent les utilisateurs comme uniques lorsqu’ils remplissent les critères d’une caractéristique :

* Pendant l’intervalle sélectionné pour le rapport.
* qui a une valeur [durée de vie](../features/traits/segment-ttl-explained.md) supérieure à l’intervalle de temps sélectionné pour le rapport.
* S’ils sont considérés comme actifs dans notre système (c’est-à-dire qu’ils sont qualifiés pour toute autre caractéristique, qu’ils ont eu une synchronisation des identifiants, etc.) au cours des 60 derniers jours.

## Rapport général : nombre d’utilisateurs uniques

Le rapport Général comptabilise les visiteurs du site comme uniques s’ils remplissent les critères pour la caractéristique pendant la période sélectionnée.

>[!MORELIKETHIS]
>
>* [ Rapports interactifs ](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Rapports généraux](../reporting/general-reports.md#general-reports-overview)
