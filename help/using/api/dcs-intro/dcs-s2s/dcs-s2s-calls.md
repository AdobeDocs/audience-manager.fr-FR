---
seo-title: Création d'appels d'API serveur à serveur
solution: Audience Manager
title: Création d'appels d'API serveur à serveur
uuid: bdfe 3430-e 27 f -4 a 5 c -88 d 9-ae 164 d 28 f 601
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Making Server-to-Server DCS API Calls {#making-server-to-server-dcs-api-calls}

Les appels nécessitent le nom d&#39;hôte du serveur DCS régional et de l&#39;utilisateur - id. If you do not have the required user and region IDs, see [Get User IDs and Regions From a DCS Response](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) and/or [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Une fois que vous avez des ID d&#39;utilisateur et de région, vous pouvez effectuer des appels serveur à serveur au serveur de collecte de données. Reportez-vous à cette section pour obtenir une syntaxe et des exemples.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Substitute a real value for the placeholder when you server-to-server calls to the [!UICONTROL DCS].

## Call Syntax and Example {#call-syntax-example}

A basic server-to-server request that sends data to the [!UICONTROL DCS] uses the syntax shown below.

<pre><code>« Host :<i>domain alias</i>. demdex. net » https://DCS<i>host name.demdex.net/event?d_rtbd=json&amp;d_jsonv=1&amp;d_uuid=user</i><i>ID</i>.</code>
</pre>

Un exemple d&#39;appel ressemble à l&#39;exemple suivant.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Call Parameters {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code><i>alias de domaine</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l'appel contient : </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Your domain alias assigned by <span class="keyword"> Audience Manager</span> (e.g., <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">The destination domain, which is always <i><code> demdex.net</code></i>. Voir <a href="../../../reference/demdex-calls.md">Signification des appels vers le domaine Demdex</a> (Understanding Calls to the Demdex Domain). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>Nom d'hôte DCS</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>The http header host parameter which shows the name of the regional <span class="wintitle"> DCS</span> server. Le nom d'hôte est lié à un identifiant de région. C'est pourquoi vous devez le faire avant d'effectuer ces types d'appel. Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données</a> (DCS Region IDs, Locations, and Host Names). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l'appel : </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifie l'appel comme appel d'événement. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Définit le début de la chaîne URL qui contient les données que vous souhaitez envoyer au serveur de collecte de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ uuid = <i>Utilisateur Audience Manager - id</i></code> </p> </td> 
   <td colname="col2"> <p>This is the unique user ID key that holds the <span class="keyword"> Audience Manager</span> user ID value in a key-value pair. </p> <p>Use <code><i>d_uuid</i></code> if you're passing in the <span class="keyword"> Audience Manager</span> user ID. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ mid =<i>User Cloud user - id</i></code> </p> </td> 
   <td colname="col2"> <p>This is the unique user ID key that holds the <span class="keyword"> Experience Cloud</span> user ID value in a key-value pair. See also <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Get the User ID from the ID Service Cookie</a>. </p> <p>Use <i><code> d_mid</code></i> if you're passing in a <span class="keyword"> Experience Cloud</span> ID captured from the <span class="keyword"> Experience Cloud</span> ID service. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_ cb =<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Paramètres de réponse facultatifs. </p> <p> None of these are required to send data to the <span class="wintitle"> DCS</span>. However, if you want the <span class="wintitle"> DCS</span> to return a response, you must include <i><code> d_rtbd=json</code></i> in your request. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemple de réponse {#sample-response}

See [Receive Data From the DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
