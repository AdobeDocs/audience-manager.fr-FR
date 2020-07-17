---
description: Méthodes DELETE et POST permettant de supprimer les destinations et les mappages de segments.
seo-description: Méthodes DELETE et POST permettant de supprimer les destinations et les mappages de segments.
seo-title: Suppression de destinations
solution: Audience Manager
title: Suppression de destinations
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 7%

---


# Suppression de destinations {#delete-destinations}

`DELETE` et `POST` les méthodes permettant de supprimer les destinations et les mappages de segments.

<!-- r_delete_destinations_all.xml -->

## Supprimer une destination

Méthode `DELETE` qui supprime une destination.

>[!NOTE]
>
>Vous devez supprimer tous les mappages de segments avant de pouvoir supprimer une destination.

* Demande: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Réponse : Renvoie le code `204 No Content` en cas de réussite.

## Destinations de suppression en bloc

Supprimez plusieurs destinations avec cette `POST` méthode. Transmettez les ID de destination ( `destinationId`) avec un tableau dans le corps de la requête.

* Demande: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Réponse : Renvoie le code `204 No Content` en cas de réussite.

## Supprimer les mappages de destination par ID de mappage de segment

Méthode `POST` qui supprime les mappages de destination en fonction de l’ID de segment spécifié.

* Demande: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Réponse : Renvoie le code `204 No Content` en cas de réussite.