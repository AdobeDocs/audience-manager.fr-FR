---
description: La page Résumé des segments affiche des détails tels que le nom, les caractéristiques dans le segment, les règles, les données de performances et les informations de mappage de destination.
seo-description: La page Résumé des segments affiche des détails tels que le nom, les caractéristiques dans le segment, les règles, les données de performances et les informations de mappage de destination.
seo-title: Vue Résumé des segments
solution: Audience Manager
title: Vue Résumé des segments
uuid: e 844 e 423-9701-42 d 4-9 ba 5-d 82 f 41358 adc
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Vue Résumé des segments {#segment-summary-view}

La [!UICONTROL Segment Summary] page affiche des détails tels que le nom, les caractéristiques du segment, les données de performances des règles et les informations de mappage de destination.

Cliquez sur un nom de segment depuis le tableau de bord principal pour accéder à sa page de résumé. Les sections récapitulatives incluent :

1. **[!UICONTROL Basic Information]:** Affiche les détails obligatoires et facultatifs spécifiés lors de la création du segment.
2. **[!UICONTROL Segment Graph]:** Affiche les données de performances sous forme graphique et pour les intervalles 1, 7, 14, 30, 60 et 90 jours. Nous expliquons les nombres de population de segments dans un [article distinct](../../features/segments/segment-builder-data.md).

   ![segments-graphique](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** Le rapport indique le nombre de personnes ou de foyers qui remplissent les critères d'un segment en comptant le nombre d'ID inter-périphériques et/ou les ID de graphique de périphériques externes liés aux périphériques qualifiés pour le segment (présenté par [!UICONTROL Total Segment Population]le). Les ID inter-périphériques et les ID de graphique de périphérique externes indiqués dans ce rapport sont utilisés pour fusionner les profils avec la règle de fusion du profil utilisée par le segment. Ce rapport s'affiche uniquement si vous avez sélectionné une source de données sur plusieurs périphériques ou un graphique de périphérique externe dans la règle de fusion du profil utilisée par le segment.

   ![segments-graphique](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager affiche uniquement [!UICONTROL Identity Type Breakdown] le rapport si des ID interterminaux sont qualifiés pour le segment.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=fre_fr)

4. **[!UICONTROL Segment Rules]:** Répertorie les caractéristiques du segment avec les règles de qualification.
5. **[!UICONTROL Destination Mappings]:** Répertorie les correspondances de destination du segment.
6. **[!UICONTROL Management Tools]:** Commandes permettant de créer, de modifier, de cloner et de supprimer des segments.