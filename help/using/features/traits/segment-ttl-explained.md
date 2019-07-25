---
description: Incidence de l'intervalle de temps à Live (TTL) sur l'appartenance au segment.
seo-description: Incidence de l'intervalle de temps à Live (TTL) sur l'appartenance au segment.
seo-title: Durée de segment et durée de la caractéristique expliquée
solution: Audience Manager
title: Temps de segmentation pour l'explication de la durée
uuid: 5 b 2 c 6911-50 b 9-4 b 68-9 dd 4-21128 d 112 eab
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# Segment and Trait Time-to-Live Explained {#segment-time-to-live-explained}

How trait [!UICONTROL time-to-live] ([!DNL TTL]) interval affects segment membership.

<!-- segment-ttl-explained.xml -->

## Durée de vie

[!DNL TTL] définit la durée pendant laquelle un visiteur du site reste dans un segment après l'événement de qualification de dernière caractéristique. [!DNL TTL] est définie sur des caractéristiques et non sur des segments. Visitors fall out of a segment if they do not see a qualifying trait before the end of the [!DNL TTL] interval. The default [!DNL TTL] for new traits is 120 days. Lorsqu'elle est définie sur 0 jour, la caractéristique n'expire jamais. [Définissez la valeur TTL](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) lorsque vous créez ou modifiez une caractéristique dans la [!UICONTROL Advanced Options] section de l'interface de création de la caractéristique.

## [!DNL TTL] et abandon d'un segment

A user falls out of a segment if they do not see any of its traits within the [!DNL TTL] interval. For example, if you have a 1-trait segment with a 30 days [!DNL TTL], the user will drop out of that segment if they do not see the trait again within the 30 days.

![](assets/ttl_1.png)

## [!DNL TTL] et renouvellement de segment

[!DNL TTL] Les réinitialisations et l'utilisateur restent dans un segment s'ils voient la caractéristique du segment dans [!DNL TTL] la période. Also, because most segments contain multiple traits with their own [!DNL TTL] periods, a user can remain in a segment (and reset the [!DNL TTL] interval) as long as they keep seeing any traits associated with a segment. For example, say you have Segment 1 composed of Trait A (30 day [!DNL TTL]) and Trait B (15 day [!DNL TTL]). Assuming the user sees each trait only once, the illustration below outlines the [!DNL TTL] renewal process and total in-segment duration.

![](assets/ttl_2.png)

## [!DNL Audience Manager] TTL est indépendant des paramètres TTL tiers

Remember, the [!DNL TTL] set on your [!DNL Audience Manager] pixel operates independently from the [!DNL TTL] set on other pixels used by third parties ([!DNL DSP]s, ad networks, etc.).

>[!MORE_ LIKE_ THIS]
>
>* [Définition d'un intervalle d'expiration de caractéristique](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

