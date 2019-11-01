---
description: L’état d’authentification du visiteur dans Audience Manager détermine si les informations de nouvelle caractéristique sont écrites dans le profil authentifié du visiteur ou dans le profil du périphérique à partir duquel les données ont été collectées. Audience Manager gère de la même manière les états d’authentification de l’identifiant visiteur UNKNOWN et LOGGED_OUT dans les appels d’événement.
keywords: dpm.demdex.net
seo-description: L’état d’authentification du visiteur dans Audience Manager détermine si les informations de nouvelle caractéristique sont écrites dans le profil authentifié du visiteur ou dans le profil du périphérique à partir duquel les données ont été collectées. Audience Manager gère de la même manière les états d’authentification de l’identifiant visiteur UNKNOWN et LOGGED_OUT dans les appels d’événement.
seo-title: Etats d’authentification des visiteurs dans Audience Manager
solution: Audience Manager
title: Etats d’authentification des visiteurs dans Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Etats d’authentification des visiteurs dans Audience Manager{#visitor-authentication-states-in-audience-manager}

L’état d’authentification du visiteur dans Audience Manager détermine si les informations de nouvelle caractéristique sont écrites dans le profil authentifié du visiteur ou dans le profil du périphérique à partir duquel les données ont été collectées. Audience Manager gère de la même manière les états d’authentification de l’identifiant visiteur UNKNOWN et LOGGED_OUT dans les appels d’événement.

À partir de la version 1.5 du service [!DNL Experience Cloud] d’ID, la `setCustomerID` méthode inclut l’ `AuthState` objet facultatif. `AuthState` identifie les visiteurs en fonction de leur état [d’](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)authentification. [!DNL Audience Manager] gère différemment les caractéristiques réalisées, selon l’état d’authentification transmis dans l’appel et la règle [de fusion de](../features/profile-merge-rules/merge-rules-dashboard.md) profil utilisée pour la segmentation.

## Statut d’authentification : INCONNU {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valeur de requête </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Lire</b> les informations du profil authentifié </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Ecrire</b> de nouvelles caractéristiques dans le profil authentifié </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Oui, si la règle de fusion des options authentifiées = "Derniers profils authentifiés". </p> </td> 
   <td colname="col3" morerows="1"> <p>Non, les données de caractéristiques sont ajoutées au profil du périphérique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Non, si la règle de fusion des options authentifiées = "Profils authentifiés actuels" ou "Aucun profil authentifié". </p> </td> 
  </tr> 
 </tbody> 
</table>

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## Statut d’authentification : AUTHENTIFIÉ {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valeur de requête </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Lire</b> les informations du profil authentifié </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Ecrire</b> de nouvelles caractéristiques dans le profil authentifié </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Oui, si l’option Authentifiée Règle de fusion = "Profils authentifiés actuels" ou "Derniers profils authentifiés". </p> </td> 
   <td colname="col3" morerows="1"> <p>Oui, les données de caractéristique sont ajoutées au profil authentifié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Non, si la règle de fusion des options authentifiées = "Aucun profil authentifié". </p> </td> 
  </tr> 
 </tbody> 
</table>

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## Statut d’authentification : LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valeur de requête </p> </th> 
   <th colname="col2" class="entry"> <p> <b>Lire</b> les informations du profil authentifié </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Ecrire</b> de nouvelles caractéristiques dans le profil authentifié </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Oui, si la règle de fusion des options authentifiées = "Derniers profils authentifiés" </td> 
   <td colname="col3" morerows="1"> <p>Non, les données de caractéristiques sont écrites dans le profil du périphérique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Non, si la règle de fusion des options authentifiées = "Profils authentifiés actuels" ou "Aucun profil authentifié" </td> 
  </tr> 
 </tbody> 
</table>

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] effectue une synchronisation des identifiants entre [CID et UUID](../reference/ids-in-aam.md) dans les trois cas.

>[!MORELIKETHIS]
>
>* [ID de client et états d’authentification](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-authenticated-state.html)

