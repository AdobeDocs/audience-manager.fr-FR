---
description: Décrit comment empêcher les conditions de concurrence et la gestion des erreurs DCS.
seo-description: Décrit comment empêcher les conditions de concurrence et la gestion des erreurs DCS.
seo-title: Conditions de race et gestion des erreurs
solution: Audience Manager
title: Conditions de race et gestion des erreurs
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---


# Conditions de race et gestion des erreurs {#race-conditions-and-error-handling}

Décrit comment empêcher les conditions de race et la gestion des [!DNL DCS] erreurs.

## Prévenir les conditions raciales {#prevent-race-conditions}

Une condition de concurrence peut survenir si vous envoyez plusieurs appels simultanément (ou en succession rapide) à la [!DNL DCS] société avant qu’elle ne finisse de répondre aux requêtes initiales et d’écrire des données dans le cookie de l’utilisateur. Une condition de concurrence n’est pas souhaitable car elle peut corrompre ou remplacer incorrectement les données de cookie. Pour éviter ce problème, il est recommandé d’utiliser les méthodes suivantes :

* N&#39;appelez pas simultanément, ou n&#39;appelez pas de façon répétée, à la [!DNL DCS] même personne.
* Attendez que chaque réponse revienne avant d’effectuer les appels suivants.

## Gestion des erreurs {#error-handling}

La gestion des erreurs est limitée pour les requêtes non valides ou mal formées. Une requête non valide renvoie une `HTTP 200 OK` réponse et aucune donnée. En outre, la fonction [!DNL DCS] arrête le traitement d’une requête, ignore les données de caractéristiques et renvoie une `HTTP 200 OK` réponse lorsqu’un utilisateur :

* Permet de désactiver le suivi au niveau de l’Audience Manager ou du partenaire.
* Provient d&#39;une région géographique non valide/non sélectionnée.
* Désactive les cookies de navigateur (tous ou tiers).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).