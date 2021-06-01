---
description: La page de résumé du segment affiche des détails tels que le nom, les caractéristiques du segment, les règles, les données de performances et les informations de mappage des destinations.
seo-description: La page de résumé du segment affiche des détails tels que le nom, les caractéristiques du segment, les règles, les données de performances et les informations de mappage des destinations.
seo-title: Page Détails du segment
solution: Audience Manager
title: Page Détails du segment
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: ventilation de type d’identité, ventilation d’identité, rapport d’identité d’audience, multi-appareils, identifiant multi-appareils, identifiant d’appareil
feature: 'Segments '
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# Page Détails du segment {#segment-summary-view}

La page de détails d’un segment individuel fournit un aperçu des détails du segment, tels que le nom du segment, l’identifiant, les mesures de performances, les règles qui définissent le segment et les mappages de destination. Pour afficher ces détails, accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** et cliquez sur le nom du segment à utiliser.

## Outils de gestion des segments {#segment-management-tools}

La partie supérieure de la page des détails du segment héberge les outils que vous pouvez utiliser pour gérer vos segments :

1. **[!UICONTROL Add New]**: Utilisez cette option pour activer  [!UICONTROL Segment Builder] et créer des segments.
2. **[!UICONTROL Edit]**: Utilisez cette option pour modifier la configuration du segment actuel.
3. **[!UICONTROL Duplicate]**: Utilisez cette option pour créer une copie du segment actuel.
4. **[!UICONTROL Delete]**: Utilisez cette option pour supprimer le segment actuel de votre compte d’Audience Manager.
5. **[!UICONTROL Marketplace Recommendations]**: Utilisez cette option pour trouver des segments similaires à ceux que vous affichez, à partir de flux de  [!UICONTROL Audience Marketplace] données auxquels vous n’êtes pas abonné. Voir [Audience Marketplace pour les acheteurs de données](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) pour savoir comment naviguer sur le Marketplace et trouver des segments similaires.

![basic-segment-information](assets/basic-segment-information.png)

## Informations sur le segment {#basics}

Vous trouverez ci-dessous les outils de gestion des segments contenant les informations suivantes sur les segments :

1. **[!UICONTROL Basic Information]:** affiche les détails obligatoires et facultatifs spécifiés lors de la création du segment. Voir [Créateur de segments](segment-builder.md) pour un aperçu détaillé de la signification de ces champs.
2. **[!UICONTROL Segment Graph]:** affiche les données de performances sous forme graphique et pour des intervalles de 1, 7, 14, 30, 60 et 90 jours fixes. Nous expliquons les nombres de populations de segments dans un [article distinct](../../features/segments/segment-builder-data.md).

   ![segment-graph](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** Le rapport indique le nombre de personnes ou de ménages admissibles pour un segment en comptant le nombre d’identifiants inter-appareils et/ou d’identifiants graphiques externes d’appareil liés aux appareils qualifiés pour le segment (comme illustré par  [!UICONTROL Total Segment Population]). Les identifiants multi-appareils et les identifiants graphiques de périphérique externes affichés dans ce rapport sont utilisés pour fusionner les profils avec la règle de fusion de profils utilisée par le segment. Ce rapport s’affiche uniquement si vous avez sélectionné une source de données multi-appareils ou un graphique d’appareil externe dans la règle de fusion de profils que le segment utilise.

   ![segment-graph](assets/segment-type.png)

   >[!NOTE]
   >
   >L’Audience Manager affiche uniquement le rapport [!UICONTROL Identity Type Breakdown] si des identifiants multi-appareils sont qualifiés pour le segment.

   Regardez la vidéo ci-dessous pour un aperçu de [!UICONTROL Identity Type Breakdown].
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:** répertorie les caractéristiques du segment ainsi que les règles de qualification.
5. **[!UICONTROL Destination Mappings]:** répertorie les mappages de destination pour le segment.
6. **[!UICONTROL Management Tools]:** contrôles qui vous permettent de créer, modifier, cloner et supprimer des segments.
