---
description: Les clients du service d'ID doivent se référer à cette section pour savoir comment lire le cookie visiteur pour les ID requis pour effectuer des appels d'API DCS.
seo-description: Les clients du service d'ID doivent se référer à cette section pour savoir comment lire le cookie visiteur pour les ID requis pour effectuer des appels d'API DCS.
seo-title: Obtention de l'utilisateur - Identifiants et régions via le service Experience Cloud ID
solution: Audience Manager
title: Obtention de l'utilisateur - Identifiants et régions via le service Experience Cloud ID
uuid: 80 de 6 cf 2-5 d 9 e -4 ef 8-a 0 f 2-d 53 b 5 d 574 c 89
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Get User IDs and Regions Through the Experience Cloud ID Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make [!UICONTROL DCS] API calls.

## Get the User ID from the ID Service Cookie {#get-user-ids-from-service-cookie}

The [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/) assigns visitor and region IDs to users who come to your website. These IDs identify users across all the solutions in the [!DNL Experience Cloud] and they are required if you want to make [!UICONTROL DCS] calls.

* The [!UICONTROL user ID] is required to identify and associate data with a particular visitor.
* The [!UICONTROL region ID] is required because it is tied to a regional server name, which you need to send data to the [!UICONTROL DCS]. The [!UICONTROL DCS] stores information in data centers that are geographically closest to site visitors. Voir [ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (DCS Region IDs, Locations, and Host Names).

Les clients du service d&#39;ID peuvent extraire ces informations du cookie du service d&#39;ID ou en appelant une fonction. Le tableau ci-dessous décrit les tâches ou les étapes que vous devez effectuer pour commencer.

Code in *italics* represents a variable placeholder.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tâche </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Check your <span class="keyword"> Experience Cloud</span> status</b> </p> </td> 
   <td colname="col2"> <p>You need a <span class="keyword"> Experience Cloud</span> account to use the ID service. If you have a <span class="keyword"> Experience Cloud</span> account, great! </p> <p> If you're not part of the <span class="keyword"> Experience Cloud</span>, then sign up. Nous aimerions que vous disposiez d'une place pour plus d'espace. For instructions on how to set up an account, see <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=core_services.html" format="https" scope="external"> Core Services - Enabling Your Solutions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> ID service</span> consists of JavaScript code that gets put on each page you want to use for data collection. See the ID service <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html" format="https" scope="external"> implementation guides</a> for more information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Read the <span class="keyword"> ID service</span> cookie</b> </p> </td> 
   <td colname="col2"> <p>The <span class="keyword"> ID service</span> stores the user and region ID in the AMCV cookie. The full cookie name is <code>AMCV_<i>###</i>@AdobeOrg</code>. <code><i>Les # # #</i></code> elements sont des espaces réservés pour votre ID d'organisation. See <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>Parse le cookie AMCV pour ces paires clé-valeur : </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid =<i>user - id</i></code>: Cette paire clé-valeur contient l'utilisateur <span class="keyword"> Experience Cloud</span> - id. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh =<i>ID de région</i></code>: Cette paire clé-valeur contient l'identifiant de région (parfois appelé indicateur <span class="term"> d'emplacement</span>) associé à un nom de serveur régional. </li> 
     </ul> </p> <p>You can make calls to the <span class="wintitle"> DCS</span> once you have the user and region IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Retrieve the <span class="keyword"> Experience Cloud ID</span> with getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Facultatif)</i> Cette fonction renvoie l'identifiant visiteur <span class="keyword"> Experience Cloud</span> . Il est conçu pour des solutions personnalisées et des cas d'utilisation spécifiques. See <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Working With getMarketingCloudVisitorID</a> below and the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-getmcvid.html" format="https" scope="external"> related ID service documentation</a>. </p> <p>Vous n'avez pas besoin de l'utiliser si vous obtenez les ID d'utilisateur et d'emplacement à partir du cookie du service d'ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Working With `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Another way to get the visitor ID is with the `getMarketingCloudVisitorID` function. When invoked, this function queries the [!DNL ID service] and returns an ID. `getMarketingCloudVisitorID` accepte l&#39;argument facultatif `callback` comme indiqué :

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Callback Usage and Purpose {#callback-usage}

`callback` est facultative. This function works without it, but returns an ID only when a visitor has a [!DNL Experience Cloud] cookie in their browser. If the visitor cookie is missing, or a visitor doesn&#39;t have an ID, the function returns an empty `()` object. Cela peut se produire même après le chargement de la page et un nouvel identifiant. To avoid this, `callback` forces this function to check for a visitor ID after the page loads. Without `callback`, the visitor ID function won&#39;t return an ID even if it&#39;s written to the visitor&#39;s browser later.

## Étapes suivantes {#next-steps}

Once you have the user and region ID, you can start sending and receiving [!UICONTROL DCS] data. See [Making DCS API Calls](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).