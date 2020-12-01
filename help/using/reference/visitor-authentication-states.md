---
description: L’état d’authentification du visiteur dans l’Audience Manager détermine si les informations de nouvelle caractéristique sont écrites au profil authentifié du visiteur ou au profil du périphérique, à partir duquel les données ont été collectées. L’Audience Manager gère de la même manière les états d’authentification de l’ID de visiteur INCONNU et LOGGED_OUT dans les appels de événement.
keywords: dpm.demdex.net
seo-description: L’état d’authentification du visiteur dans l’Audience Manager détermine si les informations de nouvelle caractéristique sont écrites au profil authentifié du visiteur ou au profil du périphérique, à partir duquel les données ont été collectées. L’Audience Manager gère de la même manière les états d’authentification de l’ID de visiteur INCONNU et LOGGED_OUT dans les appels de événement.
seo-title: États d’authentification du visiteur dans Audience Manager
solution: Audience Manager
title: États d’authentification du visiteur dans Audience Manager
uuid: d748c0c3-5833-4fb9-ab3e-793f5f252e47
feature: reference
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---


# États d’authentification du visiteur dans Audience Manager{#visitor-authentication-states-in-audience-manager}

L’état d’authentification du visiteur dans l’Audience Manager détermine si les informations de nouvelle caractéristique sont écrites au profil authentifié du visiteur ou au profil du périphérique, à partir duquel les données ont été collectées. L’Audience Manager gère de la même manière les états d’authentification de l’ID de visiteur INCONNU et LOGGED_OUT dans les appels de événement.

À partir de [!DNL Experience Cloud] service d’ID v1.5+, la méthode `setCustomerID` comprend l’objet facultatif `AuthState`. `AuthState` identifie les visiteurs en fonction de leur état [ d’](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)authentification. [!DNL Audience Manager] gère différemment les caractéristiques réalisées, en fonction de l’état d’authentification transmis dans l’appel et de la  [règle de fusion du ](../features/profile-merge-rules/merge-rules-dashboard.md) Profil que vous utilisez pour la segmentation.

## État de l&#39;authentification : INCONNU {#auth-status-unknown}

<table id="table_E1EA51533FAE4BBFB338D6F6116BC1F9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valeur de requête </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Lecture des informations du profil authentifié </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Nouvelles caractéristiques </b> écrites au profil authentifié </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 0 </code> </p> </td> 
   <td colname="col2"> <p>Oui, si la règle de fusion des options authentifiées = "Derniers Profils authentifiés". </p> </td> 
   <td colname="col3" morerows="1"> <p>Non, les données de caractéristiques sont ajoutées au profil du périphérique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Non, si la règle de fusion des options authentifiées = "Profils authentifiés actuels" ou "Aucun Profil authentifié". </p> </td> 
  </tr> 
 </tbody> 
</table>

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%010&d_sid=123456`

## État de l&#39;authentification : AUTHENTIFIÉ {#auth-status-authenticated}

<table id="table_956ABF96024744308F7773E1F96482B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valeur de requête </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Lecture des informations du profil authentifié </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Nouvelles caractéristiques </b> écrites au profil authentifié </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 1 </code> </p> </td> 
   <td colname="col2"> <p>Oui, si la règle de fusion des options authentifiées = "Profils authentifiés actuels" ou "Derniers Profils authentifiés". </p> </td> 
   <td colname="col3" morerows="1"> <p>Oui, les données de caractéristiques sont ajoutées au profil authentifié. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Non, si la règle de fusion des options authentifiées = "Aucun Profil authentifié". </p> </td> 
  </tr> 
 </tbody> 
</table>

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%011&d_sid=123456`

## État de l&#39;authentification : LOGGED_OUT {#auth-status-logged-out}

<table id="table_783F0CBB0431482AA49F41468FA65B19"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Valeur de requête </p> </th> 
   <th colname="col2" class="entry"> <p> <b></b> Lecture des informations du profil authentifié </p> </th> 
   <th colname="col3" class="entry"> <p> <b>Nouvelles caractéristiques </b> écrites au profil authentifié </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <p> <code> 2 </code> </p> </td> 
   <td colname="col2"> Oui, si la règle de fusion des options authentifiées = "Derniers Profils authentifiés" </td> 
   <td colname="col3" morerows="1"> <p>Non, les données de caractéristiques sont écrites sur le profil du périphérique. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> Non, si la règle de fusion des options authentifiées = "Profils authentifiés actuels" ou "Aucun Profil authentifié" </td> 
  </tr> 
 </tbody> 
</table>

Exemple d’appel (la valeur de requête correspondant à l’état d’authentification est mise en surbrillance) :

`https://sample_customer.demdex.net/event?d_cid=123%01sample_id%012&d_sid=123456`

>[!NOTE]
>
>[!DNL Audience Manager] effectue une synchronisation des identifiants entre  [CID et ](../reference/ids-in-aam.md) UUID dans les trois cas.

>[!MORELIKETHIS]
>
>* [ID de client et états d’authentification](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html)

