---
description: La page de résumé du segment affiche des détails tels que le nom, les caractéristiques du segment, les règles, les données de performances et les informations de mappage des destinations.
seo-description: La page de résumé du segment affiche des détails tels que le nom, les caractéristiques du segment, les règles, les données de performances et les informations de mappage des destinations.
seo-title: Page Détails du segment
solution: Audience Manager
title: Page Détails du segment
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
translation-type: tm+mt
source-git-commit: 3b56d7ecdef4375bf3b007fa9b325618c701c174
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---


# Page Détails du segment {#segment-summary-view}

La page de détails d’un segment individuel fournit un aperçu des détails du segment, tels que le nom du segment, l’ID, les mesures de performances, les règles qui définissent le segment et les mappages de destination. Pour vue ces détails, cliquez sur **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** et cliquez sur le nom du segment à utiliser.

## Outils de gestion des segments {#segment-management-tools}

La partie supérieure de la page Détails du segment héberge les outils que vous pouvez utiliser pour gérer vos segments :

1. **[!UICONTROL Add New]**: Utilisez cette option pour activer les segments [!UICONTROL Segment Builder] et créer de nouveaux segments.
2. **[!UICONTROL Edit]**: Utilisez cette option pour modifier la configuration du segment actuel.
3. **[!UICONTROL Duplicate]**: Utilisez cette option pour créer une copie du segment actuel.
4. **[!UICONTROL Delete]**: Utilisez cette option pour supprimer le segment actuel de votre compte Audience Manager.
5. **[!UICONTROL Marketplace Recommendations]**: Utilisez cette option pour trouver des segments similaires à celui que vous consultez, à partir de flux de [!UICONTROL Audience Marketplace] données auxquels vous n’êtes pas abonné. Voir [Audience Marketplace pour les acheteurs](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) de données pour savoir comment naviguer sur le Marketplace et trouver des segments similaires.

![information-segment-de-base](assets/basic-segment-information.png)

## Informations sur le segment {#basics}

Sous les outils de gestion des segments, vous trouverez les informations suivantes sur les segments :

1. **[!UICONTROL Basic Information]:**Affiche les détails obligatoires et facultatifs spécifiés lors de la création du segment. Voir Créateur[de](segment-builder.md)segments pour une présentation détaillée de la signification de ces champs.
2. **[!UICONTROL Segment Graph]:**Affiche les données de performances sous forme graphique et pour les intervalles fixes de 1, 7, 14, 30, 60 et 90 jours. Nous expliquons les chiffres de population des segments dans un article[](../../features/segments/segment-builder-data.md)distinct.

   ![segment-graphique](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:**Le rapport montre le nombre de personnes ou de ménages admissibles pour un segment en comptant le nombre d’ID de graphique de périphériques et/ou externes liés aux périphériques qui remplissent les critères du segment (indiqués par le[!UICONTROL Total Segment Population]). Les identifiants multipériphériques et les identifiants graphiques de périphériques externes affichés dans ce rapport sont utilisés pour fusionner des profils avec la règle de fusion de profils utilisée par le segment. Ce rapport s’affiche uniquement si vous avez sélectionné une source de données sur plusieurs périphériques ou un graphique de périphérique externe dans la règle de fusion de profil utilisée par le segment.

   ![segment-graphique](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager affiche le [!UICONTROL Identity Type Breakdown] rapport uniquement si les ID de plusieurs périphériques sont qualifiés pour le segment.

   Regardez la vidéo ci-dessous pour un aperçu de [!UICONTROL Identity Type Breakdown].
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:**Caractéristiques des Listes dans le segment avec les règles de qualification.
5. **[!UICONTROL Destination Mappings]:**Mappages de destination des Listes pour le segment.
6. **[!UICONTROL Management Tools]:**Contrôles qui vous permettent de créer, modifier, cloner et supprimer des segments.