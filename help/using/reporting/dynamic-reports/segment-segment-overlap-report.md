---
description: Renvoie des données sur le nombre d’utilisateurs uniques partagés entre vos segments.
seo-description: Renvoie des données sur le nombre d’utilisateurs uniques partagés entre vos segments.
seo-title: Rapport de chevauchement de segments
solution: Audience Manager
title: Rapport de chevauchement de segments
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 11%

---


# Rapport de chevauchement de segments{#segment-to-segment-overlap-report}

Renvoie des données sur le nombre d’utilisateurs uniques partagés entre vos segments.

>[!NOTE]
>
>Les rapports de chevauchement en Audience Manager respectent les principes du CCRAC. Vous ne pouvez afficher que les segments provenant des sources de données auxquelles vous avez accès en fonction du groupe [d’utilisateurs](/help/using/features/administration/administration-overview.md) RBAC auquel vous appartenez.

<!-- 

c_segment_segment_overlap.xml

 -->

## Présentation

Le [!UICONTROL Segment-to-Segment Overlap] rapport peut vous aider à :

* Identifiez les segments présentant un chevauchement élevé ou faible, en fonction de vos besoins. Les caractéristiques avec un chevauchement élevé vous donnent une audience ciblée, mais moins de visiteurs uniques. Les caractéristiques présentant un faible chevauchement peuvent s’avérer utiles pour atteindre un ensemble de visiteurs unique plus grand.
* Recherchez les chevauchements inattendus et utilisez ces informations pour créer de nouveaux segments hautes performances.

## Exemple de rapport

L’illustration suivante présente un aperçu général du [!UICONTROL Segment-to-Segment Overlap] rapport.

>[!NOTE]
>
>Le [!UICONTROL Segment-to-Segment Overlap] rapport renvoie un champ vide lorsqu’il compare le même segment à lui-même.

![](assets/segment-to-segment-overlap.png)

## Zoom sur les points de données individuels

Sélectionnez un point individuel pour accéder aux détails des données de vue dans une fenêtre contextuelle. Les actions de clic mettent automatiquement à jour les données affichées dans le rapport.

## Définition des champs contextuels de données de chevauchement segment-à-segment {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

La fenêtre contextuelle du [!UICONTROL Segment-to-Segment Overlap] rapport contient les mesures ci-dessous. Notez que les mesures uniques du tableau représentent vos utilisateurs ** en temps réel.

| Mesure | Description |
|---|---|
| **[!UICONTROL Base Segment ID]** | ID numérique unique du segment qui apparaît dans les résultats du rapport. Apparaît comme ID de ligne pour le segment. |
| **[!UICONTROL Base Segment Name]** | Nom du segment qui apparaît dans la ligne des résultats du rapport. |
| **[!UICONTROL Overlapping Segment ID]** | ID numérique unique du segment sélectionné lors de l’exécution du rapport. Apparaît comme ID de colonne pour le segment. |
| **[!UICONTROL Overlapping Segment Name]** | Nom du segment sélectionné lors de l&#39;exécution du rapport. Apparaît dans la colonne des résultats du rapport. |
| **[!UICONTROL Base Segment Uniques]** | Nombre de visiteurs uniques dans votre segment de base. |
| **[!UICONTROL Base Segment Uniques]** | Nombre de visiteurs uniques dans votre segment qui se chevauchent. |
| **[!UICONTROL Overlapping Uniques]** | Nombre de visiteurs uniques partagés entre les segments comparés. |
| **[!UICONTROL Overlap %]** | Pour obtenir le pourcentage de chevauchement, l’Audience Manager utilise la formule suivante : Uniques en chevauchement / (Uniques de segments de base + Uniques de segments en chevauchement - Uniques en chevauchement) |



>[!MORELIKETHIS]
>
>* [Filtrage des résultats du rapport avec les curseurs de données](../../reporting/dynamic-reports/data-sliders.md)
>* [Formes, couleurs et tailles utilisées dans les rapports interactifs](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explication des icônes et outils du rapport](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapports de chevauchement : mise à jour des plannings et des tailles de segment minimum](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Échantillonnage de données et taux d’erreur dans les rapports Audience Manager sélectionnés...](../../reporting/report-sampling.md)
>* [Fichiers CSV pour les rapports de chevauchement](../../reporting/dynamic-reports/overlap-csv-files.md)