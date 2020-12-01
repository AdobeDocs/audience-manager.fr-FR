---
description: La fonction de suppression instantanée inter-périphérique permet de supprimer des utilisateurs sur plusieurs périphériques qui leur sont associés lorsqu’une action particulière survient sur l’un de ces périphériques. Utilisez cette fonction pour offrir aux utilisateurs des conditions d’utilisation homogènes sur tous les périphériques. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.
seo-description: La fonction de suppression instantanée inter-périphérique permet de supprimer des utilisateurs sur plusieurs périphériques qui leur sont associés lorsqu’une action particulière survient sur l’un de ces périphériques. Utilisez cette fonction pour offrir aux utilisateurs des conditions d’utilisation homogènes sur tous les périphériques. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.
seo-title: Suppression instantanée multi-appareils
title: Suppression instantanée multi-appareils
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 15%

---


# Suppression instantanée multi-appareils {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] permet de supprimer des utilisateurs sur plusieurs périphériques connectés lorsqu’une expérience particulière se produit sur l’un de ces périphériques. Utilisez la fonctionnalité [!UICONTROL Instant Cross-Device Suppression] pour offrir une expérience cohérente sur tous les périphériques à vos utilisateurs. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.

## Présentation {#overview}

[!UICONTROL Instant Cross-Device Suppression] fournit deux cas d’utilisation clés : amélioration de l’expérience utilisateur et de l’efficacité des médias.

* **Une meilleure expérience** utilisateur : Les utilisateurs qui ont déjà acheté votre produit ou service ne voient pas les mêmes éléments créatifs qu’avant l’achat. Au lieu de cela, vous pouvez afficher des messages d’augmentation ou de vente croisée pour des produits ou services que vous savez qu’ils n’ont pas achetés.
* **Efficacité** des médias : Optimisez vos dépenses de campagne en appliquant un plafond de fréquence global à toutes les  [!DNL DSP]zones. Le plafonnement de fréquence peut être activé en temps réel pour plusieurs périphériques appartenant à un utilisateur.

Les détails techniques de la non-segmentation en temps réel sont décrits en détail dans [Règles de fusion des Profils et Processus de non-segmentation des périphériques](merge-rule-unsegment.md). Lisez la suite pour la mise en oeuvre pratique des cas d&#39;utilisation décrits ci-dessus.

## Ne pas Cible une fois converti {#do-not-target-once}

Assurez-vous que vos utilisateurs qui ont déjà effectué des conversions (ont acheté un produit, acquis un abonnement, etc.) ne verra pas le même message qu’avant la conversion. Vous pouvez obtenir ce résultat à l&#39;aide de la logique [!UICONTROL AND NOT], comme suit.

1. Créez un segment à l’aide de deux caractéristiques et utilisez la logique [!UICONTROL AND NOT], comme illustré dans l’image ci-dessous. Vous devez utiliser une caractéristique basée sur des règles pour définir le événement de conversion pour que le non-segment soit déclenché en temps réel. En savoir plus sur la façon de [créer des caractéristiques basées sur des règles](../traits/create-onboarded-rule-based-traits.md).
2. Faites correspondre le segment à n’importe quel nombre de destinations serveur à serveur en temps réel. Découvrez comment ajouter des segments à [destinations serveur à serveur](../destinations/add-edit-segments.md).

Vos visiteurs sont admissibles pour le segment tant qu’ils n’ont pas effectué de conversion. Dès qu’ils répondent aux critères de la caractéristique de conversion, ils cessent de suivre la règle de segmentation et sont instantanément supprimés du segment.

![](assets/and_not_use_case.png)

## Ne pas Cible après x impressions {#do-not-target-after-x}

Vous pouvez vous assurer de ne pas inonder vos utilisateurs de la même créativité en définissant des contrôles de récence et de fréquence. Dans ce scénario, créez un segment avec deux caractéristiques, comme indiqué dans les étapes ci-dessous.

1. Créez un segment à l’aide de deux caractéristiques et utilisez la logique [!UICONTROL AND], comme illustré dans l’image ci-dessous. Vous devez utiliser une caractéristique basée sur des règles pour définir le événement d’impression pour que le non-segment soit déclenché en temps réel. En savoir plus sur la façon de [créer des caractéristiques basées sur des règles](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Vous pouvez utiliser [!UICONTROL Actionable Log Files] ou [!UICONTROL Pixel Calls] pour créer des caractéristiques basées sur les impressions des utilisateurs. Pour en savoir plus sur les [Fichiers journaux exploitables](../../integration/media-data-integration/actionable-log-files.md) et les [Appels en pixels](../../integration/media-data-integration/impression-data-pixels.md).
2. Appliquez des contrôles de fréquence à la seconde caractéristique. Si vous le souhaitez, vous pouvez également ajouter des contrôles de récence. En savoir plus sur [comment appliquer les contrôles de récence et de fréquence](../segments/recency-and-frequency.md).
3. Faites correspondre le segment à n’importe quel nombre de destinations serveur à serveur en temps réel. Découvrez comment ajouter des segments à [destinations serveur à serveur](../destinations/add-edit-segments.md).

Dans ce scénario, une fois que vos utilisateurs ont accumulé plus de trois impressions, ils seront supprimés de ce segment et ne verront plus ce créatif particulier.

![](assets/impressions_use_case.png)

## Aspects importants à prendre en compte - Traitement {#processing-notes}

Gardez à l’esprit les aspects suivants liés au traitement :

* Pour que la fonctionnalité de non-segmentation en temps réel fonctionne, vous devez mapper les segments de votre choix à des destinations serveur à serveur en temps réel.
* Pour les périphériques connectés à un périphérique par un [graphique de périphérique](profile-link-use-case.md#recommendations), nous appliquons une limite de quatre périphériques en ce qui concerne l&#39;évaluation et la non-segmentation. Cette limitation est décrite dans [Options graphiques du périphérique et Unsegmentation du périphérique](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* La commande unsegment sera incluse dans un fichier de commandes, qui est envoyé aux destinations toutes les 24 heures, pour plusieurs périphériques connectés par le graphique de l&#39;appareil.
* Le périphérique doit être visible en temps réel (sur l’[Edge](../../reference/system-components/components-edge.md) pour que l’évaluation des segments s’effectue en temps réel. Pour les caractéristiques ayant une [!UICONTROL time-to-live (TTL)] lorsque la caractéristique [!DNL TTL] est satisfaite, le périphérique est automatiquement désegmenté dans les 24 heures par l&#39;intermédiaire du fichier de commandes. &#x200B; En savoir plus sur la façon de [définir un intervalle d’expiration de caractéristique](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Si vous utilisez [!UICONTROL DCS API] pour des caractéristiques basées sur des règles embarquées en temps réel, vous pouvez déclencher la désegmentation à l’aide de la logique [!UICONTROL AND NOT]. En savoir plus sur [l&#39;envoi de données à l&#39;API DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Aspects importants à noter - Minutage {#timing-notes}

Gardez à l’esprit les aspects suivants liés au timing :

* Un segment est stocké sur le [Edge](../../reference/system-components/components-edge.md) pendant la même période qu&#39;un profil de périphérique est stocké sur le [!UICONTROL Edge], c&#39;est-à-dire 14 jours après la dernière interaction en temps réel. Pour en savoir plus sur la conservation des données, consultez notre [FAQ sur la conservation des données](../../faq/faq-privacy.md#data-retention-faq).
* Il faut environ 24 heures pour que l&#39;opération de non-segmentation se propage dans les régions [!DNL DCS]. Pour en savoir plus sur nos [!DNL DCS] régions [ici](../..//reference/system-components/components-data-collection.md) et [ici](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
