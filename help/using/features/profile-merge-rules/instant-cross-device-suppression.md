---
description: La fonction de suppression instantanée inter-périphérique permet de supprimer des utilisateurs sur plusieurs périphériques qui leur sont associés lorsqu’une action particulière survient sur l’un de ces périphériques. Utilisez cette fonction pour offrir aux utilisateurs des conditions d’utilisation homogènes sur tous les périphériques. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.
seo-description: La fonction de suppression instantanée inter-périphérique permet de supprimer des utilisateurs sur plusieurs périphériques qui leur sont associés lorsqu’une action particulière survient sur l’un de ces périphériques. Utilisez cette fonction pour offrir aux utilisateurs des conditions d’utilisation homogènes sur tous les périphériques. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.
seo-title: Suppression instantanée multi-appareils
title: Suppression instantanée multi-appareils
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Fusion des profils
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 15%

---

# Suppression instantanée multi-appareils {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] est la capacité de supprimer des utilisateurs sur plusieurs appareils qui leur sont connectés lorsqu’une expérience particulière survient sur l’un de ces appareils. Utilisez la fonctionnalité [!UICONTROL Instant Cross-Device Suppression] pour offrir une expérience cohérente sur tous les appareils à vos utilisateurs. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.

## Présentation {#overview}

[!UICONTROL Instant Cross-Device Suppression] propose deux cas pratiques clés : amélioration de l’expérience utilisateur et de l’efficacité multimédia.

* **Amélioration de l’expérience** utilisateur : Les utilisateurs qui ont déjà acheté votre produit ou service ne verront pas les mêmes créations qu’avant l’achat. Au lieu de cela, vous pouvez afficher des messages d’augmentation ou de vente croisée pour des produits ou des services que vous savez qu’ils n’ont pas achetés.
* **Efficacité du média** : Optimisez vos dépenses de campagne en appliquant un plafond global de fréquence sur tous les  [!DNL DSP]segments. Le plafonnement de la fréquence peut être activé en temps réel pour plusieurs périphériques appartenant à un utilisateur.

Les détails techniques de la désegmentation en temps réel sont décrits en détail dans [Règles de fusion de profils et processus de suppression de la segmentation des appareils](merge-rule-unsegment.md). Lisez la suite pour la mise en oeuvre pratique des cas d’utilisation décrits ci-dessus.

## Ne pas cibler une fois converti {#do-not-target-once}

Assurez-vous que vos utilisateurs qui ont déjà converti (acheté un produit, souscrit à un abonnement, etc.) ne verra pas le même message qu’avant la conversion. Vous pouvez obtenir ce résultat à l’aide de la logique [!UICONTROL AND NOT], comme suit.

1. Créez un segment à l’aide de deux caractéristiques et utilisez la logique [!UICONTROL AND NOT], comme illustré dans l’image ci-dessous. Vous devez utiliser une caractéristique basée sur des règles pour définir l’événement de conversion pour que le non-segment soit déclenché en temps réel. Découvrez comment [créer des caractéristiques basées sur des règles](../traits/create-onboarded-rule-based-traits.md).
2. Mappez le segment à un nombre indéfini de destinations serveur à serveur en temps réel. Découvrez comment ajouter des segments aux [destinations serveur à serveur](../destinations/add-edit-segments.md).

Vos visiteurs sont admissibles pour le segment tant qu’ils n’ont pas effectué de conversion. Dès qu’ils répondent aux critères de la caractéristique de conversion, ils cessent de suivre la règle de segment et sont instantanément supprimés du segment.

![](assets/and_not_use_case.png)

## Ne pas cibler après x impressions {#do-not-target-after-x}

Vous pouvez vous assurer que vous n’inondez pas vos utilisateurs de la même manière de créer en définissant les contrôles de récence et de fréquence. Dans ce scénario, créez un segment avec deux caractéristiques, comme indiqué dans les étapes ci-dessous.

1. Créez un segment à l’aide de deux caractéristiques et utilisez la logique [!UICONTROL AND], comme illustré dans l’image ci-dessous. Vous devez utiliser une caractéristique basée sur des règles pour définir l’événement d’impression pour que le non-segment soit déclenché en temps réel. Découvrez comment [créer des caractéristiques basées sur des règles](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >Vous pouvez utiliser [!UICONTROL Actionable Log Files] ou [!UICONTROL Pixel Calls] pour créer des caractéristiques basées sur les impressions des utilisateurs. En savoir plus sur les [fichiers journaux pratiques](../../integration/media-data-integration/actionable-log-files.md) et les [appels de pixel](../../integration/media-data-integration/impression-data-pixels.md).
2. Appliquez des contrôles de fréquence à la seconde caractéristique. Si vous le souhaitez, vous pouvez également ajouter des contrôles de récence. En savoir plus sur [la façon d’appliquer les contrôles de récence et de fréquence](../segments/recency-and-frequency.md).
3. Mappez le segment à un nombre indéfini de destinations serveur à serveur en temps réel. Découvrez comment ajouter des segments aux [destinations serveur à serveur](../destinations/add-edit-segments.md).

Dans ce scénario, une fois que vos utilisateurs ont accumulé plus de trois impressions, ils seront supprimés de ce segment et ne verront plus ce créatif particulier.

![](assets/impressions_use_case.png)

## Aspects importants à noter - Traitement {#processing-notes}

Gardez à l’esprit les aspects suivants liés au traitement :

* Pour que la fonctionnalité de désegmentation en temps réel fonctionne, vous devez mapper les segments souhaités aux destinations serveur à serveur en temps réel.
* Pour les appareils connectés à un appareil par un [graphique d’appareil](profile-link-use-case.md#recommendations), nous appliquons une limite de quatre appareils en ce qui concerne l’évaluation et la suppression de la segmentation. Cette limitation est décrite dans [Options de Device Graph et suppression de la segmentation des appareils](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* La commande de suppression de la segmentation sera incluse dans un fichier de commandes, qui est envoyé aux destinations toutes les 24 heures, pour plusieurs appareils connectés par la représentation graphique des appareils.
* L’appareil doit être affiché en temps réel (sur le [Edge](../../reference/system-components/components-edge.md) pour inviter l’évaluation des segments à s’effectuer en temps réel. Pour les caractéristiques ayant une [!UICONTROL time-to-live (TTL)] lorsque la caractéristique [!DNL TTL] est atteinte, l’appareil est automatiquement désegmenté dans les 24 heures via le fichier de commandes. &#x200B; En savoir plus sur la façon de [définir un intervalle d’expiration de caractéristique](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Si vous utilisez [!UICONTROL DCS API] pour des caractéristiques standard intégrées en temps réel, vous pouvez déclencher la suppression de la segmentation à l’aide de la logique [!UICONTROL AND NOT]. En savoir plus sur [l’envoi de données à l’API DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Aspects importants à noter - Minutage {#timing-notes}

Gardez à l’esprit les aspects suivants liés au timing :

* Un segment sera stocké sur l’[Edge](../../reference/system-components/components-edge.md) pendant la même période qu’un profil d’appareil est stocké sur l’[!UICONTROL Edge], c’est-à-dire 14 jours depuis la dernière interaction en temps réel. Pour en savoir plus sur la rétention des données, consultez la [FAQ sur la rétention des données](../../faq/faq-privacy.md#data-retention-faq).
* La propagation de l’opération de non-segmentation dans les régions [!DNL DCS] prend environ 24 heures. Pour en savoir plus sur nos [!DNL DCS] régions [ici](../../reference/system-components/components-data-collection.md) et [ici](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
