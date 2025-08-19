---
description: Les clients du service d’ID doivent se référer à cette section pour plus d’informations sur la lecture du cookie du visiteur pour les identifiants requis pour effectuer des appels API DCS.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: Obtention des identifiants de région et d’utilisateur via Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 2%

---

# Obtention des identifiants de région et d’utilisateur via Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Les clients du service d’ID doivent se référer à cette section pour plus d’informations sur la lecture du cookie du visiteur pour les identifiants requis pour effectuer des appels API [!DNL DCS].

## Obtention de l’ID utilisateur à partir du cookie du service d’ID {#get-user-ids-from-service-cookie}

Le [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=fr) attribue des ID de visiteur et de région aux utilisateurs qui visitent votre site web. Ces identifiants identifient les utilisateurs et utilisatrices de toutes les solutions du [!DNL Experience Cloud]. Ils sont nécessaires si vous souhaitez effectuer des appels [!DNL DCS].

* L’[!UICONTROL user ID] est nécessaire pour identifier et associer des données à un visiteur particulier.
* Le [!UICONTROL region ID] est obligatoire, car il est lié à un nom de serveur régional, auquel vous devez envoyer des données au [!DNL DCS]. Le [!DNL DCS] stocke les informations dans les centres de données géographiquement les plus proches des visiteurs du site. Voir [ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (DCS Region IDs, Locations, and Host Names).

Les clients du service d’ID peuvent extraire ces informations à partir du cookie du service d’ID ou en appelant une fonction . Le tableau ci-dessous décrit les tâches ou étapes à suivre pour commencer.

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
   <td colname="col1"> <p> <b>1. Vérifiez le statut de votre <span class="keyword"> Experience Cloud</span> </b> </p> </td> 
   <td colname="col2"> <p>Vous avez besoin d’un compte <span class="keyword"> Experience Cloud</span> pour utiliser le service d’ID. Si vous disposez d’un compte <span class="keyword"> Experience Cloud</span>, tant mieux ! </p> <p> Si vous ne faites pas partie de l’<span class="keyword"> Experience Cloud</span> inscrivez-vous. Nous serions ravis de vous accueillir et il y a toujours de la place pour plus. Pour obtenir des instructions sur la configuration d’un compte, voir <a href="https://experienceleague.adobe.com/fr/docs/core-services/interface/services/getting-started" format="https" scope="external"> Activation de vos solutions pour les services principaux</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Configurez le service <span class="keyword"> ID </span></b> </p> </td> 
   <td colname="col2"> <p>Le service d’ID de <span class="keyword"></span> se compose d’un code JavaScript qui est placé sur chaque page que vous souhaitez utiliser pour la collecte de données. Pour plus d’informations<a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=fr" format="https" scope="external"> consultez les guides de mise en œuvre du </a> du service d’ID . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Lisez le cookie <span class="keyword"> service d’ID </span> </b> </p> </td> 
   <td colname="col2"> <p>Le service <span class="keyword"> ID stocke </span>’identifiant de l’utilisateur et de la région dans le cookie AMCV. Le nom complet du cookie est <code>AMCV_<i>###</i>@AdobeOrg</code>. Les éléments <code><i>###</i></code> sont des espaces réservés pour votre ID d’organisation. Voir Cookies <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=fr" format="https" scope="external"> et Experience Cloud ID</a> pour plus d’informations. </p> <p>Analysez le cookie AMCV pour ces paires clé-valeur : </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code> : cette paire clé-valeur contient l’identifiant utilisateur Experience Cloud<span class="keyword"> </span>. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code> : cette paire clé-valeur contient l’identifiant de région (parfois appelé conseil d’emplacement <span class="term"></span>) associé à un nom de serveur régional. </li> 
     </ul> </p> <p>Vous pouvez effectuer des appels vers le <span class="wintitle"> DCS</span> une fois que vous disposez des identifiants d’utilisateur et de région. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Récupérez le <span class="keyword"> Experience Cloud ID</span> avec getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Facultatif)</i> Cette fonction renvoie l’identifiant visiteur <span class="keyword"> Experience Cloud</span>. Il est conçu pour des solutions personnalisées et des cas d’utilisation spécifiques. Voir <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Utilisation de getMarketingCloudVisitorID</a> ci-dessous et la <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html?lang=fr" format="https" scope="external"> documentation du service d’ID associé</a>. </p> <p>Vous n’avez pas besoin de l’utiliser si vous obtenez les identifiants d’utilisateur et d’emplacement à partir du cookie du service d’ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utilisation De `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

La fonction `getMarketingCloudVisitorID` permet également d’obtenir l’identifiant visiteur. Lorsqu’elle est appelée, cette fonction interroge la [!DNL ID service] et renvoie un identifiant. `getMarketingCloudVisitorID` accepte l’argument de `callback` facultatif comme illustré ci-dessous :

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Utilisation et objectif du rappel {#callback-usage}

`callback` est facultatif. Cette fonction fonctionne sans elle, mais renvoie un identifiant uniquement lorsqu’un visiteur dispose d’un cookie [!DNL Experience Cloud] dans son navigateur. Si le cookie du visiteur est manquant ou si un visiteur ne dispose pas d’un identifiant, la fonction renvoie un objet `()` vide. Cela peut se produire même après le chargement de la page et la réception d’un nouvel identifiant par le visiteur. Pour éviter cela, `callback` force cette fonction à rechercher un identifiant visiteur après le chargement de la page. Sans `callback`, la fonction d’identifiant visiteur ne renvoie pas d’identifiant, même s’il est écrit dans le navigateur du visiteur ultérieurement.

## Étapes suivantes {#next-steps}

Une fois que vous disposez de l’identifiant d’utilisateur et de région, vous pouvez commencer à envoyer et à recevoir des données [!DNL DCS]. Voir [Effectuer des appels API DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
