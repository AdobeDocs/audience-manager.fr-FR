---
description: Renseignez les réalisations de caractéristiques pour capturer les  de  historiques et éviter la perte de données pertinentes avant la date de création d’une caractéristique.
seo-description: Renseignez les réalisations de caractéristiques pour capturer les  de  historiques et éviter la perte de données pertinentes avant la date de création d’une caractéristique.
seo-title: Renvoi des caractéristiques
title: Renvoi des caractéristiques
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: 383d529d656f86fa39e2e11d312e8a8a2092926b

---


# Renvoi des caractéristiques {#backfill-trait-realizations}

Renseignez les réalisations de caractéristiques pour capturer les  de  historiques et éviter la perte de données pertinentes avant la date de création d’une caractéristique.

>[!IMPORTANT]
>
> [!UICONTROL Data Explorer Trait Backfill] est une fonctionnalité Premium qui améliore l’expérience  de  Manager en déverrouillant d’autres cas d’utilisation. Le renvoi nécessite une puissance de traitement supplémentaire et est disponible pour tous les clients   Manager à un coût incrémentiel. Pour plus d’informations, contactez votre représentant commercial Adobe.

Lorsque vous créez des caractéristiques à partir de signaux inutilisés, vous pouvez choisir de renvoyer les réalisations de caractéristiques sur une période spécifique. [!DNL Audience Manager] capture les données historiques sur les  de  qui remplissent les conditions requises pour la nouvelle caractéristique et les stocke sur l’ correspondante. Vous pouvez voir la **[!UICONTROL Backfill Options]** section dans la [!UICONTROL Trait Expression] section du Créateur de **[caractéristiques](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Vous pouvez renvoyer les réalisations de caractéristiques pour les caractéristiques basées sur des règles et les caractéristiques intégrées.

Voici comment renvoyer des réalisations de caractéristiques :

1. Accédez à [!UICONTROL Audience Data > Signals > Search] et exécutez une recherche de signaux ou utilisez le [de](../../features/data-explorer/data-explorer-signals-dashboard.md) signaux pour identifier les signaux à utiliser dans la nouvelle caractéristique.
1. Créez une nouvelle caractéristique en fonction des signaux souhaités.
1. Utilisez la **[!UICONTROL Backfill Options]** section **[!UICONTROL Trait Expression]** pour sélectionner l’intervalle de temps pour lequel vous souhaitez renvoyer les réalisations de caractéristiques. Les intervalles de renvoi prédéfinis comprennent 1, 7, 14 et 30 jours. Vous pouvez également choisir une plage de dates personnalisée allant jusqu’à 30 jours.

   ![trait-renvoi](assets/signals-trait-backfill.png)

1. (Facultatif) Cliquez **[!UICONTROL Estimate Realizations]** dans la **[!UICONTROL Estimated Trait Realizations]** section pour afficher l’estimation [!UICONTROL Unique Trait Realizations] et les [!UICONTROL Total Trait Population] valeurs de la caractéristique renversée au cours des 7 derniers jours.

   ![estimation-caractéristiques-réalisations](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Le renvoi et l’estimation des caractéristiques ne sont pas disponibles pour les caractéristiques avec   qui utilisent les opérateurs suivants :
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Créez la caractéristique.

Une fois que vous avez créé le trait, vous verrez ses réalisations empilées incluses dans les statistiques de réalisation.

Regardez la vidéo ci-dessous pour une présentation vidéo des caractéristiques de renvoi.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latence de renvoi de caractéristiques {#trait-backfilling-latency}

Caractéristiques nouvellement créées  capturer  deux à trois heures après la création. Cependant, en raison du volume important de données qui [!DNL Audience Manager] se produisent quotidiennement, la population reconstituée n’est pas immédiatement reflétée dans les [!UICONTROL Unique Trait Realizations] graphiques et [!UICONTROL Total Trait Population] les graphiques.

 Gestionnaire de  de met à jour le [!UICONTROL Trait Graph] avec la population de renvois dans les 48 heures suivant la création de la caractéristique.

## Limite de renvoi de caractéristiques {#trait-backfilling-limit}

[!UICONTROL Data Explorer] vous permet de renvoyer jusqu’à 50 caractéristiques par mois, le compteur de renvoi étant réinitialisé le 1 jour de chaque mois.

>[!NOTE]
>
>Le quota de renvois aux caractéristiques n’est pas reporté des mois précédents. Par exemple, si vous renseignez 30 caractéristiques ce mois-ci, le quota de renvoi de caractéristiques pour le mois suivant est réinitialisé à 50, et non à 70.

## Impact sur les {#reporting-impact}

Les réalisations de caractéristiques empilées sont reflétées dans les [!UICONTROL Unique Trait Realizations] mesures et [!UICONTROL Total Trait Population] les mesures, tandis que [!DNL Audience Manager] les signaux historiques deviennent des réalisations de caractéristiques.

Toutefois, les variables [!UICONTROL Trait Graph], [!UICONTROL General Reports]et [!UICONTROL Trend Reports] ne sont pas mises à jour rétroactivement avec des mesures historiques renvoyées avant la date de création de la caractéristique.