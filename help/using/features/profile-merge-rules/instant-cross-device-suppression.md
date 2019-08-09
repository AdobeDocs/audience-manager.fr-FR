---
description: La fonction de suppression instantanée inter-périphérique permet de supprimer des utilisateurs sur plusieurs périphériques qui leur sont associés lorsqu’une action particulière survient sur l’un de ces périphériques. Utilisez cette fonction pour offrir aux utilisateurs des conditions d’utilisation homogènes sur tous les périphériques. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.
seo-description: La fonction de suppression instantanée inter-périphérique permet de supprimer des utilisateurs sur plusieurs périphériques qui leur sont associés lorsqu’une action particulière survient sur l’un de ces périphériques. Utilisez cette fonction pour offrir aux utilisateurs des conditions d’utilisation homogènes sur tous les périphériques. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.
seo-title: Suppression instantanée inter-périphérique
title: Suppression instantanée inter-périphérique
uuid: cb 11 b 9 cb -6 d 7 d -4 aa 9-91 b 0-c 2715857 d 821
translation-type: tm+mt
source-git-commit: 86b23cc4097057fceadd4d0f7c5fad0db4f4232b

---


# Suppression instantanée inter-périphérique {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] est la possibilité de supprimer des utilisateurs sur plusieurs périphériques qui leur sont connectés lorsqu'une expérience spécifique se produit sur l'un de ces dispositifs. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.

## Aperçu {#overview}

[!UICONTROL Instant Cross-Device Suppression] offre deux cas d'utilisation clés : amélioration de l'expérience des utilisateurs et de l'efficacité des médias.

* **Expérience utilisateur améliorée**: Les utilisateurs qui ont déjà acheté votre produit ou service ne verront pas les mêmes créatifs qu'avant l'achat. Vous pouvez plutôt afficher des messages de vente croisée ou croisée pour les produits ou services qu'ils n'ont pas achetés.
* **Efficacité du multimédia**: Optimiser les dépenses de campagne en appliquant une enveloppe de fréquence globale à tous [!DNL DSP]les s. L'extrémité de fréquence peut être activée en temps réel pour plusieurs périphériques appartenant à un utilisateur.

Les détails techniques de la non segmentation en temps réel sont décrits en longueur dans les sections Règles de fusion [des profils et Processus de déssegmentation des périphériques](../../features/profile-merge-rules/merge-rule-unsegment.md). Lisez la mise en œuvre pratique des cas d'utilisation décrits ci-dessus.

## Ne pas cibler une fois converti {#do-not-target-once}

Assurez-vous que les utilisateurs qui ont déjà effectué la conversion (acheté un produit, ont acheté un abonnement, etc.) ne verra pas le même message avant la conversion. Vous pouvez obtenir ce résultat à l'aide [!UICONTROL AND NOT] de la logique, comme suit.

1. Créez un segment à l'aide de deux caractéristiques et utilisez la [!UICONTROL AND NOT] logique, comme illustré dans l'image ci-dessous. Vous devez utiliser une caractéristique basée sur des règles pour définir l'événement de conversion pour que le segment soit déclenché en temps réel. En savoir plus sur [la création de caractéristiques basées sur des règles](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
1. Faites correspondre le segment à n'importe quel nombre de destinations serveur à serveur en temps réel. Découvrez comment ajouter des segments aux [destinations serveur à serveur](../../features/destinations/add-edit-segments.md).

Les visiteurs sont admissibles pour le segment tant qu'ils n'ont pas été convertis. Dès qu'ils remplissent la caractéristique de conversion, ils ne suivent plus la règle de segment et sont immédiatement supprimés du segment.

![](assets/and_not_use_case.png)

## Ne pas cibler après x impressions {#do-not-target-after-x}

Vous pouvez vous assurer que vous n'encombrez pas les utilisateurs avec le même créatif en définissant des commandes de récence et de fréquence. Dans ce scénario, créez un segment avec deux caractéristiques, comme décrit dans les étapes ci-dessous.

1. Créez un segment à l'aide de deux caractéristiques et utilisez la [!UICONTROL AND] logique, comme illustré dans l'image ci-dessous. Vous devez utiliser une caractéristique basée sur des règles pour définir l'événement d'impression pour que le segment soit déclenché en temps réel. En savoir plus sur [la création de caractéristiques basées sur des règles](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits).
   >[!NOTE]
   >
   >Vous pouvez utiliser [!UICONTROL Actionable Log Files] ou [!UICONTROL Pixel Calls] créer des caractéristiques basées sur les impressions des utilisateurs. Pour en savoir plus sur [les fichiers](../../integration/media-data-integration/actionable-log-files.md) journaux et les appels [de pixels actionnés](../../integration/media-data-integration/impression-data-pixels.md).
1. Applique les commandes de fréquence à la deuxième caractéristique. Si vous le souhaitez, vous pouvez ajouter également des commandes de récence. En savoir plus sur [l'application des commandes de récence et de fréquence](../../features/segments/recency-and-frequency.md).
1. Faites correspondre le segment à n'importe quel nombre de destinations serveur à serveur en temps réel. Découvrez comment ajouter des segments aux [destinations serveur à serveur](../../features/destinations/add-edit-segments.md).

Dans ce scénario, une fois que vos utilisateurs ont accumulé plus de trois impressions, ils seront supprimés de ce segment et ne verront plus ce créatif particulier.

![](assets/impressions_use_case.png)

## Aspects importants à prendre en compte - Traitement {#processing-notes}

Gardez à l'esprit ces aspects liés au traitement :

* Pour que la fonctionnalité de segmentation en temps réel fonctionne, vous devez mapper les segments souhaités avec les destinations serveur à serveur.
* Pour les périphériques connectés à un périphérique par un graphique [de périphérique](../../features/profile-merge-rules/profile-link-use-case.md#recommendations), nous appliquons une limite de quatre périphériques au sujet d'évaluation et de non segmentation. Cette limitation est décrite dans [les sections Options graphiques de périphérique et Unsegmentation du périphérique](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation).
* La commande unsegment sera incluse dans un fichier de commandes, qui est envoyé aux destinations toutes les 24 heures, pour plusieurs périphériques connectés par le graphique de l'appareil.
* Le périphérique doit être visible en temps réel ( [sur le bord Edge](../../reference/system-components/components-edge.md)) pour demander l'évaluation de segment. Pour les caractéristiques qui possèdent [!UICONTROL time-to-live (TTL)] une valeur, même si une caractéristique [!DNL TTL] est satisfaite, le périphérique *ne* sera pas automatiquement non segmenté tant que le périphérique n'est pas visualisé en temps réel. Pour en savoir plus sur [la définition d'un intervalle d'expiration de caractéristique](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Si vous utilisez des caractéristiques [!UICONTROL DCS API] basées sur des règles sur le bord en temps réel, vous pouvez déclencher le désegment avec l'utilisation de [!UICONTROL AND NOT] la logique. En savoir plus sur [l'envoi de données à l'API DCS](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md).

## Aspects importants à noter - Minutage {#timing-notes}

Gardez à l'esprit ces aspects liés au timing :

* Un segment sera stocké sur [le bord pour](../../reference/system-components/components-edge.md) la même période qu'un profil de périphérique stocké sur le [!UICONTROL Edge], à savoir 14 jours depuis la dernière interaction en temps réel. Pour en savoir plus sur la rétention des données, consultez notre FAQ sur la rétention [des données](../../faq/faq-privacy.md#data-retention-faq).
* La propagation de l'opération de segmentation à l'échelle [!UICONTROL DCS] des régions prend environ 24 heures. En savoir plus sur nos [!UICONTROL DCS] régions [ici](../../reference/system-components/components-data-collection.md) et [ici](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).