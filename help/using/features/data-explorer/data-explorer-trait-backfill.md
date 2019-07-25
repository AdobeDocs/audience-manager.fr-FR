---
description: Realizations de caractéristiques de renvoi pour capturer les audiences historiques et éviter la perte de données pertinentes avant une date de création de caractéristique.
seo-description: Realizations de caractéristiques de renvoi pour capturer les audiences historiques et éviter la perte de données pertinentes avant une date de création de caractéristique.
seo-title: Realizations Caractéristiques de renvoi
title: Realizations Caractéristiques de renvoi
uuid: 8 b 0 ef 4 e 6-d 16 a -4 d 1 d -94 f 1-b 84 eebffa 9 a 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Backfill Trait Realizations {#backfill-trait-realizations}

Realizations de caractéristiques de renvoi pour capturer les audiences historiques et éviter la perte de données pertinentes avant une date de création de caractéristique.

[!UICONTROL Data Explorer Trait Backfill] est une fonctionnalité supérieure qui améliore l'expérience Audience Manager en déverrouillant des cas d'utilisation supplémentaires. Le renvoi nécessite une puissance de traitement supplémentaire et est disponible pour tous les clients Audience Manager à un coût incrémentiel. Pour plus d'informations, contactez votre représentant commercial Adobe.

Lorsque vous créez des caractéristiques à partir de signaux inutilisés, vous pouvez renvoyer les realizations de caractéristiques sur une période spécifique. [!DNL Audience Manager] capture les données historiques sur les audiences qui remplissent les critères de la nouvelle caractéristique et les stocke sur le profil correspondant. You can see the **[!UICONTROL Backfill Options]** in the [!UICONTROL Trait Expression] section of the **[Trait Builder](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Vous pouvez renvoyer des realizations de caractéristiques pour des caractéristiques basées sur des règles ou intégrées.

Voici comment renvoyer les realizations de caractéristiques :

1. Go to [!UICONTROL Audience Data > Signals > Search] amd run a Signals Search or use the [Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) to identify the signals to use in the new trait.
1. Créez une nouvelle caractéristique basée sur les signaux souhaités.
1. Use the **[!UICONTROL Backfill Options]** in the **[!UICONTROL Trait Expression]** section to select the time interval for which you want to backfill trait realizations. Les intervalles de renvoi prédéfinis incluent 1, 7, 14 et 30 jours. Vous pouvez également choisir une plage de dates personnalisée de 30 jours au maximum.
   ![](assets/signals-trait-backfill.png)
1. (Optional) Click **[!UICONTROL Estimate Realizations]** in the **[!UICONTROL Estimated Trait Realizations]** section to see the estimated [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] values for the backfilled trait over the last 7 days.
   ![](assets/estimate-trait-realizations.png)
   >[!IMPORTANT]
   >
   >Le renvoi et l'estimation des caractéristiques ne sont pas disponibles pour les caractéristiques avec des expressions qui utilisent les opérateurs suivants :
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Créez la caractéristique.

Une fois la caractéristique créée, vous verrez ses realizations renvoyées dans les statistiques de génération.

## Trait Backfilling Latency {#trait-backfilling-latency}

Les nouvelles caractéristiques commencent à capturer les audiences entre deux et trois heures après leur création. However, due to the large volume of data that [!DNL Audience Manager] performs on a daily basis, the backfilled population is not immediately reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] graphs.

Audience Manager updates the [!UICONTROL Trait Graph] with the backfilled population within 48 hours from trait creation.

## Trait Backfilling Limit {#trait-backfilling-limit}

[!UICONTROL Data Explorer] vous permet de renvoyer jusqu'à 50 caractéristiques par mois, le compteur de renvoi étant réinitialisé le 1 jour de chaque mois.

>[!NOTE]
>
>Le quota de renvoi des caractéristiques ne dépasse pas les mois précédents. Par exemple, si vous renseignez 30 caractéristiques ce mois-ci, le quota de renvoi de caractéristique pour le mois suivant est réinitialisé à 50, pas 70.

## Impact on Reporting {#reporting-impact}

Backfilled trait realizations are reflected in the [!UICONTROL Unique Trait Realizations] and [!UICONTROL Total Trait Population] metrics, as [!DNL Audience Manager] turns historical signals into trait realizations.

However, the [!UICONTROL Trait Graph], [!UICONTROL General Reports], and [!UICONTROL Trend Reports] are not updated retroactively with historical metrics backfilled before the trait creation date.