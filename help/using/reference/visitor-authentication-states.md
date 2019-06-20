---
description: L'état d'authentification des visiteurs dans Audience Manager détermine si les informations de nouvelle caractéristique sont écrites dans le profil authentifié du visiteur ou dans le profil de l'appareil, où les données ont été collectées. Audience Manager gère les états d'authentification des identifiants visiteur Inconnus et LOGGED_ OUT dans les appels d'événement de la même manière.
keywords: dpm.demdex.net
seo-description: L'état d'authentification des visiteurs dans Audience Manager détermine si les informations de nouvelle caractéristique sont écrites dans le profil authentifié du visiteur ou dans le profil de l'appareil, où les données ont été collectées. Audience Manager gère les états d'authentification des identifiants visiteur Inconnus et LOGGED_ OUT dans les appels d'événement de la même manière.
seo-title: États d'authentification des visiteurs dans Audience Manager
solution: Audience Manager
title: États d'authentification des visiteurs dans Audience Manager
uuid: d 748 c 0 c 3-5833-4 fb 9-ab 3 e -793 f 5 f 252 e 47
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Visitor Authentication States in Audience Manager{#visitor-authentication-states-in-audience-manager}

L&#39;état d&#39;authentification des visiteurs dans Audience Manager détermine si les informations de nouvelle caractéristique sont écrites dans le profil authentifié du visiteur ou dans le profil de l&#39;appareil, où les données ont été collectées. Audience Manager gère les états d&#39;authentification des identifiants visiteur Inconnus et LOGGED_ OUT dans les appels d&#39;événement de la même manière.

Beginning with [!DNL Experience Cloud] ID service v1.5+, the `setCustomerID` method includes the optional `AuthState` object. `AuthState` identifie les visiteurs en fonction de [leur état d&#39;authentification](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html). [!DNL Audience Manager] gère différemment les caractéristiques réalisées, selon l&#39;état d&#39;authentification transmis dans l&#39;appel et la règle de fusion [de profils que](../features/profile-merge-rules/merge-rules-dashboard.md) vous utilisez pour la segmentation.

## Authentication Status: UNKNOWN {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valeur de requête </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Lire</b> les informations du profil authentifié </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Ecriture</b> de nouvelles caractéristiques dans le profil authentifié </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Oui, si la règle de fusion d'option authentifiée = « Derniers profils authentifiés ». </p> </td> 
   <td colname="col3" morerows="1"> <p>Non, les données de caractéristique sont ajoutées au profil de périphérique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Non, si la règle de fusion d'option authentifiée = « Profils authentifiés actuels » ou « Profil authentifié ». </p> </td> 
  </tr> 
 </tbody> 
</table>

Exemple d&#39;appel (la valeur de requête correspondant à l&#39;état d&#39;authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Authentication Status: AUTHENTICATED {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valeur de requête </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Lire</b> les informations du profil authentifié </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Ecriture</b> de nouvelles caractéristiques dans le profil authentifié </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code>1</code> </p> </td> 
   <td colname="col2"> <p>Oui, si la règle de fusion d'option authentifiée = « Profils authentifiés actuels » ou « Profils authentifiés derniers ». </p> </td> 
   <td colname="col3" morerows="1"> <p>Oui, les données de caractéristique sont ajoutées au profil authentifié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Non, si la règle de fusion d'option authentifiée = « Aucun profil authentifié ». </p> </td> 
  </tr> 
 </tbody> 
</table>

Exemple d&#39;appel (la valeur de requête correspondant à l&#39;état d&#39;authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Authentication Status: LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valeur de requête </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Lire</b> les informations du profil authentifié </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Ecriture</b> de nouvelles caractéristiques dans le profil authentifié </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code>2</code> </p> </td> 
   <td colname="col2"> Oui, si la règle de fusion d'option authentifiée = « Derniers profils authentifiés » </td> 
   <td colname="col3" morerows="1"> <p>Non, les données de caractéristique sont écrites dans le profil du périphérique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Non, si la règle de fusion d'option authentifiée = « Profils authentifiés actuels » ou « Profil authentifié » ou « Profil authentifié » </td> 
  </tr> 
 </tbody> 
</table>

Exemple d&#39;appel (la valeur de requête correspondant à l&#39;état d&#39;authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] effectue une synchronisation des identifiants entre [CID et UUID](../reference/ids-in-aam.md) dans les trois cas.

>[!MORE_ LIKE_ THIS]
>
>* [ID de client et états d’authentification](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)

