---
description: Evitez d’utiliser des règles de fusion de profils avec un graphique de périphérique pour les segments qui ne sont pas très peuplés, voire pas du tout, en temps réel.
seo-description: Evitez d’utiliser des règles de fusion de profils avec un graphique de périphérique pour les segments qui ne sont pas très peuplés, voire pas du tout, en temps réel.
seo-title: Remarques importantes concernant les règles de fusion de profils avec des graphiques de périphériques
title: Remarques importantes concernant les règles de fusion de profils avec des graphiques de périphériques
uuid: 93cd8861-210d-4c52-9cb7-6f2dd7dc018a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Remarques importantes concernant les règles de fusion de profils avec des graphiques de périphériques {#important-considerations-for-profile-merge-rules-with-device-graphs}

Evitez d’utiliser [!UICONTROL Profile Merge Rules] une variable [!UICONTROL Device Graph] pour les segments dont la population de segments est faible, voire nulle, en temps réel.

>[!IMPORTANT]
>
>Si la configuration [!UICONTROL Profile Merge Rule] est incorrecte, la population de segments exportée vers des destinations par lot peut être nettement inférieure à ce qui était prévu.

Les segments qui utilisent une règle de fusion de [profil avec un graphique](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) de périphérique sont uniquement évalués par rapport aux périphériques affichés en temps réel sur les serveurs [Edge d’](../../reference/system-components/components-edge.md) Audience Manager une fois le segment créé.

N’oubliez pas que l’une des options de périphérique suivantes est sélectionnée dans une [!UICONTROL Profile Merge Rule] option avec un [!UICONTROL Device Graph] .

![](assets/pmr-considerations-1.png)

Les périphériques qui répondent aux critères d’un segment en temps réel sont mesurés par la population [en temps réel du](../../features/segments/segment-builder-data.md#segment-populations)segment.

![](assets/pmr-considerations-2.png)

Une faible population de segments en temps réel signifie que très peu de périphériques correspondant au segment sont affichés en temps réel. Pour de meilleures performances, les segments avec peu ou pas de population en temps réel doivent utiliser un [!UICONTROL Profile Merge Rule] ensemble pour évaluer le *[!UICONTROL Current Device]*, comme dans l’image ci-dessous.

![](assets/pmr-considerations-3.png)

La définition [!UICONTROL Profile Merge Rule] de pour évaluer le *[!UICONTROL Current Device]* permet de s’assurer que tous les périphériques (et pas seulement ceux affichés en temps réel) sont évalués pour le segment. Tous les périphériques correspondant au segment sont définis par la population totale de segments, comme illustré ci-dessous.

![](assets/pmr-considerations-4.png)