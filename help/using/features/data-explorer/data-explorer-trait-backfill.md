---
description: Renseignez les réalisations de caractéristiques pour capturer les audiences historiques et éviter la perte de données pertinentes avant la date de création d’une caractéristique.
seo-description: Renseignez les réalisations de caractéristiques pour capturer les audiences historiques et éviter la perte de données pertinentes avant la date de création d’une caractéristique.
seo-title: Renvoi des caractéristiques
title: Renvoi des caractéristiques
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: 0eb6a6f67d87377a044b18118fac0185219b0347

---


# Renvoi des caractéristiques {#backfill-trait-realizations}

Renseignez les réalisations de caractéristiques pour capturer les audiences historiques et éviter la perte de données pertinentes avant la date de création d’une caractéristique.

[!UICONTROL Data Explorer Trait Backfill] est une fonctionnalité Premium qui améliore l’expérience d’Audience Manager en déverrouillant d’autres cas d’utilisation. Le renvoi nécessite une puissance de traitement supplémentaire et est disponible pour tous les clients d’Audience Manager à un coût incrémentiel. Pour plus d’informations, contactez votre représentant commercial Adobe.

Lorsque vous créez des caractéristiques à partir de signaux inutilisés, vous pouvez choisir de renvoyer les réalisations de caractéristiques sur une période spécifique. [!DNL Audience Manager] capture les données d’historique sur les audiences qui remplissent les critères pour la nouvelle caractéristique et les stocke dans le profil correspondant. Vous pouvez voir la **[!UICONTROL Backfill Options]** section dans la [!UICONTROL Trait Expression] section du Créateur de **[caractéristiques](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Vous pouvez renvoyer les réalisations de caractéristiques pour les caractéristiques basées sur des règles et les caractéristiques intégrées.

Voici comment renvoyer des réalisations de caractéristiques :

1. Accédez à [!UICONTROL Audience Data > Signals > Search] et exécutez une recherche de signaux ou utilisez le tableau de bord des [signaux](../../features/data-explorer/data-explorer-signals-dashboard.md) pour identifier les signaux à utiliser dans la nouvelle caractéristique.
1. Créez une nouvelle caractéristique en fonction des signaux souhaités.
1. Utilisez la **[!UICONTROL Backfill Options]** section **[!UICONTROL Trait Expression]** pour sélectionner l’intervalle de temps pour lequel vous souhaitez renvoyer les réalisations de caractéristiques. Les intervalles de renvoi prédéfinis comprennent 1, 7, 14 et 30 jours. Vous pouvez également choisir une plage de dates personnalisée allant jusqu’à 30 jours.

   ![trait-renvoi](assets/signals-trait-backfill.png)

1. (Facultatif) Cliquez **[!UICONTROL Estimate Realizations]** dans la **[!UICONTROL Estimated Trait Realizations]** section pour afficher l’estimation [!UICONTROL Unique Trait Realizations] et les [!UICONTROL Total Trait Population] valeurs de la caractéristique renversée au cours des 7 derniers jours.

   ![estimation-caractéristiques-réalisations](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Le renvoi et l’estimation des caractéristiques ne sont pas disponibles pour les caractéristiques avec des expressions qui utilisent les opérateurs suivants :
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Créez la caractéristique.

Une fois que vous avez créé le trait, vous verrez ses réalisations empilées incluses dans les statistiques de réalisation.

Regardez la vidéo ci-dessous pour découvrir comment renvoyer les caractéristiques.

[!VIDEO](https://video.tv.adobe.com/v/25169/?captions=fre_fr)

## Latence de renvoi de caractéristiques {#trait-backfilling-latency}

Newly created traits start capturing audiences two to three hours after creation. However, due to the large volume of data that  performs on a daily basis, the backfilled population is not immediately reflected in the  and  graphs.[!DNL Audience Manager][!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population]

Audience Manager updates the  with the backfilled population within 48 hours from trait creation.[!UICONTROL Trait Graph]

## Trait Backfilling Limit {#trait-backfilling-limit}

[!UICONTROL Data Explorer] allows you to backfill up to 50 traits per month, with the backfill counter being reset on the 1 day of each month.

>[!NOTE]
>
>Trait backfilling quota does not carry over from previous months. E.g., if you backfill 30 traits this month, the trait backfill quota for the next month is reset to 50, not 70.

## Impact on Reporting {#reporting-impact}

Backfilled trait realizations are reflected in the  and  metrics, as  turns historical signals into trait realizations.[!UICONTROL Unique Trait Realizations][!UICONTROL Total Trait Population][!DNL Audience Manager]

However, the , , and  are not updated retroactively with historical metrics backfilled before the trait creation date.[!UICONTROL Trait Graph][!UICONTROL General Reports][!UICONTROL Trend Reports]