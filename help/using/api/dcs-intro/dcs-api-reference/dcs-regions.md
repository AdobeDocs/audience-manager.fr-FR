---
description: Le nom d’hôte du serveur DCS régional est requis pour effectuer des appels au serveur DCS. En effet, le serveur de collecte de données stocke des informations dans des centres de données situés à proximité géographique des visiteurs du site. Vos requêtes fonctionneront si vous les envoyez au mauvais serveur de collecte de données, mais ces appels sont inefficaces et peuvent retarder la réponse. Pour effectuer une demande de serveur de collecte de données, faites correspondre l’identifiant de région à son nom d’hôte régional correspondant et indiquez le nom d’hôte approprié dans votre requête.
seo-description: Le nom d’hôte du serveur DCS régional est requis pour effectuer des appels au serveur DCS. En effet, le serveur de collecte de données stocke des informations dans des centres de données situés à proximité géographique des visiteurs du site. Vos requêtes fonctionneront si vous les envoyez au mauvais serveur de collecte de données, mais ces appels sont inefficaces et peuvent retarder la réponse. Pour effectuer une demande de serveur de collecte de données, faites correspondre l’identifiant de région à son nom d’hôte régional correspondant et indiquez le nom d’hôte approprié dans votre requête.
seo-title: Identifiants de région DCS, emplacements et noms d’hôtes
solution: Audience Manager
title: Identifiants de région DCS, emplacements et noms d’hôtes
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 2%

---


# DCS Region IDs, Locations, and Host Names {#dcs-region-ids-locations-and-host-names}

Le nom d’hôte du [!DNL DCS] serveur régional est requis pour effectuer des appels vers le [!DNL DCS]. Ceci est dû au fait que les [!DNL DCS] centres de données stockent des informations qui sont géographiquement proches des visiteurs du site. Vos requêtes fonctionneront si vous les envoyez de travers [!DNL DCS], mais ces appels sont inefficaces et peuvent retarder la réponse. Pour faire une [!DNL DCS] demande, faites correspondre l’identifiant de région à son nom d’hôte régional correspondant et tapez votre requête avec le nom d’hôte approprié.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de région DCS (dcs_region) </th> 
   <th colname="col2" class="entry"> Région (et emplacement) </th> 
   <th colname="col3" class="entry"> Nom d’hôte </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID3 </p> </td> 
   <td colname="col2"> <p>Asie du Sud-Est (Singapour) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID4 </p> </td> 
   <td colname="col2"> <p>Amérique du Sud (São Paulo, Brésil) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID6 </p> </td> 
   <td colname="col2"> <p>Europe (Dublin, Irlande) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID7 </p> </td> 
   <td colname="col2"> <p>Est des États-Unis (Virginie, États-Unis) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID8 </p> </td> 
   <td colname="col2"> <p>Pacifique Sud / Océanie (Sydney, Australie) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID9 </p> </td> 
   <td colname="col2"> <p>Ouest des États-Unis (Oregon, États-Unis) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID11 </p> </td> 
   <td colname="col2"> <p>Asie (Tokyo, Japon) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID12 </p> </td> 
   <td colname="col2"> <p>Inde </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Vous pouvez également utiliser [!DNL API] des méthodes pour obtenir une liste des [!DNL DCS] régions disponibles. Voir Méthodes [d’API de région](../../../api/rest-api-main/aam-api-dcs-regions.md)DCS.