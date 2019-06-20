---
description: Evitez d'utiliser des règles de fusion de profils avec un graphique de périphérique pour les segments qui présentent peu de population de segments en temps réel.
seo-description: Evitez d'utiliser des règles de fusion de profils avec un graphique de périphérique pour les segments qui présentent peu de population de segments en temps réel.
seo-title: Remarques importantes concernant les règles de fusion de profils avec des graphiques de périphérique
title: Remarques importantes concernant les règles de fusion de profils avec des graphiques de périphérique
uuid: 93 cd 8861-210 d -4 c 52-9 cb 7-6 f 2 dd 7 dc 018 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Important Considerations for Profile Merge Rules with Device Graphs {#important-considerations-for-profile-merge-rules-with-device-graphs}

Avoid using [!UICONTROL Profile Merge Rules] with a [!UICONTROL Device Graph] for segments which have little to no real-time segment population.

>[!IMPORTANT]
>
>If the [!UICONTROL Profile Merge Rule] is configured incorrectly, the segment population exported to batch destinations may be significantly lower than expected.

Segments using a [Profile Merge Rule with a Device Graph](../../features/profile-merge-rules/merge-rule-targeting-options.md#device-graph-options) are only evaluated against devices seen in real-time on [Audience Manager’s Edge Servers](../../reference/system-components/components-edge.md) after the segment has been created.

Remember, a [!UICONTROL Profile Merge Rule] with a [!UICONTROL Device Graph] has one of the following device options selected, as shown below.

![](assets/pmr-considerations-1.png)

Devices that qualify for a segment in real-time are measured by the [segment’s real-time population](../../features/segments/segment-builder-data.md#segment-populations).

![](assets/pmr-considerations-2.png)

Une faible population de segments en temps réel signifie que très peu de périphériques qualifiant pour le segment sont visibles en temps réel. For best performance, segments with little to no real-time population should use a [!UICONTROL Profile Merge Rule] set to evaluate the *[!UICONTROL Current Device]*, like in the image below.

![](assets/pmr-considerations-3.png)

Setting the [!UICONTROL Profile Merge Rule] to evaluate the *[!UICONTROL Current Device]* ensures that all devices (not just those seen in real-time) are evaluated for the segment. Tous les périphériques qualifiant pour le segment sont définis par la population totale de segments, comme illustré ci-dessous.

![](assets/pmr-considerations-4.png)