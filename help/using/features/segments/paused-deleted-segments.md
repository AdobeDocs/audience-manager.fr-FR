---
description: Décrit les effets des utilisateurs segmentés, des données et des destinations lorsque vous interrompez ou supprimez un segment actif à l'aide du Créateur de segments.
seo-description: Décrit les effets des utilisateurs segmentés, des données et des destinations lorsque vous interrompez ou supprimez un segment actif à l'aide du Créateur de segments.
seo-title: Segments en pause et supprimés
solution: Audience Manager
title: Segments en pause et supprimés
uuid: 88 efe 4 af-f 9 a 4-4 bce -920 a -352 bd 4 d 505 dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Paused and Deleted Segments {#paused-and-deleted-segments}

Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using [!UICONTROL Segment Builder].

## Accès aux commandes Pause et Supprimer

Hover over a segment name in the segments list to expose the **[!UICONTROL pause]** and **[!UICONTROL delete]** icons (in the [!UICONTROL Actions] column). Ces fonctionnalités affectent les segments comme décrit ci-dessous.

## Fonctionnalité de segment en pause

Segment suspendu (désactivé) :

* Arrête la segmentation des nouveaux utilisateurs qualifiés.
* Conserve l&#39;état/l&#39;appartenance à la segmentation d&#39;un utilisateur (ne supprime pas un utilisateur du segment).
* Reste dans la liste des segments et peut être réactivé.
* N&#39;envoie pas de données aux destinations associées.
* Renvoie les données dans les rapports disponibles (jusqu&#39;à la date de désactivation).

## Fonctionnalité de segment supprimée

Segment supprimé :

* Arrête la segmentation des nouveaux utilisateurs qualifiés.
* supprime les utilisateurs qualifiés de l&#39;appartenance aux segments.
* Est supprimé de la liste de segments.
* Ne peut pas être non supprimé.
* N&#39;envoie pas de données aux destinations associées.
* Ne renvoie pas de données dans les rapports disponibles.

>[!NOTE]
>
>You can also pause and delete segments using an [!DNL API] method. For more information, see [REST APIs](../../api/rest-api-main/rest-api-main.md).