---
description: Les clients du service d’ID doivent consulter cette section pour savoir comment lire le cookie visiteur pour les ID requis pour effectuer des appels à l’API DCS.
seo-description: Les clients du service d’ID doivent consulter cette section pour savoir comment lire le cookie visiteur pour les ID requis pour effectuer des appels à l’API DCS.
seo-title: Obtention des identifiants utilisateur et des régions via le service d'identité des Adobes Experience Platform
solution: Audience Manager
title: Obtention des identifiants utilisateur et des régions via le service d'identité des Adobes Experience Platform
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 2%

---


# Obtention des identifiants utilisateur et des régions via le service d&#39;identité des Adobes Experience Platform {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Les clients du service d’ID doivent consulter cette section pour savoir comment lire le cookie visiteur pour les ID requis pour effectuer des appels [!DNL DCS] d’API.

## Récupérer l’ID utilisateur à partir du cookie du service d’ID {#get-user-ids-from-service-cookie}

Le service [d’identité des](https://docs.adobe.com/content/help/en/id-service/using/home.html) Adobes Experience Platform attribue des ID de visiteur et de région aux utilisateurs qui se rendent sur votre site Web. Ces identifiants identifient les utilisateurs dans toutes les solutions du [!DNL Experience Cloud] site et ils sont nécessaires si vous souhaitez effectuer des [!DNL DCS] appels.

* Le [!UICONTROL user ID] paramètre est nécessaire pour identifier et associer des données à un visiteur particulier.
* Le [!UICONTROL region ID] est requis car il est lié à un nom de serveur régional, que vous devez envoyer des données au [!DNL DCS]serveur. Il [!DNL DCS] stocke les informations dans les centres de données qui sont géographiquement les plus proches des visiteurs du site. Voir [ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (DCS Region IDs, Locations, and Host Names).

Les clients du service d’ID peuvent extraire ces informations du cookie du service d’ID ou en appelant une fonction. Le tableau ci-dessous décrit les tâches ou les étapes à suivre pour commencer.

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
   <td colname="col1"> <p> <b>1. Vérifier le statut de votre <span class="keyword"> Experience Cloud</span></b> </p> </td> 
   <td colname="col2"> <p>Vous avez besoin d’un compte <span class="keyword"> Experience Cloud</span> pour utiliser le service d’ID. Si vous avez un compte <span class="keyword"> Experience Cloud</span> , c'est super ! </p> <p> Si vous ne faites pas partie de l' <span class="keyword"> Experience Cloud</span>, inscrivez-vous. Nous aimerions vous avoir et il y a toujours de la place pour plus. Pour obtenir des instructions sur la configuration d’un compte, voir <a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Activation de vos solutions pour les services</a>principaux. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Set up the <span class="keyword"> ID service</span></b> </p> </td> 
   <td colname="col2"> <p>Le service <span class="keyword"> d’</span> ID se compose d’un code JavaScript placé sur chaque page à utiliser pour la collecte de données. Pour plus d’informations, consultez les guides <a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external"></a> de mise en oeuvre du service d’ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Lisez le cookie du service <span class="keyword"> d’</span> ID</b> </p> </td> 
   <td colname="col2"> <p>Le service <span class="keyword"> d’</span> ID stocke l’ID d’utilisateur et de région dans le cookie AMCV. Le nom complet du cookie est <code>AMCV_<i>###</i>@AdobeOrg</code>. Les <code><i>###</i></code> éléments sont des espaces réservés pour l’ID d’organisation. See <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies and the Experience Cloud ID</a> for details. </p> <p>Analysez le cookie AMCV pour ces paires clé-valeur : </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Cette paire clé-valeur contient l’ID utilisateur <span class="keyword"> Experience Cloud</span> . </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Cette paire clé-valeur contient l’identifiant de région (parfois appelé indicateur <span class="term"> d’</span>emplacement) associé à un nom de serveur régional. </li> 
     </ul> </p> <p>Vous pouvez appeler le serveur de collecte de données <span class="wintitle"></span> une fois que vous disposez des identifiants d’utilisateur et de région. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Récupérez l’identifiant <span class="keyword"></span> Experience Cloud avec getMarketingCloudVisitorID.</b> </p> </td> 
   <td colname="col2"> <p><i>(Facultatif)</i> Cette fonction renvoie l’ID de visiteur <span class="keyword"> Experience Cloud</span> . Il est conçu pour des solutions personnalisées et des cas d'utilisation spécifiques. Voir <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Utilisation de getMarketingCloudVisitorID</a> ci-dessous et la documentation <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> du service d’ID</a>associé. </p> <p>Vous n’avez pas besoin de l’utiliser si vous obtenez les ID d’utilisateur et d’emplacement à partir du cookie du service d’ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utilisation `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Une autre façon d’obtenir l’ID de visiteur est d’utiliser la `getMarketingCloudVisitorID` fonction. Lorsqu’elle est appelée, cette fonction requête la [!DNL ID service] et renvoie un identifiant. `getMarketingCloudVisitorID` accepte l&#39;argument facultatif `callback` comme illustré ci-dessous :

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Utilisation et objectif du rappel {#callback-usage}

`callback` est facultatif. Cette fonction fonctionne sans elle, mais renvoie un identifiant uniquement lorsqu’un visiteur a un [!DNL Experience Cloud] cookie dans son navigateur. Si le cookie de visiteur est manquant ou si un visiteur ne possède pas d’ID, la fonction renvoie un `()` objet vide. Cela peut se produire même après le chargement de la page et la réception par le visiteur d’un nouvel identifiant. Pour éviter cela, `callback` cette fonction doit rechercher un ID de visiteur après le chargement de la page. Sans `callback`cela, la fonction d’identification du visiteur ne renvoie pas d’identifiant même s’il est écrit ultérieurement au navigateur du visiteur.

## Étapes suivantes {#next-steps}

Une fois que vous disposez de l’utilisateur et de l’ID de région, vous pouvez début l’envoi et la réception de [!DNL DCS] données. Voir [Exécution d’appels](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)d’API DCS.