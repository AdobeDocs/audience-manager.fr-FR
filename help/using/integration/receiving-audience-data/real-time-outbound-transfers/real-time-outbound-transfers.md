---
description: Le processus de transfert de données en temps réel sortant renvoie les données utilisateur sous la forme d’une série d’objets JSON transmis avec une méthode POST.
seo-description: Le processus de transfert de données en temps réel sortant renvoie les données utilisateur sous la forme d’une série d’objets JSON transmis avec une méthode POST.
seo-title: Transferts de données sortantes en temps réel
solution: Audience Manager
title: Transferts de données sortantes en temps réel
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: b76e905ec890dbe8270177d142dddb351438b039

---


# Transferts de données sortantes en temps réel {#real-time-outbound-data-transfers}

Le processus de transfert de données en temps réel sortant fournit les données utilisateur sous forme d’une série de messages [!DNL JSON] formatés vers une plateforme de destination.

<!-- c_outbound_json.xml -->

## Recommandations

Pour utiliser cette méthode, la plateforme de destination doit répondre aux exigences suivantes :

* Il doit fournir un point de terminaison [!DNL URL] pouvant être mis à l’échelle pour recevoir un volume élevé de messages d’Audience Manager ;
* It must accept data in  format ();[!DNL JSON]`Content-type: application/json`
* It must accept secure `HTTPS` data transfers. [!DNL Audience Manager] will not send messages through the unsecure  protocol.`HTTP`

## Fréquence

This data transfer method can send data in near real-time as users qualify for segments. Real-time messages are only delivered while the user is online and actively visible to the Audience Manager Edge network. Cette méthode peut également envoyer des lots de données hors ligne ou intégrées aussi souvent que toutes les 24 heures.

## Batch Transfers

Both real-time and batch transfers are sent to the same endpoint and use the same message format. Lorsque les transferts par lot sont activés, la plateforme de destination voit un pic dans le volume des messages pendant la remise des messages par lot. Bon nombre des qualifications du segment envoyées par le biais de messages en temps réel seront répétées dans les messages par lots. Les transferts par lots incluront uniquement les qualifications (ou non-qualifications) du segment qui ont changé depuis la livraison du dernier lot.

## Limites de taux

Aucune limite de débit n'est fixée pour le débit des messages diffusés. La définition de limites de taux peut entraîner une perte de données.

## Réponses requises

Par défaut, le serveur destinataire doit renvoyer le `200 OK` code pour indiquer la réception réussie. Les autres codes seront interprétés comme des échecs. Cette réponse est attendue dans les 3 000 millisecondes. En cas d’échec, [!DNL Audience Manager] une seule tentative est effectuée.

## Paramètres

Le tableau suivant définit les éléments du fichier de [!DNL JSON] données renvoyé.

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
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS IDs (IDFA):  20915<code></code> </li>
     <li>ID de cookie/Web : varie selon la plateforme de destination</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Represents the target account in the destination platform. This ID originates from the destination platform.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>The ID of the Audience Manager “destination” object. This ID originates from Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Total number of users in the  POST request.<code></code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Utilisateurs</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>An array of user objects. By default, each message will contain between 1 and 10 users, to keep the message size optimal. </p> </td> 
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
   <td colname="col3"> Identifiant de région d’Audience Manager <span class="keyword"></span> où nous avons vu ce périphérique. Par exemple, si le périphérique avait une certaine activité à Paris (Europe), l’ID de région serait <code> 6</code>. Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données</a> (DCS Region IDs, Locations, and Host Names). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>Tableau d’objets de segment. Pour les messages en temps réel, le tableau contient tous les segments auxquels appartient l’utilisateur. Pour les messages par lot, le tableau contient uniquement les modifications de segment depuis le dernier lot.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Identifiant du segment. Dans la plupart des cas, il s’agit de l’identifiant de segment généré par Audience Manager (entier). Dans certains cas, si la plate-forme de destination le permet, les clients peuvent définir l’identifiant de segment dans l’interface utilisateur d’Audience Manager (champ de texte ouvert), ce qui est répercuté dans cette propriété. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Définit l’état d’un utilisateur dans le segment. Accepts the following values: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1: Active (default)</code> </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0: Inactive, opted-out, or unsegmented.</code> </li> 
    </ul> <p>Users are unsegmented when they are: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Removed from a segment based on the segment rule. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Removed from a segment based on the segment's  time-to-live interval.<a href="../../../features/traits/segment-ttl-explained.md"></a> </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Moved to an inactive state if they have not been seen for the last 120-days. </li>
     <li>Removed due to a privacy change request (i.e. [!DNL GDPR])</li>
    </ul> <p>All partner IDs that are synced to an  Audience Manager ID will receive the  "Status":"0" flag when a user is unsegmented.<span class="keyword"></span><code></code> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>The time when the user-segment qualification was most recently verified.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sécurité

Vous pouvez sécuriser votre processus de transfert de données sortantes en temps réel en [signant des requêtes](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) HTTP à l’aide de clés privées ou en vous [!DNL Audience Manager] authentifiant via le protocole [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) .

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
