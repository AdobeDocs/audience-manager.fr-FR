---
description: Les méthodes DELETE et POST permettent de supprimer des destinations et des mappages de segments.
seo-description: Les méthodes DELETE et POST permettent de supprimer des destinations et des mappages de segments.
seo-title: Supprimer les destinations
solution: Audience Manager
title: Supprimer les destinations
uuid: 38 fb 2228-e 564-49 a 3-9930-3139 f 8799 a 8 f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Delete Destinations {#delete-destinations}

`DELETE` et `POST` les méthodes qui vous permettent de supprimer des destinations et des mappages de segments.

<!-- r_delete_destinations_all.xml -->

## Supprimer une destination

`DELETE` Méthode qui supprime une destination.

>[!NOTE]
>
>Vous devez supprimer tous les mappages de segments avant de pouvoir supprimer une destination.

* Request: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Response: Returns code `204 No Content` if successful.

## Destinations de suppression en masse

Remove multiple destinations with this `POST` method. Pass in destination IDs ( `destinationId`) with an array in the request body.

* Demande: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Response: Returns code `204 No Content` if successful.

## Supprimer les correspondances de destination par identifiant de mappage de segment

`POST` Méthode qui supprime les correspondances de destination selon l'identifiant de segment spécifié.

* Request: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Response: Returns code `204 No Content` if successful.