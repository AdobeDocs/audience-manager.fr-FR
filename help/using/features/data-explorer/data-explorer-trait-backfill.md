---
description: Renvoi des caractéristiques pour capturer les audiences historiques et éviter la perte de données pertinentes avant la date de création de la caractéristique.
seo-description: Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.
seo-title: Backfill Trait Realizations
title: Réalisations des caractéristiques de renvoi
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Réalisations des caractéristiques de renvoi {#backfill-trait-realizations}

Renvoi des caractéristiques pour capturer les audiences historiques et éviter la perte de données pertinentes avant la date de création de la caractéristique.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] est une fonctionnalité premium qui améliore l’expérience d’Audience Manager en déverrouillant des cas d’utilisation supplémentaires. Le renvoi nécessite une puissance de traitement supplémentaire et est disponible pour tous les clients Audience Manager à un coût incrémentiel. Veuillez contacter votre représentant commercial Adobe pour plus d’informations.

Lorsque vous créez des caractéristiques à partir de signaux inutilisés, vous pouvez choisir de renvoyer les réalisations des caractéristiques sur une période spécifique. [!DNL Audience Manager] capture les données historiques des audiences qui remplissent les critères de la nouvelle caractéristique et les stocke dans le profil correspondant. Vous pouvez voir le **[!UICONTROL Backfill Options]** dans la section [!UICONTROL Trait Expression] du **[créateur de caractéristiques](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Vous pouvez renvoyer des réalisations de caractéristiques pour les caractéristiques basées sur des règles et intégrées.

Voici comment renvoyer les réalisations des caractéristiques :

1. Accédez à [!UICONTROL Audience Data > Signals > Search] et exécutez une recherche de signaux ou utilisez le tableau de bord [Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) pour identifier les signaux à utiliser dans la nouvelle caractéristique.
1. Créez une caractéristique basée sur les signaux souhaités.
1. Utilisez le **[!UICONTROL Backfill Options]** de la section **[!UICONTROL Trait Expression]** pour sélectionner l’intervalle de temps pendant lequel vous souhaitez renvoyer les réalisations de caractéristique. Les intervalles de renvoi prédéfinis comprennent 1, 7, 14 et 30 jours. Vous pouvez également choisir une période personnalisée maximale de 30 jours.

   ![caractéristique-renvoi](assets/signals-trait-backfill.png)

1. (Facultatif) Cliquez sur **[!UICONTROL Estimate Realizations]** dans la section **[!UICONTROL Estimated Trait Realizations]** pour afficher les valeurs estimées de [!UICONTROL Unique Trait Realizations] et de [!UICONTROL Total Trait Population] pour la caractéristique renvoyée au cours des 7 derniers jours.

   ![estimation-caractéristiques-réalisations](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Le remplissage et l’estimation des caractéristiques ne sont pas disponibles pour les caractéristiques avec des expressions qui utilisent les opérateurs suivants :
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`
1. Créez la caractéristique.

Une fois la création de la caractéristique terminée, ses réalisations renvoyées sont incluses dans les statistiques de réalisation.

Regardez la vidéo ci-dessous pour une présentation vidéo sur la manière de renvoyer les caractéristiques.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latence de renvoi des caractéristiques {#trait-backfilling-latency}

Les caractéristiques nouvellement créées commencent à capturer des audiences deux à trois heures après leur création. Cependant, en raison du volume important de données que [!DNL Audience Manager] effectue quotidiennement, la population renvoyée n’est pas immédiatement répercutée dans les graphiques [!UICONTROL Unique Trait Realizations] et [!UICONTROL Total Trait Population].

Audience Manager met à jour le [!UICONTROL Trait Graph] avec la population renvoyée dans les 48 heures suivant la création de la caractéristique.

## Limite de renvoi des caractéristiques {#trait-backfilling-limit}

[!UICONTROL Data Explorer] vous permet de renvoyer jusqu’à 50 caractéristiques par mois, le compteur de renvoi étant réinitialisé le 1er jour de chaque mois.

>[!NOTE]
>
>Le quota de remplissage des caractéristiques n’est pas reporté des mois précédents. Par exemple, si vous renvoyez 30 caractéristiques ce mois-ci, le quota de renvoi de caractéristiques pour le mois suivant est réinitialisé à 50, et non à 70.

## Impact sur les rapports {#reporting-impact}

Les réalisations de caractéristiques renvoyées sont reflétées dans les mesures [!UICONTROL Unique Trait Realizations] et [!UICONTROL Total Trait Population], car [!DNL Audience Manager] transforme les signaux historiques en réalisations de caractéristiques.

Cependant, les [!UICONTROL Trait Graph], [!UICONTROL General Reports] et [!UICONTROL Trend Reports] ne sont pas mis à jour rétroactivement avec des mesures historiques renvoyées avant la date de création de la caractéristique.
