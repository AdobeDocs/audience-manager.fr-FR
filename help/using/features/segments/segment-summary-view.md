---
description: La page de résumé des segments affiche des détails tels que le nom, les caractéristiques du segment, les règles, les données de performances et les informations de mappage de destination.
seo-description: La page de résumé des segments affiche des détails tels que le nom, les caractéristiques du segment, les règles, les données de performances et les informations de mappage de destination.
seo-title: Page Détails du segment
solution: Audience Manager
title: Page Détails du segment
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: ventilation de type d’identité, ventilation d’identité, rapport d’identité d’audience
translation-type: tm+mt
source-git-commit: 51f38819bfbc72c2588f63a63fb8ba2e963919ff

---


# Page Détails du segment {#segment-summary-view}

La page de détails d’un segment individuel fournit un aperçu des détails du segment, tels que le nom du segment, l’ID, les mesures de performances, les règles qui définissent le segment et les mappages de destination. Pour afficher ces détails, sélectionnez **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Segments]** et cliquez sur le nom du segment à utiliser.

## Outils de gestion des segments {#segment-management-tools}

La partie supérieure de la page Détails du segment héberge les outils que vous pouvez utiliser pour gérer vos segments :

1. **[!UICONTROL Add New]**: Utilisez cette option pour activer [!UICONTROL Segment Builder] et créer de nouveaux segments.
2. **[!UICONTROL Edit]**: Utilisez cette option pour modifier la configuration du segment actuel.
3. **[!UICONTROL Duplicate]**: Utilisez cette option pour créer une copie du segment actuel.
4. **[!UICONTROL Delete]**: Utilisez cette option pour supprimer le segment actuel de votre compte Audience Manager.
5. **[!UICONTROL Marketplace Recommendations]**: Utilisez cette option pour rechercher des segments similaires à celui que vous consultez, à partir de [!UICONTROL Audience Marketplace] flux de données auxquels vous n’êtes pas abonné. Voir [Audience Marketplace pour les acheteurs](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) de données pour savoir comment naviguer sur le Marketplace et trouver des segments similaires.

![basic-segment-information](assets/basic-segment-information.png)

## Informations sur le segment {#basics}

Sous les outils de gestion des segments, vous trouverez les informations suivantes sur les segments :

1. **[!UICONTROL Basic Information]** : Affiche les détails obligatoires et facultatifs spécifiés lors de la création du segment. Voir Créateur [de](segment-builder.md) segments pour une présentation détaillée de la signification de ces champs.
2. **[!UICONTROL Segment Graph]** : Affiche les données de performances sous forme graphique et pour les intervalles fixes de 1, 7, 14, 30, 60 et 90 jours. Nous expliquons les chiffres de population des segments dans un article [](../../features/segments/segment-builder-data.md)distinct.

   ![segments-graphique](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]** : Le rapport montre le nombre de personnes ou de ménages qui remplissent les conditions requises pour un segment en comptant le nombre d’ID de plusieurs périphériques et/ou d’ID de graphique de périphériques externes liés aux périphériques qui remplissent les conditions requises pour le segment (comme le montre le [!UICONTROL Total Segment Population]). Les identifiants multipériphériques et les identifiants graphiques de périphériques externes affichés dans ce rapport sont utilisés pour fusionner les profils avec la règle de fusion de profil utilisée par le segment. Ce rapport s’affiche uniquement si vous avez sélectionné une source de données sur plusieurs périphériques ou un graphique de périphérique externe dans la règle de fusion de profil utilisée par le segment.

   ![segments-graphique](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager affiche le [!UICONTROL Identity Type Breakdown] rapport uniquement si vous disposez d’ID de plusieurs périphériques qualifiés pour le segment.

   Regardez la vidéo ci-dessous pour un aperçu de [!UICONTROL Identity Type Breakdown].
   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=fre_fr)

4. **[!UICONTROL Segment Rules]** : Répertorie les caractéristiques du segment ainsi que les règles de qualification.
5. **[!UICONTROL Destination Mappings]** : Répertorie les mappages de destination pour le segment.
6. **[!UICONTROL Management Tools]** : Commandes permettant de créer, modifier, cloner et supprimer des segments.