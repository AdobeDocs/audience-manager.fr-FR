---
description: Le nom d’hôte du serveur DCS régional est requis pour effectuer des appels au serveur DCS. En effet, le serveur de collecte de données stocke des informations dans des centres de données qui sont proches géographiquement des visiteurs du site. Vos requêtes fonctionneront si vous les envoyez au mauvais serveur de collecte de données, mais ces appels sont inefficaces et peuvent retarder la réponse. Pour effectuer une requête DCS, faites correspondre l’identifiant de région à son nom d’hôte régional correspondant et créez votre requête avec le nom d’hôte approprié.
seo-description: The regional DCS server host name is required to make calls to the DCS. This is because the DCS stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong DCS, but these calls are inefficient and can delay the response. To make a DCS request, match the region ID to its corresponding regional host name and form your query with the proper host name.
seo-title: DCS Region IDs, Locations, and Host Names
solution: Audience Manager
title: Identifiants de zone géographique, emplacements et noms d’hôte du serveur de collecte de données
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---

# Identifiants de zone géographique, emplacements et noms d’hôte du serveur de collecte de données {#dcs-region-ids-locations-and-host-names}

Le nom d’hôte de serveur régional [!DNL DCS] est nécessaire pour effectuer des appels vers [!DNL DCS]. En effet, [!DNL DCS] stocke des informations dans des centres de données qui sont géographiquement proches des visiteurs du site. Vos requêtes fonctionneront si vous les envoyez au mauvais [!DNL DCS], mais ces appels sont inefficaces et peuvent retarder la réponse. Pour effectuer une requête [!DNL DCS], faites correspondre l’identifiant de région à son nom d’hôte régional correspondant et créez votre requête avec le nom d’hôte approprié.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Identifiant de région DCS (dcs_region) </th> 
   <th colname="col2" class="entry"> Région (et emplacement) </th> 
   <th colname="col3" class="entry"> Nom d’hôte </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>Asie du Sud-Est (Singapour) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 4 </p> </td> 
   <td colname="col2"> <p>Amérique du Sud (São Paulo, Brésil) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>Europe (Dublin, Irlande) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>Est des États-Unis (Virginie, États-Unis) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>Pacifique Sud/Océanie (Sydney, Australie) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>Ouest des États-Unis (Oregon, États-Unis) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>Asie (Tokyo, Japon) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID 12 </p> </td> 
   <td colname="col2"> <p>Inde </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Vous pouvez également utiliser des méthodes [!DNL API] pour obtenir une liste des régions [!DNL DCS] disponibles. Voir [Méthodes d’API de région DCS](../../../api/rest-api-main/aam-api-dcs-regions.md).
