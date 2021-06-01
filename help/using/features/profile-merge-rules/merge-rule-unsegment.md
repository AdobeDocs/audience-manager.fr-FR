---
description: La suppression de la segmentation décrit les processus qui excluent et suppriment les profils d’appareil des segments. Votre capacité à supprimer un profil d’appareil d’un segment dépend de l’option d’appareil utilisée pour créer une règle de fusion de profils.
seo-description: La suppression de la segmentation décrit les processus qui excluent et suppriment les profils d’appareil des segments. Votre capacité à supprimer un profil d’appareil d’un segment dépend de l’option d’appareil utilisée pour créer une règle de fusion de profils.
seo-title: Stratégies de fusion de profils et processus de suppression de la segmentation des appareils
solution: Audience Manager
title: Stratégies de fusion de profils et processus de suppression de la segmentation des appareils
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Fusion des profils
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 6%

---

# Stratégies de fusion de profils et processus de suppression de la segmentation des appareils {#profile-merge-rules-and-device-un-segmentation-processes}

La suppression de la segmentation décrit les processus qui excluent et suppriment les profils d’appareil des segments. Votre capacité à supprimer un profil d’appareil d’un segment dépend de l’option d’appareil utilisée pour créer un [!UICONTROL Profile Merge Rule].

## Options de périphérique disponibles {#device-options}

Pour rappel, les [!UICONTROL Device Options] sont disponibles dans la section [!UICONTROL Profile Merge Rules Setup] lorsque vous créez ou modifiez une [!UICONTROL Profile Merge Rule].

## Option de profil de périphérique actuelle et suppression de périphérique {#current-device-profile-options}

**[!UICONTROL Device Profile]** est l’option de profil de périphérique par défaut pour un  [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] Vous pouvez supprimer un profil d’appareil d’un segment lorsque vous  [!UICONTROL Profile Merge Rule] utilisez l’ **[!UICONTROL Device Profile]** option . Dans ces conditions, la suppression de la segmentation se produit dans les cas suivants :

* Le profil de l’appareil est inactif depuis 120 jours. Un processus de nettoyage des données hebdomadaire supprime les profils d’appareil inactifs de vos segments.
* L’appareil n’est plus admissible pour un segment, car les mises à jour ou les modifications apportées au profil de l’appareil le disqualifient. Cela se produit lorsque les critères de qualification du segment changent, ou lorsque vous appliquez un opérateur [!DNL AND NOT] à une règle de segment, ou lorsque vous spécifiez des conditions [récence et fréquence](../segments/recency-and-frequency.md) qui utilisent les paramètres inférieur/égal à. Les cas d’utilisation sont décrits dans la documentation [Suppression instantanée entre appareils](instant-cross-device-suppression.md) .

![appareil uniquement](assets/device-only.png)

## Aucune option d’appareil et suppression de l’appareil {#no-device-option}

[!DNL Audience Manager] Vous pouvez supprimer un identifiant multi-appareils d’un segment lorsque vous  [!UICONTROL Profile Merge Rule] utilisez l’ **[!UICONTROL Current Authenticated Profiles]** option  **[!UICONTROL No Device Profile]** +. Dans ces conditions, la suppression de la segmentation se produit lorsque l’identifiant multi-appareils n’est plus admissible pour un segment, car les mises à jour ou les modifications apportées au profil multi-appareils le rendent non admissible. Cela se produit lorsque les critères de qualification du segment changent, ou lorsque vous appliquez un opérateur [!UICONTROL AND NOT] à une règle de segment, ou lorsque vous spécifiez des conditions [récence et fréquence](../segments/recency-and-frequency.md) qui utilisent les paramètres inférieur/égal à. Les cas d’utilisation sont décrits dans la documentation [Suppression instantanée entre appareils](instant-cross-device-suppression.md) .

![](assets/current-no-device.png)

## Options de Device Graph et suppression de la segmentation des appareils {#device-graph-options-unsegmentation}

[!DNL Audience Manager] Vous pouvez supprimer plusieurs profils d’appareil d’un segment lorsque vous  [!UICONTROL Profile Merge Rule] utilisez une option de représentation graphique des appareils. La suppression de la segmentation se produit lorsque le profil fusionné de l’appareil n’est plus admissible pour le segment car les mises à jour ou les modifications apportées à ce profil fusionné le rendent inadmissible du segment. Cela se produit lorsque les critères de qualification du segment changent, ou lorsque vous appliquez un opérateur [!UICONTROL AND NOT] à une règle de segment, ou lorsque vous spécifiez des conditions [récence et fréquence](../segments/recency-and-frequency.md) qui utilisent les paramètres inférieur/égal à. Les cas d’utilisation sont décrits dans la documentation [Suppression instantanée entre appareils](instant-cross-device-suppression.md) .

>[!NOTE]
>
>**100 appareils pour l’évaluation et la disqualification des segments**.
>Audience Manager fusionne jusqu’à 100 appareils lors de l’évaluation de segments avec une règle de fusion de profils qui utilise une représentation graphique des appareils. Audience Manager évalue l’appareil actuel et jusqu’à 99 appareils liés à l’appareil actuel par un [profil authentifié](../../reference/visitor-authentication-states.md) (identifiant multi-appareils). Si le signal de suppression de la segmentation est émis, l’appareil actuel et les appareils supplémentaires seront supprimés du segment dans la destination.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [FAQ sur les stratégies de fusion de profils et la représentation graphique des appareils](../../faq/faq-profile-merge.md)
* [Suppression instantanée multi-appareils](instant-cross-device-suppression.md)

