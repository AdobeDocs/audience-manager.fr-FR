---
description: L’intervalle TTL (trait time-to-live) affecte l’appartenance au segment.
seo-description: L’intervalle TTL (trait time-to-live) affecte l’appartenance au segment.
seo-title: Segment et temps de décompte jusqu’à l’heure de diffusion
solution: Audience Manager
title: Segment Durée de vie expliqué
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
translation-type: tm+mt
source-git-commit: 7e9aada98fe9c18c6fc484255b3c9ff33dc59324

---


# Segment et temps de publication des caractéristiques {#segment-time-to-live-explained}

Comment l’intervalle [!UICONTROL time-to-live] ([!DNL TTL]) de caractéristiques affecte l’appartenance au segment.

<!-- segment-ttl-explained.xml -->

## Temps de vivre

[!DNL TTL] définit la durée pendant laquelle un visiteur du site reste dans un segment après le dernier événement de qualification de caractéristique. [!DNL TTL] est définie sur les caractéristiques et non sur les segments. Les visiteurs sortent d’un segment s’ils ne voient pas une caractéristique qualifiante avant la fin de l’ [!DNL TTL] intervalle. La valeur par défaut [!DNL TTL] des nouvelles caractéristiques est de 120 jours. Lorsqu’il est défini sur 0 jour, le trait n’expire jamais. [Définissez la valeur](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) TTL lorsque vous créez ou modifiez une caractéristique dans la [!UICONTROL Advanced Options] section de l’interface de création de caractéristiques.

## [!DNL TTL] et abandonner un segment

Un utilisateur sort d’un segment s’il ne voit aucune de ses caractéristiques dans l’ [!DNL TTL] intervalle. Si, par exemple, vous disposez d’un segment à 1 caractéristique avec 30 jours [!DNL TTL], l’utilisateur abandonne ce segment s’il n’en voit plus la caractéristique dans les 30 jours.

![](assets/ttl_1.png)

## [!DNL TTL] et renouvellement des segments

Les [!DNL TTL] réinitialisations et l’utilisateur reste dans un segment s’il en voit la caractéristique au cours de la [!DNL TTL] période. En outre, comme la plupart des segments contiennent plusieurs caractéristiques avec leurs propres [!DNL TTL] périodes, un utilisateur peut rester dans un segment (et réinitialiser l’ [!DNL TTL] intervalle) tant qu’il continue à voir les caractéristiques associées à un segment. Supposons, par exemple, que vous ayez le segment 1 composé du Caractéristique A (30 jours [!DNL TTL]) et du Caractéristique B (15 jours [!DNL TTL]). En supposant que l’utilisateur ne voit chaque caractéristique qu’une seule fois, l’illustration ci-dessous décrit le processus de [!DNL TTL] renouvellement et la durée totale du segment.

![](assets/ttl_2.png)

## [!DNL Audience Manager] Les TTL sont indépendants des paramètres TTL tiers

N’oubliez pas que la [!DNL TTL] visionneuse de votre [!DNL Audience Manager] pixel fonctionne indépendamment de la [!DNL TTL] visionneuse des autres pixels utilisés par des tiers ([!DNL DSP]s, réseaux publicitaires, etc.).

>[!MORE_LIKE_This]
>
>* [Définir un intervalle d’expiration des caractéristiques](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

