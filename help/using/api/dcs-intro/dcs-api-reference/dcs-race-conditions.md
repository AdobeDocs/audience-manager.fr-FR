---
description: Décrit comment empêcher les conditions de concurrence et la gestion des erreurs DCS.
seo-description: Décrit comment empêcher les conditions de concurrence et la gestion des erreurs DCS.
seo-title: Conditions de race et gestion des erreurs
solution: Audience Manager
title: Conditions de race et gestion des erreurs
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Conditions de race et gestion des erreurs {#race-conditions-and-error-handling}

Décrit comment empêcher les conditions de concurrence et la gestion des [!UICONTROL DCS] erreurs.

## Prévenir les conditions raciales {#prevent-race-conditions}

Une condition de concurrence peut survenir si vous envoyez plusieurs appels simultanément (ou par succession rapide) à la [!UICONTROL DCS] société avant qu’elle ne finisse de répondre aux requêtes initiales et d’écrire des données dans le cookie de l’utilisateur. Une condition de concurrence n’est pas souhaitable car elle peut corrompre ou écraser incorrectement les données de cookie. Il est recommandé d’utiliser les méthodes suivantes pour éviter ce problème :

* N’appelez pas simultanément, ou n’appelez pas de manière succédante, à la [!UICONTROL DCS] même personne.
* Attendez que chaque réponse revienne avant d’effectuer les appels suivants.

## Gestion des erreurs {#error-handling}

La gestion des erreurs est limitée pour les requêtes non valides ou mal formées. Une requête non valide renvoie une `HTTP 200 OK` réponse et aucune donnée. En outre, la [!UICONTROL DCS] méthode arrête le traitement d’une requête, ignore les données de caractéristiques et renvoie une `HTTP 200 OK` réponse lorsqu’un utilisateur :

* Désactive le suivi au niveau d’Audience Manager ou du partenaire.
* Provient d’une région géographique non valide/non sélectionnée.
* Désactive les cookies du navigateur (tous les cookies ou tiers).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).