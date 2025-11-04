---
description: La page de résumé du segment affiche des détails tels que le nom, les caractéristiques du segment, les règles, les données de performances et les informations de mappage de destination.
seo-description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-title: Segment Details Page
solution: Audience Manager
title: Page Détails du segment
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: répartition des types d’identité, répartition des identités, rapports d’identité d’audience, entre appareils, ID entre appareils, ID d’appareil
feature: Segments
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Page Détails du segment {#segment-summary-view}

La page de détails d’un segment individuel fournit un aperçu des détails du segment, tels que le nom du segment, l’identifiant, les mesures de performances, les règles qui définissent le segment et les mappages de destination. Pour afficher ces détails, accédez à **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** et cliquez sur le nom du segment que vous souhaitez utiliser.

## Outils de gestion des segments {#segment-management-tools}

La partie supérieure de la page des détails du segment héberge les outils que vous pouvez utiliser pour gérer vos segments :

1. **[!UICONTROL Add New]** : utilisez cette option pour activer le [!UICONTROL Segment Builder] et créer de nouveaux segments.
2. **[!UICONTROL Edit]** : utilisez cette option pour modifier la configuration du segment actuel.
3. **[!UICONTROL Duplicate]** : utilisez cette option pour créer une copie du segment actif.
4. **[!UICONTROL Delete]** : utilisez cette option pour supprimer le segment actif de votre compte Audience Manager.
5. **[!UICONTROL Marketplace Recommendations]** : utilisez cette option pour rechercher des segments similaires à celui que vous consultez, à partir [!UICONTROL Audience Marketplace] flux de données auxquels vous n’êtes pas abonné. Consultez [Audience Marketplace pour les acheteurs de données](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) pour savoir comment naviguer sur le marché et trouver des segments similaires.

![basic-segment-information](assets/basic-segment-information.png)

## Informations sur le segment {#basics}

Sous les outils de gestion des segments, vous trouverez les informations sur les segments suivantes :

1. **[!UICONTROL Basic Information]:** affiche les détails obligatoires et facultatifs spécifiés lors de la création du segment. Consultez [Créateur de segments](segment-builder.md) pour une présentation détaillée de la signification de ces champs.
1. **[!UICONTROL Segment Graph]:** affiche les données de performances sous forme graphique et pour des intervalles fixes de 1, 7, 14, 30, 60 et 90 jours. Nous expliquons les nombres de population de segments dans un [article distinct](../../features/segments/segment-builder-data.md).

   ![segment-graph](assets/segment-graph.png)

1. **[!UICONTROL Identity Type Breakdown]:** le rapport indique le nombre de personnes ou de foyers qui remplissent les critères d’un segment en comptant le nombre d’identifiants sur plusieurs appareils et/ou d’identifiants de graphique d’appareil externe liés aux appareils qui remplissent les critères pour le segment (affichés par la [!UICONTROL Total Segment Population]). Les identifiants entre appareils et les identifiants du graphique d’appareil externe affichés dans ce rapport sont utilisés pour fusionner des profils avec la règle de fusion de profil utilisée par le segment. Ce rapport s’affiche uniquement si vous avez sélectionné une source de données entre appareils ou un graphique d’appareil externe dans la règle de fusion de profils utilisée par le segment.

   ![segment-graph](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager n’affiche le rapport [!UICONTROL Identity Type Breakdown] que si vous disposez de plusieurs identifiants d’appareil qualifiés pour le segment.

   Regardez la vidéo ci-dessous pour un aperçu de [!UICONTROL Identity Type Breakdown].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

1. **[!UICONTROL Segment Rules]:** répertorie les caractéristiques du segment avec les règles de qualification.
1. **[!UICONTROL Destination Mappings]:** répertorie les mappages de destination pour le segment.
1. **[!UICONTROL Management Tools]:** contrôles qui vous permettent de créer, modifier, cloner et supprimer des segments.
