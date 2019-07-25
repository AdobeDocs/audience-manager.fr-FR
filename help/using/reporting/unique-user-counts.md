---
description: Décrit la variation des totaux d'utilisateurs uniques entre les rapports pour la même caractéristique et la même période.
seo-description: Décrit la variation des totaux d'utilisateurs uniques entre les rapports pour la même caractéristique et la même période dans Adobe Audience Manager.
seo-title: Comptabilisation des utilisateurs uniques dans le chevauchement et les rapports généraux dans AAM
solution: Audience Manager
title: Comptabilisation des utilisateurs uniques dans le chevauchement et les rapports généraux
uuid: 450 f 6 a 8 c-f 363-43 de-b 2 d 8-0 a 156 f 14 ecae
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Counting Unique Users in Overlap and General Reports{#counting-unique-users-in-overlap-and-general-reports}

Cette page décrit la variation des totaux d'utilisateurs uniques entre les rapports pour la même caractéristique et la même période.

<!-- 

c_unique_user_counts.xml

 -->

## Rapport de chevauchement : Nombre d'utilisateurs uniques

Les rapports de chevauchement comptabilisent les utilisateurs comme uniques lorsqu'ils remplissent les critères d'une caractéristique :

* Pendant l'intervalle sélectionné pour le rapport.
* That has a [time-to-live](../features/traits/segment-ttl-explained.md) value longer than the selected time interval for the report.
* S'ils sont considérés comme actifs dans notre système (c'est-à-dire qualifiés pour toute autre caractéristique, avaient une synchronisation des identifiants, etc.) au cours des 60 derniers jours.

## Rapport général : Nombre d'utilisateurs uniques

Le rapport Général compte les visiteurs du site comme uniques s'ils sont qualifiés pour la caractéristique durant la période sélectionnée.

>[!MORE_ LIKE_ THIS]
>
>* [Rapports interactifs](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Rapports généraux](../reporting/general-reports.md#general-reports-overview)

