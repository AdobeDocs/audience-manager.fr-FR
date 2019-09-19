---
description: Les clients du service d’ID doivent consulter cette section pour savoir comment lire le cookie visiteur pour connaître les ID requis pour effectuer des appels à l’API DCS.
seo-description: Les clients du service d’ID doivent consulter cette section pour savoir comment lire le cookie visiteur pour connaître les ID requis pour effectuer des appels à l’API DCS.
seo-title: Obtention des ID utilisateur et des régions via le service d’ID Experience Cloud
solution: Audience Manager
title: Obtention des ID utilisateur et des régions via le service d’ID Experience Cloud
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Obtention des ID utilisateur et des régions via le service d’ID Experience Cloud {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Les clients du service d’ID doivent consulter cette section pour savoir comment lire le cookie visiteur pour connaître les ID requis pour effectuer des appels [!UICONTROL DCS] d’API.

## Obtention de l’ID utilisateur à partir du cookie du service d’ID {#get-user-ids-from-service-cookie}

Le service [d’ID](https://marketing.adobe.com/resources/help/en_US/mcvid/) Experience Cloud attribue des identifiants de visiteur et de région aux utilisateurs qui se rendent sur votre site Web. Ces identifiants identifient les utilisateurs dans toutes les solutions du [!DNL Experience Cloud] et ils sont nécessaires si vous souhaitez effectuer des [!UICONTROL DCS] appels.

* Le [!UICONTROL user ID] est requis pour identifier et associer des données à un visiteur particulier.
* La [!UICONTROL region ID] valeur est requise car elle est liée à un nom de serveur régional, auquel vous devez envoyer des données au [!UICONTROL DCS]. Il [!UICONTROL DCS] stocke les informations dans les centres de données qui sont géographiquement les plus proches des visiteurs du site. Voir [ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (DCS Region IDs, Locations, and Host Names).

Les clients du service d’ID peuvent extraire ces informations du cookie du service d’ID ou en appelant une fonction. Le tableau ci-dessous décrit les tâches ou les étapes à effectuer pour commencer.

Le code en *italique* représente un espace réservé de variable.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tâche </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Vérifiez votre état <span class="keyword"> Experience Cloud</span> .</b> </p> </td> 
   <td colname="col2"> <p>Vous avez besoin d’un compte <span class="keyword"> Experience Cloud</span> pour utiliser le service d’ID. Si vous avez un compte <span class="keyword"> Experience Cloud</span> , super ! </p> <p> Si vous ne faites pas partie d’ <span class="keyword"> Experience Cloud</span>, inscrivez-vous. Nous aimerions vous avoir et il y a toujours de la place pour plus. Pour plus d’informations sur la configuration d’un compte, voir <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=core_services.html" format="https" scope="external"> Services principaux - Activation de vos solutions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>Le service <span class="keyword"> d’</span> ID se compose du code JavaScript qui est placé sur chaque page à utiliser pour la collecte de données. Pour plus d’informations, consultez les guides <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html" format="https" scope="external"></a> de mise en oeuvre du service d’ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Lire le cookie du service <span class="keyword"> d’</span> ID</b> </p> </td> 
   <td colname="col2"> <p>Le service <span class="keyword"> d’</span> ID stocke l’ID utilisateur et l’ID de région dans le cookie AMCV. Le nom complet du cookie est <code>AMCV_<i>##</i>@AdobeOrg</code>. Les éléments <code><i>##</i></code> sont des espaces réservés pour l'ID d'organisation. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>Parcourez le cookie AMCV pour les paires clé-valeur suivantes : </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=ID<i></i></code>utilisateur : Cette paire clé-valeur contient l’ID utilisateur <span class="keyword"> Experience Cloud</span> . </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=ID<i>de</i></code>région : Cette paire clé-valeur contient l’identifiant de région (parfois appelé indicateur <span class="term"></span>d’emplacement) associé à un nom de serveur régional. </li> 
     </ul> </p> <p>Vous pouvez appeler le <span class="wintitle"> DCS</span> une fois que vous disposez des ID d’utilisateur et de région. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Récupérer l’ID <span class="keyword"> Experience Cloud</span> avec getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Facultatif)</i> Cette fonction renvoie l’ <span class="keyword"> identifiant visiteur Experience Cloud</span> . Il est conçu pour des solutions personnalisées et des cas d’utilisation spécifiques. Voir <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Utilisation de getMarketingCloudVisitorID</a> ci-dessous et la documentation <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-getmcvid.html" format="https" scope="external"> du service d’ID</a>associé. </p> <p>Vous n’avez pas besoin de l’utiliser si vous obtenez les ID d’utilisateur et d’emplacement à partir du cookie du service d’ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utilisation de `getMarketingCloudVisitorID`{#working-with-getmarketingcloudvisitorid}

La fonction permet également d’obtenir l’identifiant visiteur. `getMarketingCloudVisitorID` Lorsqu’elle est invoquée, cette fonction interroge le [!DNL ID service] serveur et renvoie un ID. `getMarketingCloudVisitorID` accepte l’ `callback` argument facultatif comme illustré ci-dessous :

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Utilisation et objectif du rappel {#callback-usage}

`callback` est facultatif. Cette fonction fonctionne sans elle, mais renvoie un identifiant uniquement lorsqu’un visiteur a un [!DNL Experience Cloud] cookie dans son navigateur. Si le cookie du visiteur est manquant ou qu’un visiteur n’a pas d’identifiant, la fonction renvoie un `()` objet vide. Cela peut se produire même après le chargement de la page et la réception d’un nouvel identifiant par le visiteur. Pour éviter cela, `callback` cette fonction vérifie l’identifiant d’un visiteur une fois la page chargée. Sans `callback`cela, la fonction Identifiant visiteur ne renvoie pas d’identifiant même s’il est écrit dans le navigateur du visiteur ultérieurement.

## Étapes suivantes {#next-steps}

Une fois que vous disposez de l’utilisateur et de l’ID de région, vous pouvez commencer à envoyer et à recevoir [!UICONTROL DCS] des données. Voir [Création d’appels](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)d’API DCS.