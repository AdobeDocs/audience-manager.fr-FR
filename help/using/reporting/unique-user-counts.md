---
description: Décrit la variation des totaux d’utilisateurs uniques entre les rapports pour la même caractéristique et la même période.
seo-description: Décrit la variation des totaux d’utilisateurs uniques entre les rapports pour la même caractéristique et la même période dans Adobe Audience Manager.
seo-title: Comptabilisation des utilisateurs uniques dans le chevauchement et les rapports généraux dans AAM
solution: Audience Manager
title: Comptage des utilisateurs uniques dans les rapports de chevauchement et les rapports généraux
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: Référence du rapports
exl-id: 439e7e8e-0c2e-4d3e-8148-61b9d57bf4df
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 10%

---

# Comptage des utilisateurs uniques dans les rapports de chevauchement et les rapports généraux{#counting-unique-users-in-overlap-and-general-reports}

Cette page décrit la variation des totaux d’utilisateurs uniques entre les rapports pour la même caractéristique et la même période.

<!-- 

c_unique_user_counts.xml

 -->

## Rapport de chevauchement : Nombre d’utilisateurs uniques

Les rapports de chevauchement comptabilisent les utilisateurs comme uniques lorsqu’ils remplissent les critères d’une caractéristique :

* Pendant l&#39;intervalle sélectionné pour le rapport.
* La valeur [time-to-live](../features/traits/segment-ttl-explained.md) est supérieure à l’intervalle sélectionné pour le rapport.
* S&#39;ils sont considérés comme principaux dans notre système (c&#39;est-à-dire qu&#39;ils sont qualifiés pour toute autre caractéristique, qu&#39;ils ont une synchronisation des identifiants, etc.) au cours des 60 derniers jours.

## Rapport général : Nombre d’utilisateurs uniques

Le rapport Général comptabilise les visiteurs du site comme uniques s’ils se sont qualifiés pour la caractéristique au cours de la période sélectionnée.

>[!MORELIKETHIS]
>
>* [Rapports interactifs](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Rapports généraux](../reporting/general-reports.md#general-reports-overview)

