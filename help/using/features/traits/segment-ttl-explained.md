---
description: Incidence de l’intervalle TTL (trait time-to-live) sur l’appartenance au segment.
seo-description: Incidence de l’intervalle TTL (trait time-to-live) sur l’appartenance au segment.
seo-title: Explication du temps de segment et de caractéristique à vivre
solution: Audience Manager
title: Explication de la durée de vie du segment
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 0%

---


# Explication du temps de vie des segments et des caractéristiques {#segment-time-to-live-explained}

Comment l’intervalle de caractéristiques [!UICONTROL time-to-live] ([!DNL TTL]) affecte l’appartenance au segment.

<!-- segment-ttl-explained.xml -->

## Temps de vie

[!DNL TTL] définit la durée pendant laquelle un visiteur de site reste dans un segment après le dernier événement de qualification des caractéristiques. [!DNL TTL] est définie sur les caractéristiques et non sur les segments. Les Visiteurs abandonnent un segment s’ils ne remplissent pas les critères d’une caractéristique avant la fin de l’ [!DNL TTL] intervalle. La valeur par défaut [!DNL TTL] pour les nouvelles caractéristiques est de 120 jours. Lorsqu’elle est définie sur 0 jour, la caractéristique n’expire jamais. [Définissez la valeur](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) TTL lorsque vous créez ou modifiez une caractéristique dans la [!UICONTROL Advanced Options] section de l’interface de création de caractéristiques.

### Explication de TTL sur 1 jour

Lorsque vous définissez la valeur [!DNL TTL] sur 1 jour, le minuteur TTL début le lendemain de la prise en compte de la caractéristique, sans compter les heures restantes dans le jour de la prise en compte de la caractéristique.

L’Audience Manager calcule l’ [!DNL TTL] expiration pour les caractéristiques avec 1 jour [!DNL TTL] en fonction de la formule suivante :

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Exemple 1**: Caractéristique réalisée à 1h00 [!DNL UTC], avec une journée [!DNL TTL]. [!DNL TTL] expirera 24 + 24 - 1 = 47 heures plus tard.
* **Exemple 2**: Caractéristique réalisée à 23h00 [!DNL UTC], avec une journée [!DNL TTL]. [!DNL TTL] expirera 24 + 24 - 23 = 25 heures plus tard.

## [!DNL TTL] et abandonner un segment

Un utilisateur sort d’un segment s’il ne remplit aucune de ses caractéristiques dans l’ [!DNL TTL] intervalle. Par exemple, si vous disposez d’un segment à 1 caractéristique avec 30 jours [!DNL TTL], l’utilisateur abandonnera ce segment s’il ne remplit pas les critères pour la caractéristique dans les 30 prochains jours.

![](assets/ttl-explained.png)

## [!DNL TTL] et renouvellement des segments

Les [!DNL TTL] réinitialisations et l’utilisateur reste dans un segment, s’ils répondent aux critères de ce segment au cours de la [!DNL TTL] période. En outre, comme la plupart des segments contiennent plusieurs caractéristiques avec leurs propres [!DNL TTL] intervalles, un utilisateur peut rester dans un segment et réinitialiser l’ [!DNL TTL] intervalle, tant qu’il continue à se qualifier pour les caractéristiques associées au segment.

Supposons, par exemple, que vous ayez le segment 1 composé de la caractéristique A (30 jours [!DNL TTL]) et de la caractéristique B (15 jours [!DNL TTL]). En supposant qu’un visiteur ne soit admissible pour chaque caractéristique qu’une seule fois, l’illustration ci-dessous décrit le processus de [!DNL TTL] renouvellement et la durée totale du segment.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] Les TTL sont indépendants des paramètres TTL tiers

N’oubliez pas que la [!DNL TTL] visionneuse de votre [!DNL Audience Manager] pixel fonctionne indépendamment de la [!DNL TTL] visionneuse des autres pixels utilisés par des tiers ([!DNL DSP]s, réseaux publicitaires, etc.).

>[!MORELIKETHIS]
>
>* [Définir un intervalle d&#39;expiration de caractéristique](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

