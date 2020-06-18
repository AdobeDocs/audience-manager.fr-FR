---
description: Le processus de transfert de données en temps réel sortant renvoie des données utilisateur sous la forme d’une série d’objets JSON transmis avec une méthode POST.
seo-description: Le processus de transfert de données en temps réel sortant renvoie des données utilisateur sous la forme d’une série d’objets JSON transmis avec une méthode POST.
seo-title: Transferts de données sortantes en temps réel
solution: Audience Manager
title: Transferts de données sortantes en temps réel
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 4%

---


# Transferts de données sortantes en temps réel {#real-time-outbound-data-transfers}

Le processus de transfert de données en temps réel sortant fournit des données utilisateur sous la forme d’une série de messages [!DNL JSON] formatés à une plateforme de destination.

<!-- c_outbound_json.xml -->

## Recommandations

Pour utiliser cette méthode, la plate-forme de destination doit répondre aux exigences suivantes :

* Il doit fournir un point de terminaison [!DNL URL] pouvant être mis à l&#39;échelle pour recevoir un volume élevé de messages d&#39;Audience Manager ;
* Il doit accepter les données au [!DNL JSON] format (`Content-type: application/json`);
* Il doit accepter `HTTPS` des transferts de données sécurisés. [!DNL Audience Manager] n&#39;enverra pas de messages via le `HTTP` protocole non sécurisé.

## Fréquence

Cette méthode de transfert de données peut envoyer des données en temps quasi réel, car les utilisateurs remplissent les conditions requises pour les segments. Les messages en temps réel ne sont diffusés que lorsque l’utilisateur est en ligne et qu’il est activement visible sur le réseau Audience Manager Edge. Cette méthode peut également envoyer des lots de données hors ligne ou intégrées aussi souvent que toutes les 24 heures.

## Transferts par lots

Les transferts en temps réel et par lots sont envoyés au même point de terminaison et utilisent le même format de message. Lorsque les transferts par lots sont activés, la plate-forme de destination voit un pic dans le volume des messages pendant la remise des messages par lot. La plupart des qualifications du segment envoyées par le biais de messages en temps réel seront répétées dans les messages par lots. Les transferts par lots incluront uniquement les qualifications (ou les non-qualifications) du segment qui ont changé depuis la livraison du dernier lot.

## Limites de taux

Aucune limite de débit n&#39;est fixée pour le débit des messages diffusés. La définition de limites de taux peut entraîner une perte de données.

## Réponses requises

Par défaut, le serveur destinataire doit renvoyer le `200 OK` code pour indiquer la réception réussie. Les autres codes seront interprétés comme des échecs. Cette réponse est attendue dans les 3 000 millisecondes. En cas d’échec, [!DNL Audience Manager] une seule tentative de réessai est effectuée.

## Paramètres

Le tableau suivant définit les éléments du fichier de [!DNL JSON] données que vous envoyez à la destination.

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
   <td colname="col3"> <p>ID qui indique le type d’ID de périphérique contenus dans le message, dans la propriété User.DataPartner_UUID. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Identifiants Android (GAID) : <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">ID iOS (IDFA) : <code> 20915</code> </li>
     <li>Identifiants Web/Cookie : varie selon la plateforme de destination</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Représente le compte de cible dans la plateforme de destination. Cet identifiant provient de la plateforme de destination.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>ID de l’objet Audience Manager "destination". Cet identifiant provient de l'Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Nombre total d’utilisateurs dans la <code> POST</code> requête. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>Tableau d’objets utilisateur. Par défaut, chaque message contiendra entre 1 et 10 utilisateurs, afin que la taille du message reste optimale. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>UUID <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>UUID de plate-forme de destination ou ID de périphérique global. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Tableau </td> 
   <td colname="col3"> Identifiant de région <span class="keyword"> d'Audience Manager</span> où nous avons vu cet appareil. Par exemple, si le périphérique avait une certaine activité à Paris (Europe), l’identifiant de région serait <code> 6</code>celui-ci. Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données</a> (DCS Region IDs, Locations, and Host Names). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>Tableau d’objets de segment. Pour les messages en temps réel, la baie contient tous les segments auxquels l'utilisateur appartient. Pour les messages par lot, la baie contient uniquement des modifications de segment depuis le dernier lot.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmnent.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Identificateur du segment. Dans la plupart des cas, il s’agit de l’identifiant de segment généré par l’Audience Manager (entier). Dans certains cas, si la plate-forme de destination le permet, les clients peuvent définir l’identifiant de segment dans l’interface utilisateur de l’Audience Manager (champ de texte ouvert), qui est alors répercuté dans cette propriété. </p> </td> 
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
     <li>Supprimé en raison d’une demande de modification de la confidentialité (c.-à-d. <span class="keyword"> RMMD</span>)</li>
    </ul> <p>Tous les identifiants de partenaire synchronisés avec un ID d’ <span class="keyword"> Audience Manager</span> reçoivent l’ <code> "Status":"0"</code> indicateur lorsqu’un utilisateur n’est pas segmenté. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Heure à laquelle la qualification du segment utilisateur a été vérifiée le plus récemment.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sécurité

Vous pouvez sécuriser votre processus de transfert de données sortant en temps réel en [signant des requêtes](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) HTTP à l’aide de clés privées ou en vous authentifiant [!DNL Audience Manager] via le protocole [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) .

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
