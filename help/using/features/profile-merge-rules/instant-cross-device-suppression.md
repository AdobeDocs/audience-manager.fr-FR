---
description: La fonction de suppression instantanée inter-périphérique permet de supprimer des utilisateurs sur plusieurs périphériques qui leur sont associés lorsqu’une action particulière survient sur l’un de ces périphériques. Utilisez cette fonction pour offrir aux utilisateurs des conditions d’utilisation homogènes sur tous les périphériques. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.
seo-description: La fonction de suppression instantanée inter-périphérique permet de supprimer des utilisateurs sur plusieurs périphériques qui leur sont associés lorsqu’une action particulière survient sur l’un de ces périphériques. Utilisez cette fonction pour offrir aux utilisateurs des conditions d’utilisation homogènes sur tous les périphériques. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.
seo-title: Suppression instantanée inter-périphérique
title: Suppression instantanée inter-périphérique
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
translation-type: tm+mt
source-git-commit: 86b23cc4097057fceadd4d0f7c5fad0db4f4232b

---


# Suppression instantanée inter-périphérique {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] permet de supprimer des utilisateurs sur plusieurs périphériques connectés lorsqu’une expérience particulière se produit sur l’un de ces périphériques. Use the [!UICONTROL Instant Cross-Device Suppression] capability to deliver a consistent experience across devices to your users. Ceci est rendu possible grâce aux options de désegmentation en temps réel dans Audience Manager.

## Aperçu {#overview}

[!UICONTROL Instant Cross-Device Suppression] fournit deux cas d’utilisation clés : amélioration de l’expérience utilisateur et de l’efficacité des médias.

* **Une expérience** utilisateur améliorée : Les utilisateurs qui ont déjà acheté votre produit ou service ne voient pas les mêmes éléments créatifs qu’avant l’achat. Au lieu de cela, vous pouvez afficher des messages de promotion ou de vente croisée pour les produits ou services que vous savez qu’ils n’ont pas achetés.
* **Efficacité** des médias : Optimisez vos dépenses de campagne en appliquant un plafond global de fréquence à tous les [!DNL DSP]secteurs. Le plafond de fréquence peut être activé en temps réel pour plusieurs périphériques appartenant à un utilisateur.

Les détails techniques de la non-segmentation en temps réel sont décrits en détail dans Règles de fusion [de profil et Processus de désegmentation](../../features/profile-merge-rules/merge-rule-unsegment.md)des périphériques. Lisez la suite pour la mise en oeuvre pratique des cas d'utilisation décrits ci-dessus.

## Ne pas cibler une fois converti {#do-not-target-once}

Assurez-vous que les utilisateurs qui ont déjà effectué une conversion (ont acheté un produit, souscrit un abonnement, etc.) ne voit pas le même message qu’avant la conversion. Vous pouvez obtenir ceci à l’aide de la [!UICONTROL AND NOT] logique, comme suit.

1. Créez un segment à l’aide de deux caractéristiques et utilisez la [!UICONTROL AND NOT] logique, comme illustré dans l’image ci-dessous. Vous devez utiliser une caractéristique basée sur des règles pour définir l’événement de conversion pour que le non-segment soit déclenché en temps réel. En savoir plus sur la [création de caractéristiques](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)basées sur des règles.
1. Faites correspondre le segment à un nombre indéfini de destinations serveur à serveur en temps réel. Découvrez comment ajouter des segments aux destinations [](../../features/destinations/add-edit-segments.md)serveur à serveur.

Vos visiteurs sont admissibles pour le segment tant qu’ils n’ont pas effectué de conversion. Dès qu’ils remplissent les conditions requises pour la caractéristique de conversion, ils cessent de suivre la règle de segmentation et sont instantanément supprimés du segment.

![](assets/and_not_use_case.png)

## Ne pas cibler après x impressions {#do-not-target-after-x}

Vous pouvez vous assurer que vous n’inondez pas vos utilisateurs avec le même élément créatif en définissant des contrôles de récence et de fréquence. Dans ce scénario, créez un segment avec deux caractéristiques, comme indiqué dans les étapes ci-dessous.

1. Créez un segment à l’aide de deux caractéristiques et utilisez la [!UICONTROL AND] logique, comme illustré dans l’image ci-dessous. Vous devez utiliser une caractéristique basée sur des règles pour définir l’événement d’impression pour que le désegment soit déclenché en temps réel. En savoir plus sur la [création de caractéristiques](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits)basées sur des règles.
   >[!NOTE]
   >
   >Vous pouvez utiliser [!UICONTROL Actionable Log Files] ou [!UICONTROL Pixel Calls] créer des caractéristiques basées sur les impressions des utilisateurs. En savoir plus sur les fichiers [journaux](../../integration/media-data-integration/actionable-log-files.md) exploitables et les appels [en](../../integration/media-data-integration/impression-data-pixels.md)pixels.
1. Appliquez des commandes de fréquence à la seconde caractéristique. Si vous le souhaitez, vous pouvez également ajouter des contrôles de récence. En savoir plus sur [l'application des contrôles](../../features/segments/recency-and-frequency.md)de récence et de fréquence.
1. Faites correspondre le segment à un nombre indéfini de destinations serveur à serveur en temps réel. Découvrez comment ajouter des segments aux destinations [](../../features/destinations/add-edit-segments.md)serveur à serveur.

Dans ce scénario, une fois que vos utilisateurs ont accumulé plus de trois impressions, ils seront supprimés de ce segment et ne verront plus ce créatif particulier.

![](assets/impressions_use_case.png)

## Aspects importants à prendre en compte - Traitement {#processing-notes}

Gardez à l’esprit les aspects suivants liés au traitement :

* Pour que la fonctionnalité de désegmentation en temps réel fonctionne, vous devez mapper les segments souhaités sur des destinations serveur à serveur en temps réel.
* Pour les périphériques connectés à un périphérique par un graphique [de](../../features/profile-merge-rules/profile-link-use-case.md#recommendations)périphérique, nous imposons une limite de quatre périphériques en ce qui concerne l’évaluation et la non-segmentation. Cette limitation est décrite dans Options graphiques du [périphérique et Unsegmentation](../../features/profile-merge-rules/merge-rule-unsegment.md#device-graph-options-unsegmentation)du périphérique. &#x200B;
* La commande unsegment sera incluse dans un fichier de commandes, qui est envoyé aux destinations toutes les 24 heures, pour plusieurs périphériques connectés par le graphique de périphériques.
* Le périphérique doit être visualisé en temps réel (sur le [bord](../../reference/system-components/components-edge.md)) pour déclencher l’évaluation des segments. Pour les caractéristiques qui ont une [!UICONTROL time-to-live (TTL)] valeur, même si une caractéristique [!DNL TTL] est satisfaite, le périphérique ** ne sera pas automatiquement désegmenté tant que le périphérique n'aura pas été vu en temps réel. &#x200B; En savoir plus sur la [définition d’un intervalle](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)d’expiration des caractéristiques.
* Si vous utilisez les caractéristiques [!UICONTROL DCS API] à bord basées sur des règles en temps réel, vous pouvez déclencher le désegmentation à l’aide de la [!UICONTROL AND NOT] logique. En savoir plus sur l’ [envoi de données à l’API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md)DCS. &#x200B;

## Aspects importants à noter - Minutage {#timing-notes}

Gardez à l’esprit les points suivants relatifs au timing :

* Un segment est stocké sur le [bord](../../reference/system-components/components-edge.md) pendant la même période qu’un profil de périphérique est stocké sur le [!UICONTROL Edge], à savoir 14 jours depuis la dernière interaction en temps réel. Pour en savoir plus sur la rétention des données, consultez notre FAQ [sur la rétention des](../../faq/faq-privacy.md#data-retention-faq)données.
* L’opération de désegmentation prend environ 24 heures pour se propager à travers [!UICONTROL DCS] les régions. En savoir plus sur nos [!UICONTROL DCS] régions [ici](../../reference/system-components/components-data-collection.md) et [ici](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).