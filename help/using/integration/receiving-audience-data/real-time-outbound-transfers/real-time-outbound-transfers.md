---
description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-description: Le processus de transfert de données en temps réel sortant renvoie les données utilisateur sous la forme d’une série d’objets JSON transmis avec une méthode POST.
seo-title: Transferts de données sortantes en temps réel
solution: Audience Manager
title: Transferts de données sortantes en temps réel
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 4e84682dea46f5b6c76464c66199f7a468bec334

---


# Transferts de données sortantes en temps réel {#real-time-outbound-data-transfers}

Le processus de transfert de données en temps réel sortant fournit les données utilisateur sous forme d’une série de messages [!DNL JSON] formatés vers une plateforme de destination.

<!-- c_outbound_json.xml -->

## Recommandations

Pour utiliser cette méthode, la plateforme de destination doit répondre aux exigences suivantes :

* Il doit fournir un point de terminaison [!DNL URL] pouvant être mis à l’échelle pour recevoir un volume élevé de messages d’Audience Manager ;
* It must accept data in  format ();[!DNL JSON]`Content-type: application/json`
* Il doit accepter des transferts `HTTPS` de données sécurisés. [!DNL Audience Manager] will not send messages through the unsecure  protocol.`HTTP`

## Fréquence

Cette méthode de transfert de données permet d’envoyer des données en temps quasi réel, car les utilisateurs remplissent les conditions requises pour les segments. Real-time messages are only delivered while the user is online and actively visible to the Audience Manager Edge network. Optionally, this method can also send batches of offline or onboarded data as frequently as every 24-hours.

## Transferts par lots

Both real-time and batch transfers are sent to the same endpoint and use the same message format. Lorsque les transferts par lot sont activés, la plateforme de destination voit un pic dans le volume des messages pendant la remise des messages par lot. Bon nombre des qualifications du segment envoyées par le biais de messages en temps réel seront répétées dans les messages par lots. Les transferts par lots incluront uniquement les qualifications (ou non-qualifications) du segment qui ont changé depuis la livraison du dernier lot.

## Rate Limits

There are no rate limits set on the throughput of delievered messages. Setting rate limits could lead to data loss.

## Required Responses

By default, the recipient server must return the  code to indicate successful receipt. `200 OK` Other codes will be interpreted as failures. This response is expected within 3000 milliseconds. En cas d’échec, [!DNL Audience Manager] une seule tentative est effectuée.

## Paramètres

The following table defines the elements in the  data file that you send to the destination.[!DNL JSON]

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Paramètre </th> 
   <th colname="col2" class="entry"> Type de données </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>ProcessTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Heure d’exécution de la requête. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>ID qui indique le type d’ID de périphérique contenu dans le message, dans la propriété User.DataPartner_UUID. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Identifiants Android (GAID) : <code> 2014</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">ID iOS (IDFA) : <code> 2015</code> </li>
     <li>ID de cookie/Web : varie selon la plateforme de destination</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Représente le compte cible dans la plateforme de destination. Cet ID provient de la plateforme de destination.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>ID de l’objet "destination" d’Audience Manager. Cet identifiant provient d’Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Nombre total d’utilisateurs dans la requête <code> POST</code> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Utilisateurs</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>Tableau d’objets utilisateur. Par défaut, chaque message contiendra entre 1 et 10 utilisateurs, afin que la taille du message reste optimale. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>The  Audience Manager UUID.<span class="keyword"></span> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Destination platform UUID or the global device ID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Years</i></code> </td> 
   <td colname="col2"> Tableau </td> 
   <td colname="col3"> The  Audience Manager region ID where we've seen this device. <span class="keyword"></span> For instance, if the device had some activity in Paris (Europe), the region ID would be  6. <code></code> Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données</a> (DCS Region IDs, Locations, and Host Names). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>An array of segment objects. For real-time messages, the array contains all of the segments the user belongs to. For batch messages, the array contains only segment changes since the last batch.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Identifiant du segment. Dans la plupart des cas, il s’agit de l’identifiant de segment généré par Audience Manager (entier). Dans certains cas, si la plate-forme de destination le permet, les clients peuvent définir l’identifiant de segment dans l’interface utilisateur d’Audience Manager (champ de texte ouvert), ce qui est répercuté dans cette propriété. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Définit l’état d’un utilisateur dans le segment. Accepte les valeurs suivantes : </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Actif (par défaut) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inactif, désactivé ou non segmenté. </li> 
    </ul> <p>Les utilisateurs ne sont pas segmentés lorsqu’ils sont : </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Supprimé d’un segment en fonction de la règle de segment. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Supprimé d’un segment en fonction de l’intervalle <a href="../../../features/traits/segment-ttl-explained.md"> de</a>durée de vie du segment. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Déplacé vers un état inactif s’ils n’ont pas été vus depuis 120 jours. </li>
     <li>Removed due to a privacy change request (i.e. [!DNL GDPR])</li>
    </ul> <p>Tous les identifiants de partenaire synchronisés avec un <span class="keyword"> ID Audience Manager</span> recevront l’indicateur <code> "État":"0"</code> lorsqu’un utilisateur n’est pas segmenté. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>The time when the user-segment qualification was most recently verified.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sécurité

You can secure your real-time outbound data transfer process by signing HTTP requests using private keys or by having  authenticate through the OAuth 2.0 protocol.[](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md)[!DNL Audience Manager][](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md)

## Demande

Une requête en temps réel peut se présenter comme suit :

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}
```
