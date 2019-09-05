---
seo-title: Création d'appels d'API serveur à serveur
solution: Audience Manager
title: Création d'appels d'API serveur à serveur
uuid: bdfe 3430-e 27 f -4 a 5 c -88 d 9-ae 164 d 28 f 601
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# Création d'appels d'API serveur à serveur {#making-server-to-server-dcs-api-calls}

Les appels nécessitent le nom d'hôte du serveur DCS régional et de l'utilisateur - id. Si vous ne possédez pas les ID d'utilisateur et de région requis, voir [Obtention d'un utilisateur - Identifiants et régions à partir d'une réponse](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) DCS et/ou [d'Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Une fois que vous avez des ID d'utilisateur et de région, vous pouvez effectuer des appels serveur à serveur au serveur de collecte de données. Reportez-vous à cette section pour obtenir une syntaxe et des exemples.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Remplacez la valeur réelle de l'espace réservé lorsque vous appelez [!UICONTROL DCS]le serveur à serveur.

## Appel de la syntaxe et exemple {#call-syntax-example}

Une requête de base serveur à serveur qui envoie des données aux [!UICONTROL DCS] utilisations de la syntaxe illustrée ci-dessous.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

Un exemple d'appel ressemble à l'exemple suivant.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Paramètres d'appel {#call-parameters}

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Alias de domaine attribué par <span class="keyword"> Audience Manager</span> (par ex. <i><code> mon_ domaine. demdex. net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Domaine de destination, toujours <i><code> demdex. net</code></i>. Voir <a href="../../../reference/demdex-calls.md">Signification des appels vers le domaine Demdex</a> (Understanding Calls to the Demdex Domain). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>Nom d'hôte DCS</i>. demdex. net</code> </p> </td> 
   <td colname="col2"> <p>Paramètre d'hôte HTTP d'en-tête qui indique le nom du serveur <span class="wintitle"> DCS</span> régional. Le nom d'hôte est lié à un identifiant de région. C'est pourquoi vous devez le faire avant d'effectuer ces types d'appel. Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données</a> (DCS Region IDs, Locations, and Host Names). </p> </td> 
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
   <td colname="col2"> <p>Il s'agit de la clé user - id qui contient la <span class="keyword"> valeur User Manager</span> user - id dans une paire clé-valeur. </p> <p>Utilisez <code><i>d_ uuid</i></code> si vous transmettez l'utilisateur <span class="keyword"> Audience Manager</span> - id. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_ mid =<i>User Cloud user - id</i></code> </p> </td> 
   <td colname="col2"> <p>Il s'agit de la clé user-id unique qui contient la <span class="keyword"> valeur User Cloud</span> User - id dans une paire clé-valeur. Voir aussi <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Obtention de l'utilisateur - id depuis le cookie du service d'ID</a>. </p> <p>Utilisez <i><code> d_ mid</code></i> si vous transmettez un <span class="keyword"> ID</span> d'expérience capturé à partir du service <span class="keyword"> Experience Cloud</span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_ dst = 1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_ rtbd = json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_ cb =<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Paramètres de réponse facultatifs. </p> <p> Aucun d'eux n'est nécessaire pour envoyer des données au <span class="wintitle"> serveur de collecte de données</span>. Toutefois, si vous souhaitez que <span class="wintitle"> le serveur de collecte de données</span> renvoie une réponse, vous devez inclure <i><code> d_ rtbd = json</code></i> dans votre requête. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemple de réponse {#sample-response}

Voir [Réception des données du serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
