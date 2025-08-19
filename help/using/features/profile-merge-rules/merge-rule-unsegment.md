---
description: L’annulation de segmentation décrit les processus qui disqualifient et suppriment les profils d’appareils des segments. Votre capacité à supprimer un profil d’appareil d’un segment dépend de l’option d’appareil utilisée pour créer une règle de fusion de profils.
seo-description: Unsegmentation describes processes that disqualify and remove device profiles from segments. Your ability to remove a device profile from a segment depends on the device option used to create a Profile Merge Rule.
seo-title: Profile Merge Rules and Device Un-Segmentation Processes
solution: Audience Manager
title: Règles de fusion de profils et processus d’annulation de segmentation d’appareils
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# Règles de fusion de profils et processus d’annulation de segmentation d’appareils {#profile-merge-rules-and-device-un-segmentation-processes}

L’annulation de segmentation décrit les processus qui disqualifient et suppriment les profils d’appareils des segments. Votre capacité à supprimer un profil d’appareil d’un segment dépend de l’option d’appareil utilisée pour créer un [!UICONTROL Profile Merge Rule].

## Options d’appareil disponibles {#device-options}

Pour rappel, les [!UICONTROL Device Options] sont disponibles dans la section [!UICONTROL Profile Merge Rules Setup] lorsque vous créez ou modifiez un [!UICONTROL Profile Merge Rule].

## Option de profil d’appareil actuelle et annulation de la segmentation de l’appareil {#current-device-profile-options}

**[!UICONTROL Device Profile]** est l’option de profil d’appareil par défaut pour un [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] pouvez supprimer un profil d’appareil d’un segment lorsque votre [!UICONTROL Profile Merge Rule] utilise l’option **[!UICONTROL Device Profile]**. Dans ces conditions, l’annulation de la segmentation se produit lorsque :

* Le profil de l’appareil est inactif depuis 120 jours. Un processus de nettoyage de données hebdomadaire supprime les profils d’appareils inactifs de vos segments.
* L’appareil n’est plus éligible à un segment car les mises à jour ou les modifications apportées au profil de l’appareil le disqualifient. Cela se produit lorsque les critères de qualification du segment changent, ou que vous appliquez un opérateur [!DNL AND NOT] à une règle de segment, ou que vous spécifiez des conditions [récence et fréquence](../segments/recency-and-frequency.md) qui utilisent les paramètres inférieur/égal à . Les cas d’utilisation sont décrits dans la documentation [Suppression instantanée sur plusieurs appareils](instant-cross-device-suppression.md).

![périphérique uniquement](assets/device-only.png)

## Aucune option d’appareil et annulation de segmentation d’appareil {#no-device-option}

[!DNL Audience Manager] pouvez supprimer un identifiant sur plusieurs appareils d’un segment lorsque votre [!UICONTROL Profile Merge Rule] utilise l’option **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]**. Dans ces conditions, l’annulation de la segmentation se produit lorsque l’identifiant sur l’ensemble des appareils n’est plus qualifié pour un segment, car les mises à jour ou les modifications apportées au profil sur l’ensemble des appareils le disqualifient. Cela se produit lorsque les critères de qualification du segment changent, ou que vous appliquez un opérateur [!UICONTROL AND NOT] à une règle de segment, ou que vous spécifiez des conditions [récence et fréquence](../segments/recency-and-frequency.md) qui utilisent les paramètres inférieur/égal à . Les cas d’utilisation sont décrits dans la documentation [Suppression instantanée sur plusieurs appareils](instant-cross-device-suppression.md).

![](assets/current-no-device.png)

## Options du graphique des appareils et annulation de la segmentation des appareils {#device-graph-options-unsegmentation}

[!DNL Audience Manager] pouvez supprimer plusieurs profils d’appareil d’un segment lorsque votre [!UICONTROL Profile Merge Rule] utilise une option de graphique d’appareil. L’annulation de la segmentation se produit lorsque le profil fusionné de l’appareil dans le graphique d’appareil n’est plus qualifié pour le segment, car les mises à jour ou les modifications apportées à ce profil fusionné le disqualifient du segment. Cela se produit lorsque les critères de qualification du segment changent, ou que vous appliquez un opérateur [!UICONTROL AND NOT] à une règle de segment, ou que vous spécifiez des conditions [récence et fréquence](../segments/recency-and-frequency.md) qui utilisent les paramètres inférieur/égal à . Les cas d’utilisation sont décrits dans la documentation [Suppression instantanée sur plusieurs appareils](instant-cross-device-suppression.md).

>[!NOTE]
>
>**limite de 100 appareils pour l’évaluation et la disqualification des segments**.
>&#x200B;>Audience Manager fusionne jusqu’à 100 appareils lors de l’évaluation de segments avec une règle de fusion de profil qui utilise un graphique d’appareil. Audience Manager évalue l’appareil actuel et jusqu’à 99 appareils liés à l’appareil actuel par un [profil authentifié](../../reference/visitor-authentication-states.md) (identifiant sur l’ensemble des appareils). Si le signal unsegment est émis, l’appareil actuel et les appareils supplémentaires sont supprimés du segment dans la destination.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [FAQ sur les stratégies de fusion de profils et la représentation graphique des appareils](../../faq/faq-profile-merge.md)
>* [Suppression instantanée multi-appareils](instant-cross-device-suppression.md)
