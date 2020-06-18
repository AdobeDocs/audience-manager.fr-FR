---
description: Cette section décrit comment analyser une réponse du serveur de collecte de données afin de récupérer les ID de visiteur et de région requis pour effectuer des appels en temps réel au serveur de collecte de données.
seo-description: Cette section décrit comment analyser une réponse du serveur de collecte de données afin de récupérer les ID de visiteur et de région requis pour effectuer des appels en temps réel au serveur de collecte de données.
seo-title: Obtention des ID utilisateur et des régions à partir d’une réponse DCS
solution: Audience Manager
title: Obtention des ID utilisateur et des régions à partir d’une réponse DCS
uuid: 08036045-3b26-4d40-8e94-7d0884048683
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 6%

---


# Get User IDs and Regions From a DCS Response {#get-user-ids-and-regions-from-a-dcs-response}

Cette section décrit comment analyser une [!DNL DCS] réponse afin de récupérer les ID de visiteur et de région requis pour effectuer des appels en temps réel vers le [!DNL DCS].

## ID d’utilisateur et de région {#user-region-ids}

Une [!DNL DCS] réponse contient des données sur les visiteurs de votre site. Vous avez besoin de l’ID de visiteur et de région avant de pouvoir effectuer des appels serveur à serveur au [!DNL DCS].

* L’ID utilisateur est requis pour identifier et associer des données à un visiteur particulier.
* L’identifiant de région est requis car il est lié à un nom de serveur régional, auquel vous devez envoyer des données au [!DNL DCS]serveur. Il [!DNL DCS] stocke les informations dans les centres de données qui sont géographiquement les plus proches des visiteurs du site. Voir [ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (DCS Region IDs, Locations, and Host Names).

Ces paramètres sont décrits ci-dessous. Le code en *italique* représente un espace réservé de variable.

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
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemple de réponse {#sample-response}

Cette réponse simple montre la région `UUID` et la région `ID`. Remarque : il s’agit uniquement d’exemples de données. Vos fichiers journaux peuvent être de plus en plus longs et complexes.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Étapes suivantes {#next-steps}

Une fois que vous disposez de l’ID utilisateur et du nom de serveur régional, vous pouvez début l’envoi et la réception de [!DNL DCS] données. Voir [Exécution d’appels](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)d’API DCS.
