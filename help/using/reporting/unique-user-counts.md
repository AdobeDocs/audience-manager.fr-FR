---
description: Décrit la variation des totaux d’utilisateurs uniques entre les rapports pour la même caractéristique et la même période.
seo-description: Décrit la variation des totaux d’utilisateurs uniques entre les rapports pour la même caractéristique et la même période dans l’Adobe Audience Manager.
seo-title: Comptage des utilisateurs uniques dans le chevauchement et les rapports généraux dans AAM
solution: Audience Manager
title: Comptabilisation des utilisateurs uniques dans les chevauchements et les rapports généraux
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 0%

---


# Comptabilisation des utilisateurs uniques dans les chevauchements et les rapports généraux{#counting-unique-users-in-overlap-and-general-reports}

Cette page décrit la variation des totaux d’utilisateurs uniques entre les rapports pour la même caractéristique et la même période.

<!-- 

c_unique_user_counts.xml

 -->

## Rapport de chevauchement : Nombre d’utilisateurs uniques

Les rapports de chevauchement comptabilisent les utilisateurs comme uniques lorsqu’ils remplissent les critères d’une caractéristique :

* Pendant l&#39;intervalle sélectionné pour le rapport.
* La valeur de [durée de vie](../features/traits/segment-ttl-explained.md) est supérieure à l’intervalle sélectionné pour le rapport.
* S’ils sont considérés comme actifs dans notre système (c.-à-d. qualifiés pour toute autre caractéristique, avec une synchronisation des identifiants, etc.) au cours des 60 derniers jours.

## Rapport général : Nombre d’utilisateurs uniques

Le rapport Général comptabilise les visiteurs du site comme uniques s’ils se sont qualifiés pour la caractéristique au cours de la période sélectionnée.

>[!MORELIKETHIS]
>
>* [Rapports interactifs](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Rapports généraux](../reporting/general-reports.md#general-reports-overview)

