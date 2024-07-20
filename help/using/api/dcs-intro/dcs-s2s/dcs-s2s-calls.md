---
seo-title: Making Server-to-Server DCS API Calls
solution: Audience Manager
title: Lancement d’appels d’API DCS serveur à serveur
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: Appel de la syntaxe, de l’exemple et des paramètres lors des appels de l’API DCS serveur à serveur
exl-id: 977f4dfe-0beb-43c8-b64e-df4042427474
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 1%

---

# Lancement d’appels d’API DCS serveur à serveur {#making-server-to-server-dcs-api-calls}

Les appels requièrent le nom d’hôte du serveur DCS régional et l’identifiant utilisateur. Si vous ne disposez pas des identifiants utilisateur et de région requis, voir [Obtention des identifiants d’utilisateur et de région à partir d’une réponse DCS](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) et/ou [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Une fois que vous disposez des identifiants d’utilisateur et de région, vous pouvez effectuer des appels serveur à serveur vers le serveur de collecte de données. Reportez-vous à cette section pour consulter la syntaxe et les exemples.

>[!NOTE]
>
>Dans le code et les exemples, *italics* représente un espace réservé de variable. Remplacez la valeur réelle de l’espace réservé lorsque vous effectuez des appels serveur à serveur vers le [!DNL DCS].

## Syntaxe des appels et exemple {#call-syntax-example}

Une requête de base serveur à serveur qui envoie des données à [!DNL DCS] utilise la syntaxe illustrée ci-dessous.

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
   <td colname="col1"> <p><code> <i>domain alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l’appel contient : </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Votre alias de domaine attribué par <span class="keyword"> Audience Manager</span> (par exemple, <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Domaine de destination, qui est toujours <i><code> demdex.net</code></i>. Voir <a href="../../../reference/demdex-calls.md"> Signification des appels vers le domaine Demdex</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Le paramètre http header host qui affiche le nom du serveur régional <span class="wintitle"> DCS</span>. Le nom d’hôte est lié à un identifiant de région. C’est pourquoi vous en avez besoin avant d’effectuer ce type d’appels. Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Cette partie de l’appel : </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identifie l’appel en tant qu’appel d’événement. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Définit le début de la chaîne d’URL qui contient les données que vous souhaitez envoyer au serveur de collecte de données. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Il s’agit de la clé d’identifiant utilisateur unique qui contient la valeur d’identifiant utilisateur <span class="keyword"> Audience Manager</span> dans une paire clé-valeur. </p> <p>Utilisez <code><i>d_uuid</i></code> si vous transmettez l’identifiant utilisateur <span class="keyword"> Audience Manager</span>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Il s’agit de la clé d’identifiant utilisateur unique qui contient la valeur d’identifiant utilisateur <span class="keyword"> Experience Cloud</span> dans une paire clé-valeur. Voir aussi <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Obtention de l’ID utilisateur à partir du cookie du service d’ID</a>. </p> <p>Utilisez <i><code> d_mid</code></i> si vous transmettez un ID <span class="keyword"> Experience Cloud</span> capturé à partir du service <span class="keyword"> Experience Cloud</span> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Paramètres de réponse facultatifs. </p> <p> Aucun de ces éléments n’est nécessaire pour envoyer des données au <span class="wintitle"> DCS</span>. Cependant, si vous souhaitez que le <span class="wintitle"> DCS</span> renvoie une réponse, vous devez inclure <i><code> d_rtbd=json</code></i> dans votre requête. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exemple de réponse {#sample-response}

Voir [Recevoir des données du DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
