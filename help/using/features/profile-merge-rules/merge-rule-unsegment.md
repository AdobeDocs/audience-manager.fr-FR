---
description: La section Unsegmentation décrit les processus qui excluent et suppriment les profils de périphériques des segments. La suppression d’un profil de périphérique d’un segment dépend de l’option de périphérique utilisée pour créer une règle de fusion de profil.
seo-description: La section Unsegmentation décrit les processus qui excluent et suppriment les profils de périphériques des segments. La suppression d’un profil de périphérique d’un segment dépend de l’option de périphérique utilisée pour créer une règle de fusion de profil.
seo-title: Règles de fusion des profils et processus de désegmentation des périphériques
solution: Audience Manager
title: Règles de fusion des profils et processus de désegmentation des périphériques
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
translation-type: tm+mt
source-git-commit: 54ae5956a34c193d42d4ff9a231249d56cce87aa

---


# Règles de fusion des profils et processus de désegmentation des périphériques {#profile-merge-rules-and-device-un-segmentation-processes}

La section Unsegmentation décrit les processus qui excluent et suppriment les profils de périphériques des segments. Votre capacité à supprimer un profil de périphérique d’un segment dépend de l’option de périphérique utilisée pour créer un profil de périphérique [!UICONTROL Profile Merge Rule].

## Options de périphérique disponibles {#device-options}

À titre de rappel, les [!UICONTROL Device Options] sont disponibles dans la [!UICONTROL Profile Merge Rules Setup] section lorsque vous créez ou modifiez un [!UICONTROL Profile Merge Rule].

## Option de profil de périphérique actuelle et déssegmentation de périphérique {#current-device-profile-options}

**[!UICONTROL Device Profile]** est l’option de profil de périphérique par défaut pour un [!UICONTROL Profile Merge Rule]périphérique. [!DNL Audience Manager] peut supprimer un profil de périphérique d’un segment lorsque vous [!UICONTROL Profile Merge Rule] utilisez l’ **[!UICONTROL Device Profile]** option. Dans ces conditions, la non-segmentation se produit lorsque :

* Le profil du périphérique est inactif depuis 120 jours. Un processus hebdomadaire de nettoyage des données supprime les profils de périphérique inactifs de vos segments.
* Le périphérique n’est plus admissible pour un segment, car les mises à jour ou les modifications apportées au profil du périphérique le disqualifient. Cela se produit lorsque les critères de qualification des segments changent, ou lorsque vous appliquez un [!DNL AND NOT] opérateur à une règle de segment, ou lorsque vous spécifiez des conditions de [récence et de fréquence](../segments/recency-and-frequency.md) qui utilisent les valeurs inférieures/égales aux paramètres. Les cas d’utilisation sont décrits dans la documentation [Instant Cross-Device Suppression](instant-cross-device-suppression.md) .

![périphérique uniquement](assets/device-only.png)

## Pas d'option de périphérique et de désegmentation de périphérique {#no-device-option}

[!DNL Audience Manager] Vous pouvez supprimer un ID de plusieurs périphériques d’un segment lorsque vous [!UICONTROL Profile Merge Rule] utilisez l’option **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** . Dans ces conditions, la non-segmentation se produit lorsque l’ID inter-périphériques n’est plus admissible pour un segment, car les mises à jour ou les modifications apportées au profil inter-périphériques le excluent. Cela se produit lorsque les critères de qualification des segments changent, ou lorsque vous appliquez un [!UICONTROL AND NOT] opérateur à une règle de segment, ou lorsque vous spécifiez des conditions de [récence et de fréquence](../segments/recency-and-frequency.md) qui utilisent les valeurs inférieures/égales aux paramètres. Les cas d’utilisation sont décrits dans la documentation [Instant Cross-Device Suppression](instant-cross-device-suppression.md) .

![](assets/current-no-device.png)

## Options de graphique de périphérique et désegmentation de périphérique {#device-graph-options-unsegmentation}

[!DNL Audience Manager] Vous pouvez supprimer plusieurs profils de périphérique d’un segment lorsque vous [!UICONTROL Profile Merge Rule] utilisez une option de graphique de périphérique. La non-segmentation se produit lorsque le profil fusionné du périphérique du graphique du périphérique n’est plus admissible pour le segment, car les mises à jour ou les modifications apportées à ce profil fusionné le disqualifient du segment. Cela se produit lorsque les critères de qualification des segments changent, ou lorsque vous appliquez un [!UICONTROL AND NOT] opérateur à une règle de segment, ou lorsque vous spécifiez des conditions de [récence et de fréquence](../segments/recency-and-frequency.md) qui utilisent les valeurs inférieures/égales aux paramètres. Les cas d’utilisation sont décrits dans la documentation [Instant Cross-Device Suppression](instant-cross-device-suppression.md) .

>[!NOTE]
>
>**Limite de 100 périphériques pour l’évaluation et la disqualification**des segments.
>Audience Manager fusionne jusqu’à 100 périphériques lors de l’évaluation de segments à l’aide d’une règle de fusion de profils qui utilise un graphique de périphériques. Audience Manager évalue le périphérique actuel et jusqu’à 99 périphériques liés au périphérique actuel par un profil [](../../reference/visitor-authentication-states.md) authentifié (ID inter-périphériques). Si le signal de désegmentation est émis, le périphérique actuel et les périphériques supplémentaires sont supprimés du segment dans la destination.

![](assets/last-device-graph.png)

>[!MORE_LIKE_This]
>
>* [FAQ sur les règles de fusion de profils et le graphique de périphériques](../../faq/faq-profile-merge.md)
>* [Suppression instantanée inter-périphérique](instant-cross-device-suppression.md)

