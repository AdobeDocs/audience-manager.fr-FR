---
description: Décrit la procédure à suivre pour éviter les conditions de concurrence et la gestion des erreurs DCS.
seo-description: Décrit la procédure à suivre pour éviter les conditions de concurrence et la gestion des erreurs DCS.
seo-title: Conditions de concurrence et gestion des erreurs
solution: Audience Manager
title: Conditions de concurrence et gestion des erreurs
uuid: b 0 aac 960-6732-4 e 96-87 a 5-40 ba 2755 e 02 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Race Conditions and Error Handling {#race-conditions-and-error-handling}

Describes how to prevent race conditions and [!UICONTROL DCS] error handling.

## Preventing Race Conditions {#prevent-race-conditions}

A race condition can occur if you send multiple calls simultaneously (or in rapid succession) to the [!UICONTROL DCS] before it finishes responding to the initial queries and writing data to the user’s cookie. Une condition de concurrence est indésirable car elle peut endommager ou incorrectement remplacer des données de cookie. En règle générale, tenez compte des méthodes suivantes pour éviter ce problème :

* Don't make simultaneous calls, or calls in rapid succession, to the [!UICONTROL DCS] from the same user.
* Attendez que chaque réponse vienne avant d'effectuer les appels suivants.

## Error Handling {#error-handling}

La gestion des erreurs est limitée pour les requêtes non valides ou mal formées. An invalid request returns an `HTTP 200 OK` response and no data. Also, the [!UICONTROL DCS] stops processing a request, discards trait data, and returns an `HTTP 200 OK` response when a user:

* Permet d'exclure le suivi au niveau d'Audience Manager ou du partenaire.
* Provient d'une zone géographique non sélectionnée/non sélectionnée.
* Désactive les cookies du navigateur (tous ou tiers).

See also, [DCS Error Codes, Messages, and Examples](../../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).