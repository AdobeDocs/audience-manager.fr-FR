---
description: La fonction de suppression instantanée inter-périphérique permet de supprimer des utilisateurs sur plusieurs périphériques qui leur sont associés lorsqu’une action particulière survient sur l’un de ces périphériques. Utilisez la fonctionnalité de suppression instantanée sur plusieurs appareils pour offrir à vos utilisateurs une expérience cohérente sur l’ensemble des appareils. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: Suppression Instantanée Sur Plusieurs Appareils
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 6%

---

# Suppression Instantanée Sur Plusieurs Appareils {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] est la possibilité de supprimer des utilisateurs sur plusieurs appareils qui leur sont connectés lorsqu’une expérience particulière se produit sur l’un de ces appareils. Utilisez la fonctionnalité [!UICONTROL Instant Cross-Device Suppression] pour offrir une expérience cohérente entre les appareils à vos utilisateurs. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.

## Présentation {#overview}

[!UICONTROL Instant Cross-Device Suppression] propose deux cas d’utilisation clés : amélioration de l’expérience utilisateur et efficacité des médias.

* **Amélioration de l’expérience utilisateur** : les utilisateurs et utilisatrices qui ont déjà acheté votre produit ou service ne verront pas les mêmes contenus publicitaires qu’avant l’achat. Vous pouvez plutôt afficher des messages de vente incitative ou de vente croisée pour des produits ou des services que vous savez qu’ils n’ont pas achetés.
* **Efficacité des médias** : optimisez vos dépenses de campagne en appliquant une limitation de fréquence globale à tous les [!DNL DSP]. La limitation de fréquence peut être activée en temps réel pour plusieurs appareils appartenant à un utilisateur.

Les détails techniques de l’annulation de segmentation en temps réel sont décrits en détail dans la section [Règles de fusion de profils et Processus d’annulation de segmentation d’appareil](merge-rule-unsegment.md). Lisez la suite pour une mise en œuvre pratique des cas d’utilisation décrits ci-dessus.

## Ne Pas Cibler Une Fois Converti {#do-not-target-once}

Assurez-vous que les utilisateurs et utilisatrices qui ont déjà effectué une conversion (achat d’un produit, souscription à un abonnement, etc.) ne verront pas le même message qu’avant la conversion. Vous pouvez l’obtenir à l’aide de la logique [!UICONTROL AND NOT], comme suit.

1. Créez un segment à l’aide de deux caractéristiques et utilisez la logique [!UICONTROL AND NOT], comme illustré dans l’image ci-dessous. Vous devez utiliser une caractéristique basée sur des règles pour définir l’événement de conversion pour que l’annulation de segment soit déclenchée en temps réel. En savoir plus sur la façon de [créer des caractéristiques basées sur des règles](../traits/create-onboarded-rule-based-traits.md).
2. Mappez le segment à un nombre illimité de destinations serveur à serveur en temps réel. Découvrez comment ajouter des segments aux [destinations serveur à serveur](../destinations/add-edit-segments.md).

Vos visiteurs sont qualifiés pour le segment tant qu’ils n’ont pas effectué de conversion. Dès qu’ils remplissent les critères de la caractéristique de conversion, ils cessent de suivre la règle de segment et sont instantanément supprimés du segment.

![](assets/and_not_use_case.png)

## Ne Pas Cibler Après X Impressions {#do-not-target-after-x}

Vous pouvez veiller à ne pas inonder vos utilisateurs de la même créativité en définissant des contrôles de récence et de fréquence. Dans ce scénario, créez un segment avec deux caractéristiques, comme indiqué dans les étapes ci-dessous.

1. Créez un segment à l’aide de deux caractéristiques et utilisez la logique [!UICONTROL AND], comme illustré dans l’image ci-dessous. Vous devez utiliser une caractéristique basée sur des règles pour définir l’événement d’impression afin que l’annulation de segment soit déclenchée en temps réel. En savoir plus sur la façon de [créer des caractéristiques basées sur des règles](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Vous pouvez utiliser [!UICONTROL Actionable Log Files] ou [!UICONTROL Pixel Calls] pour créer des caractéristiques en fonction des impressions des utilisateurs. En savoir plus sur les [Fichiers journaux exploitables](../../integration/media-data-integration/actionable-log-files.md) et [Appels de pixels](../../integration/media-data-integration/impression-data-pixels.md).
2. Appliquez des contrôles de fréquence à la deuxième caractéristique. Si vous le souhaitez, vous pouvez également ajouter des contrôles de récence. En savoir plus sur [comment appliquer des contrôles de récence et de fréquence](../segments/recency-and-frequency.md).
3. Mappez le segment à un nombre illimité de destinations serveur à serveur en temps réel. Découvrez comment ajouter des segments aux [destinations serveur à serveur](../destinations/add-edit-segments.md).

Dans ce scénario, une fois que vos utilisateurs ont accumulé plus de trois impressions, ils sont supprimés de ce segment et ne verront plus cette création particulière.

![](assets/impressions_use_case.png)

## Aspects importants à noter - Traitement {#processing-notes}

Gardez à l’esprit les aspects suivants liés au traitement :

* Pour que la fonctionnalité d’annulation de segment en temps réel fonctionne, vous devez mapper les segments souhaités aux destinations serveur à serveur en temps réel.
* Pour les appareils connectés à un appareil par un [graphique d’appareil](profile-link-use-case.md#recommendations), nous appliquons une limite de quatre appareils concernant l’évaluation et la non-segmentation. Cette limitation est décrite dans [Options du graphique de l’appareil et Dissegmentation de l’appareil](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* La commande unsegment est incluse dans un fichier par lot, qui est envoyé aux destinations toutes les 24 heures, pour plusieurs appareils connectés par le graphique d’appareil.
* L’appareil doit être affiché en temps réel (dans l’[Edge](../../reference/system-components/components-edge.md) pour inviter à l’évaluation des segments en temps réel. Pour les caractéristiques qui ont un [!UICONTROL time-to-live (TTL)] lorsque le [!DNL TTL] de caractéristique est satisfait, l’appareil sera automatiquement non segmenté dans les 24 heures via le fichier de commandes&#x200B; En savoir plus sur comment [Définir un intervalle d’expiration de caractéristique](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Si vous utilisez l’[!UICONTROL DCS API] pour intégrer en temps réel des caractéristiques basées sur des règles, vous pouvez déclencher l’annulation de segment à l’aide de la logique [!UICONTROL AND NOT]. En savoir plus sur [l’envoi de données à l’API DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Aspects importants à noter - Calendrier {#timing-notes}

Gardez à l’esprit les aspects suivants liés au minutage :

* Un segment sera stocké sur [Edge](../../reference/system-components/components-edge.md) pendant la même période que le profil d’appareil stocké sur le [!UICONTROL Edge], soit 14 jours depuis la dernière interaction en temps réel. Pour en savoir plus sur la conservation des données, consultez notre [&#x200B; FAQ sur la conservation des données &#x200B;](../../faq/faq-privacy.md#data-retention-faq).
* Il faut environ 24 heures pour que l’opération d’annulation de segment se propage dans les régions [!DNL DCS]. Pour en savoir plus sur nos [!DNL DCS] régions [ici](../../reference/system-components/components-data-collection.md) et [ici](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
