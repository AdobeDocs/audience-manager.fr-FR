---
description: La section Unsegmentation décrit les processus qui excluent et suppriment les profils de périphériques des segments. La possibilité de supprimer un profil de périphérique d’un segment dépend de l’option de périphérique utilisée pour créer une règle de fusion de Profil.
seo-description: La section Unsegmentation décrit les processus qui excluent et suppriment les profils de périphériques des segments. La possibilité de supprimer un profil de périphérique d’un segment dépend de l’option de périphérique utilisée pour créer une règle de fusion de Profil.
seo-title: Règles de fusion des Profils et processus de désegmentation des périphériques
solution: Audience Manager
title: Règles de fusion des Profils et processus de désegmentation des périphériques
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---


# Règles de fusion des Profils et processus de désegmentation des périphériques {#profile-merge-rules-and-device-un-segmentation-processes}

La section Unsegmentation décrit les processus qui excluent et suppriment les profils de périphériques des segments. Votre capacité à supprimer un profil de périphérique d’un segment dépend de l’option de périphérique utilisée pour créer un [!UICONTROL Profile Merge Rule]segment.

## Options de périphérique disponibles {#device-options}

À titre de rappel, les [!UICONTROL Device Options] sont disponibles dans la [!UICONTROL Profile Merge Rules Setup] section lorsque vous créez ou modifiez un [!UICONTROL Profile Merge Rule]fichier.

## Option actuelle de Profil de périphérique et déssegmentation de périphérique {#current-device-profile-options}

**[!UICONTROL Device Profile]** est l’option de profil de périphérique par défaut pour un [!UICONTROL Profile Merge Rule]périphérique. [!DNL Audience Manager] Vous pouvez supprimer un profil de périphérique d’un segment lorsque vous [!UICONTROL Profile Merge Rule] utilisez l’ **[!UICONTROL Device Profile]** option. Dans ces conditions, la non-segmentation se produit lorsque :

* Le profil du périphérique est inactif depuis 120 jours. Un processus hebdomadaire de nettoyage des données supprime les profils de périphériques inactifs de vos segments.
* L&#39;appareil n&#39;est plus admissible pour un segment, car les mises à jour ou les modifications apportées au profil de l&#39;appareil l&#39;excluent. Cela se produit lorsque les critères de qualification des segments changent ou lorsque vous appliquez un [!DNL AND NOT] opérateur à une règle de segment, ou lorsque vous spécifiez des conditions de [récence et de fréquence](../segments/recency-and-frequency.md) qui utilisent les paramètres Inférieur/égal à. Les cas d’utilisation sont décrits dans la documentation [Instant Cross-Device Suppression](instant-cross-device-suppression.md) .

![périphérique uniquement](assets/device-only.png)

## Pas d&#39;option de périphérique et de désegmentation de périphérique {#no-device-option}

[!DNL Audience Manager] Vous pouvez supprimer un ID sur plusieurs périphériques d’un segment lorsque vous [!UICONTROL Profile Merge Rule] utilisez l’option **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** . Dans ces conditions, la non-segmentation se produit lorsque l’identifiant inter-périphériques n’est plus admissible pour un segment car les mises à jour ou les modifications apportées au profil inter-périphériques le excluent. Cela se produit lorsque les critères de qualification des segments changent ou lorsque vous appliquez un [!UICONTROL AND NOT] opérateur à une règle de segment, ou lorsque vous spécifiez des conditions de [récence et de fréquence](../segments/recency-and-frequency.md) qui utilisent les paramètres Inférieur/égal à. Les cas d’utilisation sont décrits dans la documentation [Instant Cross-Device Suppression](instant-cross-device-suppression.md) .

![](assets/current-no-device.png)

## Options graphiques du périphérique et déssegmentation du périphérique {#device-graph-options-unsegmentation}

[!DNL Audience Manager] Vous pouvez supprimer plusieurs profils de périphérique d’un segment lorsque vous [!UICONTROL Profile Merge Rule] utilisez une option de graphique de périphérique. La non-segmentation se produit lorsque le profil fusionné du périphérique dans le graphique du périphérique n’est plus admissible pour le segment, car les mises à jour ou les modifications apportées à ce profil fusionné le disqualifient pour le segment. Cela se produit lorsque les critères de qualification des segments changent ou lorsque vous appliquez un [!UICONTROL AND NOT] opérateur à une règle de segment, ou lorsque vous spécifiez des conditions de [récence et de fréquence](../segments/recency-and-frequency.md) qui utilisent les paramètres Inférieur/égal à. Les cas d’utilisation sont décrits dans la documentation [Instant Cross-Device Suppression](instant-cross-device-suppression.md) .

>[!NOTE]
>
>**Limite de 100 dispositifs pour l&#39;évaluation et la disqualification**des segments.
>L’Audience Manager fusionne jusqu’à 100 périphériques lors de l’évaluation de segments avec une règle de fusion de Profil qui utilise un graphique de périphérique. L’Audience Manager évalue le périphérique actuel et jusqu’à 99 périphériques liés au périphérique actuel par un profil [](../../reference/visitor-authentication-states.md) authentifié (ID inter-périphériques). Si le signal de non-segmentation est émis, le périphérique actuel et les périphériques supplémentaires seront supprimés du segment dans la destination.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [FAQ sur les règles de fusion de Profils et le graphique de périphériques](../../faq/faq-profile-merge.md)
>* [Suppression instantanée inter-périphérique](instant-cross-device-suppression.md)

