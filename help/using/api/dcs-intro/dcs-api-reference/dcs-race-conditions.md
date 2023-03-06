---
description: Décrit comment empêcher les conditions de concurrence et la gestion des erreurs DCS.
seo-description: Describes how to prevent race conditions and DCS error handling.
seo-title: Race Conditions and Error Handling
solution: Audience Manager
title: Conditions de race et gestion des erreurs
uuid: b0aac960-6732-4e96-87a5-40ba2755e02d
feature: DCS
exl-id: bfb0b684-6b15-434d-b5ec-5f8741c0c691
source-git-commit: 25d785097228ae66d20cf2b35c8ef63fd64936c6
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 2%

---

# Conditions de race, limitation de taux et gestion des erreurs {#race-conditions-and-error-handling}

Décrit comment empêcher les conditions de concurrence et [!DNL DCS] gestion des erreurs.

## Empêcher les conditions de race {#prevent-race-conditions}

Une situation de concurrence peut se produire si vous envoyez plusieurs appels simultanément (ou dans une succession rapide) à la variable [!DNL DCS] avant qu’il ne finisse de répondre aux requêtes initiales et d’écrire des données dans le cookie de l’utilisateur. Une condition de concurrence n’est pas souhaitable, car elle peut corrompre ou remplacer incorrectement les données de cookie. Pour éviter ce problème, il est recommandé d’utiliser les méthodes suivantes :

* N’effectuez pas d’appels simultanés, ou d’appels successifs rapides, au [!DNL DCS] du même utilisateur.
* Attendez que chaque réponse revienne avant d’effectuer les appels suivants.

## Limite de débit {#rate-limiting}

Adobe peut introduire une limitation de débit s’il détecte des appels d’API DCS excessifs qui peuvent avoir un impact négatif sur la disponibilité du service.

Si la limitation de débit est activée, vous pouvez recevoir une `429 Too Many Requests` Code d’état de réponse HTTP sur vos appels DCS. Lors de la réception de cette réponse HTTP, veuillez réessayer les appels API ultérieurement.

## Gestion des erreurs {#error-handling}

La gestion des erreurs est limitée pour les requêtes non valides ou mal formées. Une requête non valide renvoie une `HTTP 200 OK` réponse et aucune donnée. En outre, la variable [!DNL DCS] arrête le traitement d’une requête, ignore les données de caractéristique et renvoie une `HTTP 200 OK` réponse lorsqu’un utilisateur :

* Exclut le suivi au niveau de l’Audience Manager ou du partenaire.
* provient d’une région géographique non valide/non sélectionnée.
* Désactive les cookies de navigateur (tous ou tiers).

Voir aussi [Codes, messages et exemples d’erreur des serveurs de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).
