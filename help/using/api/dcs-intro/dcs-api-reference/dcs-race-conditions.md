---
description: Décrit comment empêcher les conditions de concurrence et la gestion des erreurs DCS.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Conditions de concurrence et gestion des erreurs
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---

# Conditions de concurrence, limitation de débit et gestion des erreurs {#race-conditions-and-error-handling}

Décrit comment empêcher les conditions de concurrence et [!DNL DCS] la gestion des erreurs.

## Prévenir les conditions de concurrence {#prevent-race-conditions}

Une condition de concurrence peut se produire si vous envoyez plusieurs appels simultanément (ou en succession rapide) au [!DNL DCS] avant qu’il ne termine de répondre aux requêtes initiales et d’écrire des données dans le cookie de l’utilisateur. Une condition de concurrence n’est pas souhaitable, car elle peut corrompre ou remplacer de manière incorrecte les données de cookie. Envisagez les méthodes suivantes pour éviter ce problème :

* N’effectuez pas d’appels simultanés, ou d’appels successifs rapides, à la [!DNL DCS] du même utilisateur.
* Attendez que chaque réponse revienne avant d’effectuer les appels suivants.

## Limitation de débit {#rate-limiting}

Adobe peut introduire une limitation de débit s’il détecte un nombre excessif d’appels API DCS, ce qui peut avoir un impact négatif sur la disponibilité du service.

Si la limitation de débit est activée, vous pouvez recevoir un code de statut de réponse HTTP `429 Too Many Requests` sur vos appels DCS. Lors de la réception de cette réponse HTTP, réessayez les appels API ultérieurement.

## Gestion des erreurs {#error-handling}

La gestion des erreurs est limitée pour les requêtes non valides ou mal formées. Une requête non valide renvoie une réponse `HTTP 200 OK` et aucune donnée. En outre, le [!DNL DCS] arrête le traitement d’une requête, ignore les données de caractéristique et renvoie une réponse `HTTP 200 OK` lorsqu’un utilisateur :

* Se désinscrit du suivi au niveau d’Audience Manager ou du partenaire.
* Provient d’une région géographique non valide/non sélectionnée.
* Désactive les cookies de navigateur (entièrement ou tiers).

Voir aussi [Codes d’erreur, messages et exemples DCS](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
