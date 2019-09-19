---
description: Les méthodes DELETE et POST permettent de supprimer les destinations et les mappages de segments.
seo-description: Les méthodes DELETE et POST permettent de supprimer les destinations et les mappages de segments.
seo-title: Supprimer les destinations
solution: Audience Manager
title: Supprimer les destinations
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Supprimer les destinations {#delete-destinations}

`DELETE` et `POST` les méthodes permettant de supprimer les destinations et les mappages de segments.

<!-- r_delete_destinations_all.xml -->

## Supprimer une destination

Méthode `DELETE` qui supprime une destination.

>[!NOTE]
>
>Vous devez supprimer tous les mappages de segments avant de pouvoir supprimer une destination.

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Réponse : Renvoie le code `204 No Content` en cas de réussite.

## Destinations de suppression en bloc

Supprimez plusieurs destinations avec cette `POST` méthode. Transmettez les ID de destination ( `destinationId`) avec un tableau dans le corps de la requête.

* Demande: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Réponse : Renvoie le code `204 No Content` en cas de réussite.

## Supprimer les correspondances de destination par ID de mappage de segment

Méthode `POST` qui supprime les mappages de destination selon l’ID de segment spécifié.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Réponse : Renvoie le code `204 No Content` en cas de réussite.