---
description: Méthodes de DELETE et de POST qui vous permettent de supprimer des destinations et des mappages de segments.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Suppression de destinations
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---

# Suppression de destinations {#delete-destinations}

Les méthodes `DELETE` et `POST` qui vous permettent de supprimer des destinations et des mappages de segments.

<!-- r_delete_destinations_all.xml -->

## Suppression d’une destination

Une méthode `DELETE` qui supprime une destination.

>[!NOTE]
>
>Vous devez supprimer tous les mappages de segments avant de pouvoir supprimer une destination.

* Requête : `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Réponse : renvoie le code `204 No Content` en cas de réussite.

## Suppression de destinations en bloc

Supprimez plusieurs destinations avec cette méthode `POST`. Transmettez les identifiants de destination ( `destinationId`) avec un tableau dans le corps de la requête.

* Requête : `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Réponse : renvoie le code `204 No Content` en cas de réussite.

## Suppression des mappages de destinations par identifiant de mappage de segment

Une méthode `POST` qui supprime les mappages de destination en fonction de l’identifiant de segment spécifié.

* Requête : `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Réponse : renvoie le code `204 No Content` en cas de réussite.
