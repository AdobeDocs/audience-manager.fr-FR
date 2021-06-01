---
description: Incidence de l’intervalle TTL (trait time-to-live) sur l’appartenance au segment.
seo-description: Incidence de l’intervalle TTL (trait time-to-live) sur l’appartenance au segment.
seo-title: Explication de la durée de vie des segments et des caractéristiques
solution: Audience Manager
title: Explication de la durée de vie des segments
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: 'Caractéristiques '
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---

# Explication de la durée de vie des segments et des caractéristiques {#segment-time-to-live-explained}

L’intervalle de caractéristiques [!UICONTROL time-to-live] ([!DNL TTL]) affecte l’appartenance au segment.

<!-- segment-ttl-explained.xml -->

## Durée de vie

[!DNL TTL] définit la durée pendant laquelle un visiteur du site reste dans un segment après le dernier événement de qualification de caractéristique. [!DNL TTL] est définie sur les caractéristiques et non sur les segments. Les visiteurs ne sont pas inclus dans un segment s’ils ne remplissent pas les critères d’une caractéristique avant la fin de l’intervalle [!DNL TTL]. La valeur par défaut [!DNL TTL] pour les nouvelles caractéristiques est de 120 jours. Lorsqu’elle est définie sur 0 jour, la caractéristique n’expire jamais. [Définissez la ](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) valeur TTL lorsque vous créez ou modifiez une caractéristique dans la  [!UICONTROL Advanced Options] section de l’interface de création de caractéristiques.

### Explication de la durée de vie 1 jour

Lorsque vous définissez la valeur [!DNL TTL] sur 1 jour, le minuteur TTL commence le lendemain de la réalisation de la caractéristique, sans compter les heures restantes dans le jour de la réalisation de la caractéristique.

Audience Manager calcule [!DNL TTL] l’expiration des caractéristiques avec un jour [!DNL TTL] en fonction de la formule suivante :

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Exemple 1** : Caractéristique réalisée à 1:00  [!DNL UTC], avec une journée  [!DNL TTL]. [!DNL TTL] expirera 24 + 24 - 1 = 47 heures plus tard.
* **Exemple 2** : Caractéristique réalisée à 23h00  [!DNL UTC], avec une journée  [!DNL TTL]. [!DNL TTL] expirera 24 + 24 - 23 = 25 heures plus tard.

## [!DNL TTL] et abandon d’un segment

Un utilisateur sort d’un segment s’il ne remplit aucune de ses caractéristiques dans l’intervalle [!DNL TTL]. Par exemple, si vous disposez d’un segment à 1 caractéristique avec un délai de 30 jours [!DNL TTL], l’utilisateur abandonnera ce segment s’il ne remplit pas les critères de la caractéristique dans les 30 prochains jours.

![](assets/ttl-explained.png)

## [!DNL TTL] Renouvellement des segments

[!DNL TTL] est réinitialisé et l’utilisateur reste dans un segment, s’il remplit les conditions requises pour la caractéristique de ce segment au cours de la période [!DNL TTL]. En outre, comme la plupart des segments contiennent plusieurs caractéristiques ayant leurs propres [!DNL TTL] intervalles, un utilisateur peut rester dans un segment et réinitialiser l’intervalle [!DNL TTL], tant qu’il reste admissible pour toutes les caractéristiques associées au segment.

Par exemple, supposons que vous ayez le segment 1 composé de la caractéristique A (30 jours [!DNL TTL]) et de la caractéristique B (15 jours [!DNL TTL]). En supposant qu’un visiteur ne soit admissible pour chaque caractéristique qu’une seule fois, l’illustration ci-dessous décrit le processus de renouvellement [!DNL TTL] et la durée totale du segment.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] Les TTL sont indépendants des paramètres TTL tiers

N’oubliez pas que la valeur [!DNL TTL] définie sur votre pixel [!DNL Audience Manager] fonctionne indépendamment de la valeur [!DNL TTL] définie sur d’autres pixels utilisés par des tiers ([!DNL DSP]s, réseaux publicitaires, etc.).

>[!MORELIKETHIS]
>
>* [Définition d’un intervalle d’expiration de caractéristique](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

