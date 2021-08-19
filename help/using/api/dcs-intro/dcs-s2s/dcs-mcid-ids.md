---
description: Les clients du service d’ID doivent se référer à cette section pour plus d’informations sur la lecture du cookie visiteur pour les ID requis pour effectuer des appels de l’API DCS.
seo-description: Les clients du service d’ID doivent se référer à cette section pour plus d’informations sur la lecture du cookie visiteur pour les ID requis pour effectuer des appels de l’API DCS.
seo-title: Obtention des identifiants et des régions via Adobe Experience Platform Identity Service
solution: Audience Manager
title: Obtention des identifiants et des régions via Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 7%

---

# Obtention des identifiants et des régions via Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Les clients du service d’ID doivent se référer à cette section pour plus d’informations sur la lecture du cookie visiteur pour les ID requis pour effectuer des appels d’API [!DNL DCS].

## Obtention de l’ID utilisateur à partir du cookie du service d’ID {#get-user-ids-from-service-cookie}

Le [service Adobe Experience Platform Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html) affecte les identifiants de visiteur et de région aux utilisateurs qui se rendent sur votre site web. Ces identifiants identifient les utilisateurs de toutes les solutions dans [!DNL Experience Cloud] et ils sont nécessaires si vous souhaitez effectuer des appels [!DNL DCS].

* [!UICONTROL user ID] est nécessaire pour identifier et associer des données à un visiteur particulier.
* [!UICONTROL region ID] est requis, car il est lié à un nom de serveur régional, que vous devez envoyer aux [!DNL DCS]. [!DNL DCS] stocke des informations dans les centres de données qui sont géographiquement les plus proches des visiteurs du site. Voir [ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md) (DCS Region IDs, Locations, and Host Names).

Les clients du service d’ID peuvent extraire ces informations du cookie du service d’ID ou en appelant une fonction. Le tableau ci-dessous décrit les tâches ou les étapes à réaliser pour commencer.

Le code de *italics* représente un espace réservé de variable.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tâche </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Vérifiez votre <span class="keyword"> Experience Cloud</span> statut</b> </p> </td> 
   <td colname="col2"> <p>Vous avez besoin d’un compte <span class="keyword"> Experience Cloud</span> pour utiliser le service d’ID. Si vous disposez d’un compte <span class="keyword"> Experience Cloud</span>, c’est super ! </p> <p> Si vous ne faites pas partie de l’Experience Cloud <span class="keyword"> </span>, inscrivez-vous. Nous aimerions vous avoir et il y a toujours de la place pour plus. Pour plus d’informations sur la configuration d’un compte, voir <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Activation de vos solutions pour les services principaux</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Configuration du <span class="keyword"> service d’ID</span></b> </p> </td> 
   <td colname="col2"> <p>Le <span class="keyword"> service d’ID</span> est constitué de code JavaScript qui est placé sur chaque page que vous souhaitez utiliser pour la collecte de données. Pour plus d’informations, consultez les <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> guides de mise en oeuvre du service d’ID</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Lisez le <span class="keyword"> cookie du service d’ID</span></b> </p> </td> 
   <td colname="col2"> <p>Le <span class="keyword"> service d’ID</span> stocke l’identifiant utilisateur et l’identifiant de région dans le cookie AMCV. Le nom complet du cookie est <code>AMCV_<i>###</i>@AdobeOrg</code>. Les éléments <code><i>###</i></code> sont des espaces réservés pour l’ID d’organisation. Voir <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies et ID Experience Cloud</a> pour plus d’informations. </p> <p>Analysez le cookie AMCV pour ces paires clé-valeur : </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Cette paire clé-valeur contient l’identifiant  <span class="keyword"> Experience </span> Cloud. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Cette paire clé-valeur contient l’identifiant de région (parfois appelé indicateur d’ <span class="term"> emplacement</span>) associé à un nom de serveur régional. </li> 
     </ul> </p> <p>Vous pouvez appeler le <span class="wintitle"> DCS</span> une fois que vous disposez des identifiants d’utilisateur et de région. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. Récupérez l’<span class="keyword"> ID Experience Cloud</span> avec getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Facultatif)</i> Cette fonction renvoie l’identifiant visiteur  <span class="keyword"> Experience </span> Cloud. Il est conçu pour des solutions personnalisées et des cas d’utilisation spécifiques. Voir <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Utilisation de getMarketingCloudVisitorID</a> ci-dessous et la <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> documentation du service d’ID associée</a>. </p> <p>Vous n’avez pas besoin de l’utiliser si vous obtenez les ID d’utilisateur et d’emplacement à partir du cookie du service d’ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utilisation De `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Une autre méthode pour obtenir l’identifiant visiteur consiste à utiliser la fonction `getMarketingCloudVisitorID`. Lorsqu’elle est appelée, cette fonction interroge la balise [!DNL ID service] et renvoie un ID. `getMarketingCloudVisitorID` accepte l’ `callback` argument facultatif comme illustré ci-dessous :

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Utilisation et objectif du rappel {#callback-usage}

`callback` est facultatif. Cette fonction fonctionne sans elle, mais renvoie un ID uniquement lorsqu’un visiteur a un cookie [!DNL Experience Cloud] dans son navigateur. Si le cookie du visiteur est manquant ou si un visiteur n’a pas d’identifiant, la fonction renvoie un objet `()` vide. Cela peut se produire même après le chargement de la page et la réception par le visiteur d’un nouvel identifiant. Pour éviter cela, `callback` force cette fonction à rechercher un identifiant visiteur une fois la page chargée. Sans `callback`, la fonction d’identification du visiteur ne renvoie pas d’identifiant même s’il est écrit ultérieurement dans le navigateur du visiteur.

## Étapes suivantes {#next-steps}

Une fois que vous disposez de l’identifiant de région et de l’utilisateur, vous pouvez commencer à envoyer et recevoir des données [!DNL DCS]. Voir [Lancement d’appels d’API DCS](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
