---
description: La fonction de suppression instantanée inter-périphérique permet de supprimer des utilisateurs sur plusieurs périphériques qui leur sont associés lorsqu’une action particulière survient sur l’un de ces périphériques. Utilisez cette fonction pour offrir aux utilisateurs des conditions d’utilisation homogènes sur tous les périphériques. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.
seo-description: La fonction de suppression instantanée inter-périphérique permet de supprimer des utilisateurs sur plusieurs périphériques qui leur sont associés lorsqu’une action particulière survient sur l’un de ces périphériques. Utilisez cette fonction pour offrir aux utilisateurs des conditions d’utilisation homogènes sur tous les périphériques. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.
seo-title: Suppression instantanée inter-périphérique
title: Suppression instantanée inter-périphérique
uuid: cb 11 b 9 cb -6 d 7 d -4 aa 9-91 b 0-c 2715857 d 821
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Suppression instantanée inter-périphérique {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] est la possibilité de supprimer des utilisateurs sur plusieurs périphériques qui leur sont connectés lorsqu'une expérience spécifique se produit sur l'un de ces dispositifs. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.

## Aperçu {#overview}

[!UICONTROL Instant Cross-Device Suppression] offre deux cas d'utilisation clés : amélioration de l'expérience des utilisateurs et de l'efficacité des médias.

* **Expérience utilisateur améliorée**: Les utilisateurs qui ont déjà acheté votre produit ou service ne verront pas les mêmes créatifs qu'avant l'achat. Vous pouvez plutôt afficher des messages de vente croisée ou croisée pour les produits ou services qu'ils n'ont pas achetés.
* **Efficacité du multimédia**: Optimiser les dépenses de campagne en appliquant une enveloppe de fréquence globale à tous [!DNL DSP]les s. L'extrémité de fréquence peut être activée en temps réel pour plusieurs périphériques appartenant à un utilisateur.

The technical details of the real-time unsegmentation are described in length in [Profile Merge Rules and Device Un-Segmentation Processes](../../features/profile-merge-rules/merge-rule-unsegment.md). Lisez la mise en œuvre pratique des cas d'utilisation décrits ci-dessus.

## Do Not Target Once Converted {#do-not-target-once}

Assurez-vous que les utilisateurs qui ont déjà effectué la conversion (acheté un produit, ont acheté un abonnement, etc.) ne verra pas le même message avant la conversion. You can obtain this using the [!UICONTROL AND NOT] logic, as follows.

1. Create a segment using two traits, and use the [!UICONTROL AND NOT] logic, as shown in the image below. Vous devez utiliser une caractéristique basée sur des règles pour définir l'événement de conversion pour que le segment soit déclenché en temps réel. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
1. Faites correspondre le segment à n'importe quel nombre de destinations serveur à serveur en temps réel. Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

Les visiteurs sont admissibles pour le segment tant qu'ils n'ont pas été convertis. Dès qu'ils remplissent la caractéristique de conversion, ils ne suivent plus la règle de segment et sont immédiatement supprimés du segment.

![](assets/and_not_use_case.png)

## Do Not Target After x Impressions {#do-not-target-after-x}

Vous pouvez vous assurer que vous n'encombrez pas les utilisateurs avec le même créatif en définissant des commandes de récence et de fréquence. Dans ce scénario, créez un segment avec deux caractéristiques, comme décrit dans les étapes ci-dessous.

1. Create a segment using two traits, and use the [!UICONTROL AND] logic, as shown in the image below. Vous devez utiliser une caractéristique basée sur des règles pour définir l'événement d'impression pour que le segment soit déclenché en temps réel. Read more about how to [create rule-based traits](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
   >[!NOTE]
   >
   >You can use [!UICONTROL Actionable Log Files] or [!UICONTROL Pixel Calls] to create traits based on user impressions. Read more about [Actionable Log Files](../../integration/media-data-integration/actionable-log-files.md) and [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md).
1. Applique les commandes de fréquence à la deuxième caractéristique. Si vous le souhaitez, vous pouvez ajouter également des commandes de récence. Read more about [how to apply recency and frequency controls](../../features/segments/recency-and-frequency.md).
1. Faites correspondre le segment à n'importe quel nombre de destinations serveur à serveur en temps réel. Read on about how to add segments to [server-to-server destinations](../../features/destinations/manage-destinations.md#add-edit-segments).

Dans ce scénario, une fois que vos utilisateurs ont accumulé plus de trois impressions, ils seront supprimés de ce segment et ne verront plus ce créatif particulier.

![](assets/impressions_use_case.png)

## Important Aspects to Note - Processing {#processing-notes}

Gardez à l'esprit ces aspects liés au traitement :

* Pour que la fonctionnalité de segmentation en temps réel fonctionne, vous devez mapper les segments souhaités avec les destinations serveur à serveur.
* For devices connected to a device by a [device graph](../../features/profile-merge-rules/profile-link-use-case.md#recommendations), we enforce a four-device limit regarding evaluation and unsegmentation. This limitation is described in [Device Graph Options and Device Unsegmentation](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation).&#x200B;
* La commande unsegment sera incluse dans un fichier de commandes, qui est envoyé aux destinations toutes les 24 heures, pour plusieurs périphériques connectés par le graphique de l'appareil.
* The device must be seen in real-time (on the [Edge](../../reference/system-components/components-edge.md)) to prompt segment evaluation. For traits that have a [!UICONTROL time-to-live (TTL)] value, even if a trait [!DNL TTL] is met, the device will *not* automatically be unsegmented until the device is next seen in real-time.&#x200B; Read more about how to [Set a Trait Expiration Interval](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* If you are using the [!UICONTROL DCS API] to on-board rule-based traits in real-time, you can trigger the unsegment with the use of the [!UICONTROL AND NOT] logic. Read more about [sending data to the DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).&#x200B;

## Important Aspects to Note - Timing {#timing-notes}

Gardez à l'esprit ces aspects liés au timing :

* A segment will be stored on the [Edge](../../reference/system-components/components-edge.md) for the same time period as a device profile is stored on the [!UICONTROL Edge], namely 14 days since last real-time interaction. Read more about data retention in our [Data Retention FAQ](../../faq/faq-privacy.md#data-retention-faq).
* It takes approximately 24 hours for the unsegment operation to propagate across [!UICONTROL DCS] regions. Read more about our [!UICONTROL DCS] regions [here](../../reference/system-components/components-data-collection.md) and [here](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).