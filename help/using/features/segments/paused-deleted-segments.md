---
description: Décrit les effets sur les utilisateurs segmentés, les données et les destinations lorsque vous suspendez ou supprimez un segment actif à l’aide du créateur de segments.
seo-description: Décrit les effets sur les utilisateurs segmentés, les données et les destinations lorsque vous suspendez ou supprimez un segment actif à l’aide du créateur de segments.
seo-title: Segments en pause et supprimés
solution: Audience Manager
title: Segments en pause et supprimés
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# Segments en pause et supprimés {#paused-and-deleted-segments}

Décrit les effets sur les utilisateurs segmentés, les données et les destinations lorsque vous suspendez ou supprimez un segment actif à l’aide de [!UICONTROL Segment Builder].

## Accès aux commandes Pause et Supprimer

Passez la souris sur un nom de segment dans la liste de segments pour afficher les **[!UICONTROL pause]** icônes et **[!UICONTROL delete]** (dans la [!UICONTROL Actions] colonne). Ces fonctionnalités affectent les segments comme décrit ci-dessous.

## Fonctionnalité de segment en pause

Segment suspendu (désactivé) :

* Arrête la segmentation des nouveaux utilisateurs qualifiés.
* Conserve l’état/l’appartenance de segmentation d’un utilisateur (ne supprime pas un utilisateur du segment).
* Reste dans la liste de segments et peut être réactivé.
* N’envoie pas de données vers les destinations associées.
* Renvoie les données des rapports disponibles (jusqu’à la date de désactivation).

## Fonctionnalité de segment supprimée

Un segment supprimé :

* Arrête la segmentation des nouveaux utilisateurs qualifiés.
* Supprime les utilisateurs qualifiés de l’adhésion au segment.
* Est supprimé de la liste de segments.
* Impossible d&#39;annuler la suppression.
* N’envoie pas de données vers les destinations associées.
* Ne renvoie pas de données dans les rapports disponibles.

>[!NOTE]
>
>Vous pouvez également suspendre et supprimer des segments à l’aide d’une [!DNL API] méthode. Pour plus d’informations, voir API [](../../api/rest-api-main/rest-api-main.md)REST.