---
description: Le nom d'hôte du serveur DCS régional est requis pour effectuer des appels au serveur de collecte de données. Cela est dû au fait que le serveur de collecte de données stocke les informations dans les centres de données proches des visiteurs du site. Vos requêtes fonctionnent si vous les envoyez au serveur DCS incorrect, mais ces appels sont inefficaces et peuvent retarder la réponse. Pour effectuer une requête DCS, faites correspondre l'identifiant de région à son nom d'hôte régional correspondant et formulez votre requête avec le nom d'hôte approprié.
seo-description: Le nom d'hôte du serveur DCS régional est requis pour effectuer des appels au serveur de collecte de données. Cela est dû au fait que le serveur de collecte de données stocke les informations dans les centres de données proches des visiteurs du site. Vos requêtes fonctionnent si vous les envoyez au serveur DCS incorrect, mais ces appels sont inefficaces et peuvent retarder la réponse. Pour effectuer une requête DCS, faites correspondre l'identifiant de région à son nom d'hôte régional correspondant et formulez votre requête avec le nom d'hôte approprié.
seo-title: Identifiants de région de DCS, emplacements et noms d'hôtes
solution: Audience Manager
title: Identifiants de région de DCS, emplacements et noms d'hôtes
uuid: ad 150 ffe -4583-472 b-ac 8 b-fb 900 a 7966 e 4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# DCS Region IDs, Locations, and Host Names {#dcs-region-ids-locations-and-host-names}

The regional [!UICONTROL DCS] server host name is required to make calls to the [!UICONTROL DCS]. This is because the [!UICONTROL DCS] stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong [!UICONTROL DCS], but these calls are inefficient and can delay the response. To make a [!UICONTROL DCS] request, match the region ID to its corresponding regional host name and form your query with the proper host name.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Identifiant de région DCS (dcs_ region) </th> 
   <th colname="col2" class="entry"> Région (et emplacement) </th> 
   <th colname="col3" class="entry"> Nom d'hôte </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>Asie du Sud-Est (Singapour) </p> </td> 
   <td colname="col3"> <p> <code> apse. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>Amérique du Sud (São Paulo, Brésil) </p> </td> 
   <td colname="col3"> <p> <code> sae. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>Europe (Dublin, Irlande) </p> </td> 
   <td colname="col3"> <p> <code> irl 1. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>East East (Virginie, Etats-Unis) </p> </td> 
   <td colname="col3"> <p> <code> use. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>Pacifique (Pacifique)/Océanie (Sydney, Australie) </p> </td> 
   <td colname="col3"> <p> <code> apse 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>Ouest des Etats-Unis (Oregon, Etats-Unis) </p> </td> 
   <td colname="col3"> <p> <code> usw 2. demdex. net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>Asie (Tokyo, Japon) </p> </td> 
   <td colname="col3"> <p> <code> tyo 3. demdex. net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>Inde </p> </td> 
   <td colname="col3"> <p> <code> ind 1. demdex. net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

You can also use [!DNL API] methods to get a list of the available [!UICONTROL DCS] regions. See [DCS Region API Methods](../../../api/rest-api-main/aam-api-dcs-regions.md).