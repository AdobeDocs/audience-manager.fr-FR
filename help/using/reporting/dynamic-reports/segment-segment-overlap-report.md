---
description: Renvoie des données sur le nombre d’utilisateurs uniques partagés entre vos segments.
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: Rapport de chevauchement de segments à segments
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
TQID: https://experienceleague.adobe.com/0AE4fjrc4tuDVpIqdqtYbEcS2feeO4hdNwMFf6SVoVU
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 360
ht-degree: 6%

---

# Rapport de chevauchement de segments à segments{#segment-to-segment-overlap-report}

Renvoie des données sur le nombre d’utilisateurs uniques partagés entre vos segments.

>[!NOTE]
>
>Les rapports de chevauchement dans Audience Manager respectent les principes RBAC. Vous pouvez uniquement afficher les segments des sources de données auxquelles vous avez accès en fonction du [Groupe d’utilisateurs RBAC](/help/using/features/administration/administration-overview.md) auquel vous appartenez.

<!-- 

c_segment_segment_overlap.xml

 -->

## Présentation

Le rapport [!UICONTROL Segment-to-Segment Overlap] peut vous aider à :

* Identifier les segments avec un chevauchement élevé ou faible, selon vos besoins. Les caractéristiques avec un chevauchement élevé vous donnent une audience ciblée, mais moins de visiteurs uniques. Les caractéristiques avec un faible chevauchement peuvent s’avérer utiles pour atteindre un ensemble de visiteurs unique plus vaste.
* Recherchez les chevauchements inattendus et utilisez ces informations pour créer de nouveaux segments hautement performants.

## Exemple de rapport

L’illustration suivante présente de manière générale le rapport [!UICONTROL Segment-to-Segment Overlap].

>[!NOTE]
>
>Le rapport [!UICONTROL Segment-to-Segment Overlap] renvoie un champ vide lorsqu’il compare le même segment à lui-même.

![](assets/segment-to-segment-overlap.png)

## Accéder à des points de données individuels

Sélectionnez un point individuel pour afficher les détails des données dans une fenêtre pop-up. Les actions de clic mettent automatiquement à jour les données affichées dans le rapport.

## Champs de pop de données de chevauchement de segment à segment définis {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

La fenêtre contextuelle du rapport [!UICONTROL Segment-to-Segment Overlap] contient les mesures ci-dessous. Notez que la mesure uniques du tableau représente vos *utilisateurs en temps réel*.

| Mesure | Description |
|---|---|
| **[!UICONTROL Base Segment ID]** | Identifiant numérique unique du segment qui apparaît dans les résultats du rapport. S’affiche comme l’identifiant de ligne du segment. |
| **[!UICONTROL Base Segment Name]** | Nom du segment qui apparaît dans la ligne des résultats du rapport. |
| **[!UICONTROL Overlapping Segment ID]** | Identifiant numérique unique du segment sélectionné lors de l’exécution du rapport. S’affiche comme l’identifiant de la colonne pour le segment. |
| **[!UICONTROL Overlapping Segment Name]** | Nom du segment sélectionné lors de l’exécution du rapport. Apparaît dans la colonne des résultats du rapport. |
| **[!UICONTROL Base Segment Uniques]** | Nombre de visiteurs et visiteuses uniques dans votre segment de base. |
| **[!UICONTROL Base Segment Uniques]** | Nombre de visiteurs et visiteuses uniques dans votre segment qui se chevauche. |
| **[!UICONTROL Overlapping Uniques]** | Nombre de visiteurs et visiteuses uniques partagés entre les segments comparés. |
| **[!UICONTROL Overlap %]** | Pour obtenir le pourcentage de chevauchement, Audience Manager utilise la formule suivante : Unités de segment de base qui se chevauchent / (Unités de segment de base + Unités de segment qui se chevauchent - Unités qui se chevauchent) |



>[!MORELIKETHIS]
>
>* [Filtrage des résultats du rapport avec les curseurs de données](../../reporting/dynamic-reports/data-sliders.md)
>* [Formes, couleurs et tailles utilisées dans les rapports interactifs](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* Présentation des icônes et des outils de rapport [&#128279;](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Rapports de chevauchement : mise à jour des plannings et des tailles de segment minimum](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Échantillonnage des données et taux d’erreur dans certains rapports Audience Manager...](../../reporting/report-sampling.md)
>* [Fichiers CSV pour les rapports de chevauchement](../../reporting/dynamic-reports/overlap-csv-files.md)
