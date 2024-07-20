---
description: Décrit la variation des totaux d’utilisateurs uniques entre les rapports pour la même caractéristique et la même période.
seo-description: Describes the variation in unique user totals between reports for the same trait and time period in Adobe Audience Manager
seo-title: Counting Unique Users in Overlap and General Reports in AAM
solution: Audience Manager
title: Comptabilisation des utilisateurs uniques dans les rapports de chevauchement et généraux
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Reporting Reference
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---

# Comptabilisation des utilisateurs uniques dans les rapports de chevauchement et généraux{#counting-unique-users-in-overlap-and-general-reports}

Cette page décrit la variation des totaux d’utilisateurs uniques entre les rapports pour la même caractéristique et la même période.

<!-- 

c_unique_user_counts.xml

 -->

## Rapport de chevauchement : nombre d’utilisateurs uniques

Les rapports de chevauchement comptabilisent les utilisateurs comme uniques lorsqu’ils remplissent les critères d’une caractéristique :

* Pendant l’intervalle sélectionné pour le rapport.
* La valeur [time-to-live](../features/traits/segment-ttl-explained.md) est supérieure à l’intervalle sélectionné pour le rapport.
* S’ils sont considérés comme actifs dans notre système (c’est-à-dire qualifiés pour toute autre caractéristique, ont une synchronisation des identifiants, etc.) dans les 60 derniers jours.

## Rapport général : Nombre d’utilisateurs uniques

Le rapport Général comptabilise les visiteurs du site comme uniques s’ils remplissent les critères de la caractéristique au cours de la période sélectionnée.

>[!MORELIKETHIS]
>
>* [Rapports interactifs](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Rapports généraux](../reporting/general-reports.md#general-reports-overview)
