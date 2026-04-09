---
description: Les méthodes DELETE et POST qui vous permettent de supprimer des destinations et des mappages de segments.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Supprimer les destinations
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
TQID: https://experienceleague.adobe.com/hONQoLCrSxcMnDY7yPf-RX22Etj3WIykBhKEx1IyRMo
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 104
ht-degree: 0%

---

# Supprimer les destinations {#delete-destinations}

`DELETE` et méthodes de `POST` qui vous permettent de supprimer des destinations et des mappages de segments.

<!-- r_delete_destinations_all.xml -->

## Suppression d’une destination

Une méthode `DELETE` qui supprime une destination.

>[!NOTE]
>
>Vous devez supprimer tous les mappages de segments avant de pouvoir supprimer une destination.

* Demande : `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Réponse : renvoie le code `204 No Content` en cas de réussite.

## Supprimer des destinations en bloc

Supprimez plusieurs destinations avec cette méthode `POST`. Transmettez les identifiants de destination ( `destinationId`) avec un tableau dans le corps de la requête.

* Demande : `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Réponse : renvoie le code `204 No Content` en cas de réussite.

## Supprimer les mappages de destination par identifiant de mappage de segments

Une méthode `POST` qui supprime les mappages de destination en fonction de l’identifiant de segment spécifié.

* Demande : `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Réponse : renvoie le code `204 No Content` en cas de réussite.
