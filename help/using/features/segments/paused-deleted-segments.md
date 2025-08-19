---
description: Décrit les effets sur les utilisateurs, les données et les destinations segmentés lorsque vous suspendez ou supprimez un segment actif à l’aide du créateur de segments.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Segments en pause et supprimés
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Segments en pause et supprimés {#paused-and-deleted-segments}

Décrit les effets sur des utilisateurs, des données et des destinations segmentés lorsque vous mettez en pause ou supprimez un segment actif à l’aide de [!UICONTROL Segment Builder].

## Accès aux commandes de pause et de suppression

Passez la souris sur un nom de segment de la liste pour afficher les icônes de **[!UICONTROL pause]** et de **[!UICONTROL delete]** (dans la colonne [!UICONTROL Actions]). Ces fonctionnalités affectent les segments comme décrit ci-dessous.

## Fonctionnalité De Segment En Pause

Un segment en pause (désactivé) :

* Arrête la segmentation des nouveaux utilisateurs et utilisatrices qualifiés.
* Conserve le statut/l’appartenance de segmentation d’un utilisateur (ne supprime pas un utilisateur du segment).
* Reste dans la liste des segments et peut être réactivé.
* N’envoie pas de données aux destinations associées.
* Renvoie les données des rapports disponibles (jusqu’à la date de désactivation).

## Fonctionnalité de segment supprimé

Un segment supprimé :

* Arrête la segmentation des nouveaux utilisateurs et utilisatrices qualifiés.
* Supprime les utilisateurs qualifiés de l’appartenance à un segment.
* Est supprimé de la liste des segments.
* Impossible d’annuler la suppression.
* N’envoie pas de données aux destinations associées.
* Ne renvoie pas de données dans les rapports disponibles.

>[!NOTE]
>
>Vous pouvez également suspendre et supprimer des segments à l’aide d’une méthode [!DNL API]. Pour plus d’informations, voir [API REST](../../api/rest-api-main/rest-api-main.md).
