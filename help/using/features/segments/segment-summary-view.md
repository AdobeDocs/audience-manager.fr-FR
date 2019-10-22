---
description: La page de résumé des segments affiche des détails tels que le nom, les caractéristiques du segment, les règles, les données de performances et les informations de mappage de destination.
seo-description: La page de résumé des segments affiche des détails tels que le nom, les caractéristiques du segment, les règles, les données de performances et les informations de mappage de destination.
seo-title: Affichage du résumé des segments
solution: Audience Manager
title: Affichage du résumé des segments
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: ventilation de type d’identité, ventilation d’identité, rapport d’identité d’audience
translation-type: tm+mt
source-git-commit: 345042673a9ee7abdac994d774e5c4c893a78749

---


# Affichage du résumé des segments {#segment-summary-view}

La [!UICONTROL Segment Summary] page affiche des détails tels que le nom, les caractéristiques du segment, les données de performances des règles et les informations de mappage de destination.

Cliquez sur le nom d’un segment dans le tableau de bord principal pour accéder à sa page de résumé. Les sections récapitulatives incluent :

1. **[!UICONTROL Basic Information]** : Affiche les détails obligatoires et facultatifs spécifiés lors de la création du segment.
2. **[!UICONTROL Segment Graph]** : Affiche les données de performances sous forme graphique et pour les intervalles fixes de 1, 7, 14, 30, 60 et 90 jours. Nous expliquons les chiffres de population des segments dans un article [](../../features/segments/segment-builder-data.md)distinct.

   ![segments-graphique](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]** : Le rapport montre le nombre de personnes ou de ménages qui remplissent les conditions requises pour un segment en comptant le nombre d’ID de plusieurs périphériques et/ou d’ID de graphique de périphériques externes liés aux périphériques qui remplissent les conditions requises pour le segment (comme le montre le [!UICONTROL Total Segment Population]). Les identifiants multipériphériques et les identifiants graphiques de périphériques externes affichés dans ce rapport sont utilisés pour fusionner les profils avec la règle de fusion de profil utilisée par le segment. Ce rapport s’affiche uniquement si vous avez sélectionné une source de données sur plusieurs périphériques ou un graphique de périphérique externe dans la règle de fusion de profil utilisée par le segment.

   ![segments-graphique](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager affiche le [!UICONTROL Identity Type Breakdown] rapport uniquement si vous disposez d’ID de plusieurs périphériques qualifiés pour le segment.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=fre_fr)

4. **[!UICONTROL Segment Rules]** : Répertorie les caractéristiques du segment ainsi que les règles de qualification.
5. **[!UICONTROL Destination Mappings]** : Répertorie les mappages de destination pour le segment.
6. **[!UICONTROL Management Tools]** : Commandes permettant de créer, modifier, cloner et supprimer des segments.