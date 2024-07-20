---
description: Renvoie des données sur le nombre d’utilisateurs uniques partagés entre vos segments.
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: Rapport de chevauchement de segments
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 6%

---

# Rapport de chevauchement de segments{#segment-to-segment-overlap-report}

Renvoie des données sur le nombre d’utilisateurs uniques partagés entre vos segments.

>[!NOTE]
>
>Les rapports de chevauchement d’Audience Manager respectent les principes du reporting RBAC. Vous ne pouvez afficher que les segments provenant des sources de données auxquelles vous avez accès en fonction du [groupe d’utilisateurs RBAC](/help/using/features/administration/administration-overview.md) auquel vous appartenez.

<!-- 

c_segment_segment_overlap.xml

 -->

## Présentation

Le rapport [!UICONTROL Segment-to-Segment Overlap] peut vous aider à :

* Identifiez les segments présentant un chevauchement élevé ou faible, en fonction de vos besoins. Les caractéristiques avec un chevauchement élevé vous donnent une audience ciblée, mais moins de visiteurs uniques. Les caractéristiques présentant un faible chevauchement peuvent s’avérer utiles pour atteindre un ensemble de visiteurs plus grand et unique.
* Recherchez les chevauchements inattendus et utilisez ces informations pour créer de nouveaux segments hautement performants.

## Exemple de rapport

L’illustration suivante présente un aperçu général du rapport [!UICONTROL Segment-to-Segment Overlap].

>[!NOTE]
>
>Le rapport [!UICONTROL Segment-to-Segment Overlap] renvoie un champ vide lorsqu’il compare le même segment à lui-même.

![](assets/segment-to-segment-overlap.png)

## Exploration des points de données individuels

Sélectionnez un point individuel pour afficher les détails des données dans une fenêtre contextuelle. Les actions de clic mettent automatiquement à jour les données affichées dans le rapport.

## Définition des champs de pop de données de chevauchement de segments {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

La fenêtre contextuelle du rapport [!UICONTROL Segment-to-Segment Overlap] contient les mesures ci-dessous. Notez que la mesure uniques dans le tableau représente vos *utilisateurs en temps réel*.

| Mesure | Description |
|---|---|
| **[!UICONTROL Base Segment ID]** | Identifiant numérique unique du segment qui apparaît dans les résultats du rapport. S’affiche comme identifiant de ligne pour le segment. |
| **[!UICONTROL Base Segment Name]** | Nom du segment qui apparaît dans la ligne des résultats du rapport. |
| **[!UICONTROL Overlapping Segment ID]** | Identifiant numérique unique du segment sélectionné lors de l’exécution du rapport. S’affiche comme ID de colonne pour le segment. |
| **[!UICONTROL Overlapping Segment Name]** | Nom du segment sélectionné lors de l’exécution du rapport. S’affiche dans la colonne des résultats du rapport. |
| **[!UICONTROL Base Segment Uniques]** | Le nombre de visiteurs uniques dans votre segment de base. |
| **[!UICONTROL Base Segment Uniques]** | Nombre de visiteurs uniques dans votre segment qui chevauche. |
| **[!UICONTROL Overlapping Uniques]** | Nombre de visiteurs uniques partagés entre les segments comparés. |
| **[!UICONTROL Overlap %]** | Pour obtenir le % de chevauchement, l’Audience Manager utilise la formule suivante : Chevauchement des uniques / (Uniques de segments de base + Uniques de segments qui se chevauchent - Uniques qui se chevauchent) |



>[!MORELIKETHIS]
>
>* [Filtrage des résultats du rapport avec les curseurs de données](../../reporting/dynamic-reports/data-sliders.md)
>* [Formes, couleurs et tailles utilisées dans les rapports interactifs](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Explication des icônes et outils de rapport](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapports de chevauchement : mise à jour des plannings et des tailles de segment minimum](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [ Échantillonnage de données et taux d’erreur dans les rapports d’Audience Manager sélectionnés...](../../reporting/report-sampling.md)
>* [Fichiers CSV pour les rapports de chevauchement](../../reporting/dynamic-reports/overlap-csv-files.md)
