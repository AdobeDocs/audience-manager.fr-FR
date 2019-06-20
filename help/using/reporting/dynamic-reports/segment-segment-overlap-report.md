---
description: Renvoie des données sur le nombre d'utilisateurs uniques partagés entre vos segments.
seo-description: Renvoie des données sur le nombre d'utilisateurs uniques partagés entre vos segments.
seo-title: Rapport de chevauchement de segments
solution: Audience Manager
title: Rapport de chevauchement de segments
uuid: 0339 eb 6 c -6355-44 a 3-9 c 46-f 159485449 d 1
translation-type: tm+mt
source-git-commit: 339d5550b22949862415d2abc812217e5479c993

---


# Rapport de chevauchement de segments{#segment-to-segment-overlap-report}

Renvoie des données sur le nombre d&#39;utilisateurs uniques partagés entre vos segments.

>[!NOTE]
>
>Les rapports de chevauchement dans Audience Manager respectent les principes RBAC. You can only see segments from data sources that you have access to based on the [RBAC User Group](/help/using/features/administration/administration-overview.md) that you belong to.

<!-- 

c_segment_segment_overlap.xml

 -->

## Aperçu

The [!UICONTROL Segment-to-Segment Overlap] report can help you:

* Identifiez les segments présentant un chevauchement élevé ou élevé en fonction de vos besoins. Les caractéristiques présentant un chevauchement élevé vous donnent une audience ciblée, mais moins de visiteurs uniques. Les caractéristiques présentant un chevauchement faible peuvent s&#39;avérer utiles pour atteindre un jeu de visiteurs unique plus large.
* Recherchez un chevauchement inattendu et utilisez ces informations pour créer de nouveaux segments hautes performances.

## Exemple de rapport

The following illustration provides a high-level overview of the [!UICONTROL Segment-to-Segment Overlap] report.

>[!NOTE]
>
>The [!UICONTROL Segment-to-Segment Overlap] report returns an empty field when it compares the same segment to itself.

![](assets/segment-to-segment-overlap.png)

## Exploration des points de données individuels

Sélectionnez un point individuel pour afficher les détails des données dans une fenêtre contextuelle. Les actions de clic mettent automatiquement à jour les données affichées dans le rapport.

## Segment-to-Segment Overlap Data Pop Fields Defined {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

The popup for the [!UICONTROL Segment-to-Segment Overlap] report contains the metrics below. Note that the uniques metric in the table represents your *real-time users*.

| Mesure | Description |
|---|---|
| **[!UICONTROL Segment ID1]** | Identifiant numérique unique du segment qui apparaît dans les résultats du rapport. Apparaît comme identifiant de ligne du segment. |
| **[!UICONTROL Segment ID2]** | Identifiant numérique unique du segment sélectionné lors de l&#39;exécution du rapport. Apparaît comme ID de colonne du segment. |
| **[!UICONTROL Segment Name1]** | Nom du segment qui apparaît dans la ligne des résultats du rapport. |
| **[!UICONTROL Segment Name2]** | Nom du segment que vous sélectionnez lors de l&#39;exécution du rapport. Apparaît dans la colonne des résultats du rapport. |
| **[!UICONTROL Overlap %]** | Pour obtenir le chevauchement %, Audience Manager utilise la formule suivante : Chevauchement des valeurs uniques/(segment de base + chevauchement des segments - uniques se chevauchant) |
| **[!UICONTROL Overlap Uniques]** | Nombre de visiteurs uniques partagés entre les segments comparés. |
| **[!UICONTROL Segment Uniques1]** | Nombre de visiteurs uniques dans le segment 1. |
| **[!UICONTROL Segment Uniques2]** | Nombre de visiteurs uniques dans le segment 2. |

>[!MORE_ LIKE_ THIS]
>
>* [Filtrage des résultats du rapport avec les curseurs de données](../../reporting/dynamic-reports/data-sliders.md)
>* [Formes, couleurs et tailles utilisées dans les rapports interactifs](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Icônes de rapport et outils expliqués](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapports de chevauchement : Mettre à jour la planification et la taille minimale du segment](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Taux d&#39;échantillonnage des données et taux d&#39;erreur dans les rapports Audience Manager sélectionnés…](../../reporting/report-sampling.md)
>* [Fichiers CSV pour les rapports de chevauchement](../../reporting/dynamic-reports/overlap-csv-files.md)