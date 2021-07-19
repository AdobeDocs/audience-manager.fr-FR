---
description: Décrit comment empêcher les conditions de concurrence et la gestion des erreurs DCS.
seo-description: Décrit comment empêcher les conditions de concurrence et la gestion des erreurs DCS.
seo-title: Conditions de race et gestion des erreurs
solution: Audience Manager
title: Conditions de race et gestion des erreurs
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 7%

---

# Conditions de race et gestion des erreurs {#race-conditions-and-error-handling}

Décrit comment empêcher les conditions de concurrence et la gestion des erreurs [!DNL DCS].

## Empêcher les conditions de race {#prevent-race-conditions}

Une condition de concurrence peut se produire si vous envoyez plusieurs appels simultanément (ou dans une succession rapide) à la balise [!DNL DCS] avant qu’elle ne finisse de répondre aux requêtes initiales et d’écrire des données dans le cookie de l’utilisateur. Une condition de concurrence n’est pas souhaitable, car elle peut corrompre ou remplacer incorrectement les données de cookie. Pour éviter ce problème, il est recommandé d’utiliser les méthodes suivantes :

* N’effectuez pas d’appels simultanés, ou d’appels successifs rapides, à la [!DNL DCS] du même utilisateur.
* Attendez que chaque réponse revienne avant d’effectuer les appels suivants.

## Gestion des erreurs {#error-handling}

La gestion des erreurs est limitée pour les requêtes non valides ou mal formées. Une requête non valide renvoie une réponse `HTTP 200 OK` et aucune donnée. En outre, la fonction [!DNL DCS] arrête le traitement d’une requête, ignore les données de caractéristiques et renvoie une réponse `HTTP 200 OK` lorsqu’un utilisateur :

* Exclut le suivi au niveau de l’Audience Manager ou du partenaire.
* provient d’une région géographique non valide/non sélectionnée.
* Désactive les cookies de navigateur (tous ou tiers).

Voir aussi [Codes d’erreur, messages et exemples DCS](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
