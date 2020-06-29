---
description: Renvoi des réalisations de caractéristiques pour capturer les audiences historiques et éviter la perte de données pertinentes avant la date de création d’une caractéristique.
seo-description: Renvoi des réalisations de caractéristiques pour capturer les audiences historiques et éviter la perte de données pertinentes avant la date de création d’une caractéristique.
seo-title: Renvoi des rapprochements de caractéristiques
title: Renvoi des rapprochements de caractéristiques
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---


# Renvoi des rapprochements de caractéristiques {#backfill-trait-realizations}

Renvoi des réalisations de caractéristiques pour capturer les audiences historiques et éviter la perte de données pertinentes avant la date de création d’une caractéristique.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] est une fonctionnalité haut de gamme qui améliore l&#39;expérience d&#39;Audience Manager en déverrouillant d&#39;autres cas d&#39;utilisation. Le renvoi nécessite une puissance de traitement supplémentaire et est disponible pour tous les clients de l’Audience Manager à un coût incrémentiel. Veuillez contacter votre représentant commercial Adobe pour plus de détails.

Lorsque vous créez des caractéristiques à partir de signaux inutilisés, vous pouvez choisir de renvoyer les réalisations des caractéristiques sur une période donnée. [!DNL Audience Manager] capture les données historiques sur les audiences qui remplissent les conditions requises pour la nouvelle caractéristique et les stocke sur le profil correspondant. Vous pouvez voir la **[!UICONTROL Backfill Options]** section dans la [!UICONTROL Trait Expression] section du créateur **[de](../../features/traits/about-trait-builder.md)**caractéristiques.

>[!NOTE]
>
>Vous pouvez renvoyer des réalisations de caractéristiques pour les caractéristiques basées sur des règles et les caractéristiques intégrées.

Voici comment renvoyer des réalisations de caractéristiques :

1. Accédez à [!UICONTROL Audience Data > Signals > Search] amd exécuter une recherche de signaux ou utilisez le Tableau de bord [](../../features/data-explorer/data-explorer-signals-dashboard.md) de signaux pour identifier les signaux à utiliser dans la nouvelle caractéristique.
1. Créez une nouvelle caractéristique basée sur les signaux souhaités.
1. Utilisez la **[!UICONTROL Backfill Options]** section **[!UICONTROL Trait Expression]** pour sélectionner l’intervalle de temps pour lequel vous souhaitez renvoyer les réalisations de caractéristiques. Les intervalles de renvoi prédéfinis incluent 1, 7, 14 et 30 jours. Vous pouvez également choisir une plage de dates personnalisée allant jusqu’à 30 jours.

   ![trait-retour](assets/signals-trait-backfill.png)

1. (Facultatif) Cliquez **[!UICONTROL Estimate Realizations]** dans la **[!UICONTROL Estimated Trait Realizations]** section pour afficher l’estimation [!UICONTROL Unique Trait Realizations] et les [!UICONTROL Total Trait Population] valeurs de la caractéristique renversée au cours des 7 derniers jours.

   ![estimation-caractéristiques-réalisations](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Il n&#39;est pas possible de renvoyer et d&#39;estimer les caractéristiques avec des expressions qui utilisent les opérateurs suivants :
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Créez la caractéristique.

Une fois que vous avez créé la caractéristique, vous verrez ses réalisations dépassées incluses dans les statistiques de réalisation.

Regardez la vidéo ci-dessous pour découvrir comment renvoyer les caractéristiques.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latence de renvoi de caractéristiques {#trait-backfilling-latency}

Les caractéristiques nouvellement créées début capturer les audiences deux à trois heures après leur création. Cependant, en raison du volume important de données qui [!DNL Audience Manager] se produisent quotidiennement, la population reconstituée n’est pas immédiatement reflétée dans les [!UICONTROL Unique Trait Realizations] graphiques et les [!UICONTROL Total Trait Population] graphiques.

L&#39;Audience Manager met à jour la population [!UICONTROL Trait Graph] avec la population dépassée dans les 48 heures suivant la création d&#39;un trait.

## Limite de renvoi de caractéristiques {#trait-backfilling-limit}

[!UICONTROL Data Explorer] vous permet de renvoyer jusqu’à 50 caractéristiques par mois, le compteur de renvoi étant réinitialisé le 1 jour de chaque mois.

>[!NOTE]
>
>Le quota de renflouement des caractéristiques n&#39;est pas reporté des mois précédents. Par exemple, si vous renseignez 30 caractéristiques ce mois-ci, le quota de renvois de caractéristiques pour le mois suivant est réinitialisé à 50, et non à 70.

## Impact sur le Rapports {#reporting-impact}

Les réalisations rétroactives des caractéristiques sont reflétées dans les [!UICONTROL Unique Trait Realizations] mesures et [!UICONTROL Total Trait Population] les mesures, à mesure que [!DNL Audience Manager] les signaux historiques deviennent des réalisations des caractéristiques.

Toutefois, les éléments [!UICONTROL Trait Graph], [!UICONTROL General Reports]et [!UICONTROL Trend Reports] ne sont pas mis à jour rétroactivement avec des mesures historiques renvoyées avant la date de création de la caractéristique.