---
description: Cette section décrit comment analyser une réponse DCS pour récupérer les ID de visiteur et de région requis pour effectuer des appels en temps réel au serveur de collecte de données.
seo-description: Cette section décrit comment analyser une réponse DCS pour récupérer les ID de visiteur et de région requis pour effectuer des appels en temps réel au serveur de collecte de données.
seo-title: Obtention de l'utilisateur - Identifiants et régions à partir d'une réponse DCS
solution: Audience Manager
title: Obtention de l'utilisateur - Identifiants et régions à partir d'une réponse DCS
uuid: 08036045-3 b 26-4 d 40-8 e 94-7 d 0884048683
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

This section describes how to parse a [!UICONTROL DCS] response to retrieve the visitor and region IDs required to make real-time calls to the [!UICONTROL DCS].

## User and Region IDs {#user-region-ids}

A [!UICONTROL DCS] response contains data about your site visitors. You need the visitor and region ID before you can make server-to-server calls to the [!UICONTROL DCS].

* L'utilisateur - id est requis pour identifier et associer des données à un visiteur particulier.
* The region ID is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. Voir [ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (DCS Region IDs, Locations, and Host Names).

Ces paramètres sont décrits ci-dessous. Code in *italics* represents a variable placeholder.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Type de données </th> 
   <th colname="col3" class="entry"> Exemple </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>« uuid » : <i>user - id</i></code></span> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p> <code> « uuid » : " 123456789 "</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>« dcs_ region » :<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> « dcs_ region » : 9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemple de réponse {#sample-response}

This simple response shows the `UUID` and region `ID`. Remarque : il s'agit uniquement de données d'exemple. Vos fichiers journaux peuvent être plus longs et plus complexes.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Étapes suivantes {#next-steps}

Once you have the user ID and regional server name, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
