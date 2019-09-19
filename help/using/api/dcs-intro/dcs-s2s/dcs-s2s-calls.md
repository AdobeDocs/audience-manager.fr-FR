---
seo-title: Réalisation d’appels d’API DCS de serveur à serveur
solution: Audience Manager
title: Réalisation d’appels d’API DCS de serveur à serveur
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
translation-type: tm+mt
source-git-commit: bc2a9364b771436fe0191f9d69a8c291563f9229

---


# Réalisation d’appels d’API DCS de serveur à serveur {#making-server-to-server-dcs-api-calls}

Les appels nécessitent le nom d’hôte du serveur DCS régional et l’ID utilisateur. Si vous ne disposez pas des ID utilisateur et de région requis, reportez-vous à la section [Obtention des ID utilisateur et des régions à partir d’une réponse](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) DCS et/ou d’ [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Une fois que vous disposez d’ID d’utilisateur et de région, vous pouvez lancer des appels serveur à serveur au serveur de collecte de données. Reportez-vous à cette section pour obtenir des exemples de syntaxe.

>[!NOTE]
>
>In the code and examples, *italics* represents a variable placeholder. Remplacez une valeur réelle pour l’espace réservé lorsque vous appelez le serveur à serveur vers le [!UICONTROL DCS].

## Syntaxe des appels et exemple {#call-syntax-example}

Une requête de base de serveur à serveur qui envoie des données au serveur [!UICONTROL DCS] utilise la syntaxe ci-dessous.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

Un exemple d’appel ressemble à l’exemple suivant.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Paramètres d’appel {#call-parameters}

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> alias <i>de</i>domaine.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l’appel contient : </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Votre alias de domaine est attribué par <span class="keyword"> Audience Manager</span> (par exemple, <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Domaine de destination, qui est toujours <i><code> demdex.net</code></i>. Voir <a href="../../../reference/demdex-calls.md">Signification des appels vers le domaine Demdex</a> (Understanding Calls to the Demdex Domain). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Nom d’hôte <i>DCS</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Paramètre hôte d’en-tête http qui indique le nom du serveur <span class="wintitle"> DCS</span> régional. Le nom d’hôte est lié à un identifiant de région. C’est pourquoi vous en avez besoin avant d’effectuer ce type d’appels. Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données</a> (DCS Region IDs, Locations, and Host Names). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l’appel : </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifie l’appel comme un appel d’événement. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Définit le début de la chaîne URL contenant les données à envoyer au serveur de collecte de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= ID utilisateur <i>Audience Manager</i></code> </p> </td> 
   <td colname="col2"> <p>Il s’agit de la clé d’ID utilisateur unique qui contient la valeur d’ID utilisateur d’Audience Manager <span class="keyword"></span> dans une paire clé-valeur. </p> <p>Utilisez <code><i>d_uuid</i></code> si vous transmettez l’ <span class="keyword"> ID utilisateur d’Audience Manager</span> . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=ID utilisateur<i>Experience Cloud</i></code> </p> </td> 
   <td colname="col2"> <p>Il s’agit de la clé d’ID utilisateur unique qui contient la valeur de l’ID utilisateur <span class="keyword"> Experience Cloud</span> dans une paire clé-valeur. Voir aussi <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Obtention de l’ID utilisateur à partir du cookie</a>du service d’ID. </p> <p>Utilisez <i><code> _id</code></i> si vous transmettez un <span class="keyword"> ID Experience Cloud</span> capturé à partir du service <span class="keyword"> Experience Cloud</span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Paramètres de réponse facultatifs. </p> <p> Aucune de ces options n’est requise pour envoyer des données au <span class="wintitle"> serveur de collecte de données</span>. Toutefois, si vous souhaitez que le <span class="wintitle"> serveur de collecte de données</span> renvoie une réponse, vous devez inclure <i><code> d_rtbd=json</code></i> dans votre requête. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemple de réponse {#sample-response}

Voir [Recevoir des données du serveur de collecte de données](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
