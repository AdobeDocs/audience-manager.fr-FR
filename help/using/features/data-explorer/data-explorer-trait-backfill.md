---
description: Realizations de caractéristiques de renvoi pour capturer les audiences historiques et éviter la perte de données pertinentes avant une date de création de caractéristique.
seo-description: Realizations de caractéristiques de renvoi pour capturer les audiences historiques et éviter la perte de données pertinentes avant une date de création de caractéristique.
seo-title: Realizations Caractéristiques de renvoi
title: Realizations Caractéristiques de renvoi
uuid: 8 b 0 ef 4 e 6-d 16 a -4 d 1 d -94 f 1-b 84 eebffa 9 a 5
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

---


# Realizations Caractéristiques de renvoi {#backfill-trait-realizations}

Realizations de caractéristiques de renvoi pour capturer les audiences historiques et éviter la perte de données pertinentes avant une date de création de caractéristique.

[!UICONTROL Data Explorer Trait Backfill] est une fonctionnalité supérieure qui améliore l'expérience Audience Manager en déverrouillant des cas d'utilisation supplémentaires. Le renvoi nécessite une puissance de traitement supplémentaire et est disponible pour tous les clients Audience Manager à un coût incrémentiel. Pour plus d'informations, contactez votre représentant commercial Adobe.

Lorsque vous créez des caractéristiques à partir de signaux inutilisés, vous pouvez renvoyer les realizations de caractéristiques sur une période spécifique. [!DNL Audience Manager] capture les données historiques sur les audiences qui remplissent les critères de la nouvelle caractéristique et les stocke sur le profil correspondant. Vous pouvez voir la **[!UICONTROL Backfill Options]** section du [!UICONTROL Trait Expression] créateur **[de caractéristiques](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Vous pouvez renvoyer des realizations de caractéristiques pour des caractéristiques basées sur des règles ou intégrées.

Voici comment renvoyer les realizations de caractéristiques :

1. Atteindre [!UICONTROL Audience Data > Signals > Search] amd Exécutez une recherche de signaux ou utilisez [le tableau de bord Signaux](../../features/data-explorer/data-explorer-signals-dashboard.md) pour identifier les signaux à utiliser dans la nouvelle caractéristique.
1. Créez une nouvelle caractéristique basée sur les signaux souhaités.
1. Utilisez la **[!UICONTROL Backfill Options]** section de la **[!UICONTROL Trait Expression]** section pour sélectionner l'intervalle de temps pour lequel vous souhaitez renvoyer les realizations de caractéristiques. Les intervalles de renvoi prédéfinis incluent 1, 7, 14 et 30 jours. Vous pouvez également choisir une plage de dates personnalisée de 30 jours au maximum.

   ![caractéristique-backfill](assets/signals-trait-backfill.png)

1. (Facultatif) Cliquez sur **[!UICONTROL Estimate Realizations]** dans la **[!UICONTROL Estimated Trait Realizations]** section pour afficher la valeur estimée [!UICONTROL Unique Trait Realizations] et [!UICONTROL Total Trait Population] les valeurs de la caractéristique renvoyée au cours des 7 derniers jours.

   ![estimate-caractéristique-realizations](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Le renvoi et l'estimation des caractéristiques ne sont pas disponibles pour les caractéristiques avec des expressions qui utilisent les opérateurs suivants :
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Créez la caractéristique.

Une fois la caractéristique créée, vous verrez ses realizations renvoyées dans les statistiques de génération.

## Latence du renvoi des caractéristiques {#trait-backfilling-latency}

Les nouvelles caractéristiques commencent à capturer les audiences entre deux et trois heures après leur création. Cependant, en raison du volume élevé de données [!DNL Audience Manager] exécutées quotidiennement, la population renvoyée n'est pas immédiatement répercutée dans les graphiques [!UICONTROL Unique Trait Realizations] et [!UICONTROL Total Trait Population] dans les graphiques.

Audience Manager met à jour la [!UICONTROL Trait Graph] population avec renvoi dans les 48 heures suivant la création de la caractéristique.

## Limite de renvoi de caractéristique {#trait-backfilling-limit}

[!UICONTROL Data Explorer] vous permet de renvoyer jusqu'à 50 caractéristiques par mois, le compteur de renvoi étant réinitialisé le 1 jour de chaque mois.

>[!NOTE]
>
>Le quota de renvoi des caractéristiques ne dépasse pas les mois précédents. Par exemple, si vous renseignez 30 caractéristiques ce mois-ci, le quota de renvoi de caractéristique pour le mois suivant est réinitialisé à 50, pas 70.

## Impact sur la création de rapports {#reporting-impact}

Les realizations de caractéristiques renvoyées sont répercutées dans les [!UICONTROL Unique Trait Realizations] mesures et [!UICONTROL Total Trait Population] les mesures, comme [!DNL Audience Manager] les signaux historiques deviennent des realizations de caractéristique.

Toutefois, la [!UICONTROL Trait Graph]valeur, [!UICONTROL General Reports]et [!UICONTROL Trend Reports] ne sont pas mises à jour rétroactivement avec les mesures historiques renvoyées avant la date de création de la caractéristique.