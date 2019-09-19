---
description: Le processus de transfert de données en temps réel sortant renvoie les données utilisateur sous la forme d’une série d’objets JSON transmis avec une méthode POST.
seo-description: Le processus de transfert de données en temps réel sortant renvoie les données utilisateur sous la forme d’une série d’objets JSON transmis avec une méthode POST.
seo-title: Transferts de données sortantes en temps réel
solution: Audience Manager
title: Transferts de données sortantes en temps réel
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
translation-type: tm+mt
source-git-commit: 425315a0a6aa739a90e34deb270ac21df9b88d31

---


# Transferts de données sortantes en temps réel {#real-time-outbound-data-transfers}

Le processus de transfert de données en temps réel sortant renvoie les données utilisateur sous la forme d’une série d’ [!DNL JSON] objets transmis avec une `POST` méthode.

<!-- c_outbound_json.xml -->

## Recommandations

Pour utiliser cette méthode, nous vous recommandons de contacter votre partenaire de données :

* Accepte les données au [!DNL JSON] format.
* Fournit une URL qui peut être utilisée par l’ `POST` appel pour renvoyer des données.
* Accepte les transferts `HTTPS` de données sécurisés. [!DNL Audience Manager] n'enverra pas ce fichier avec le `HTTP` protocole non sécurisé.

## Fréquence

Cette méthode de transfert de données permet d’envoyer des données en temps quasi réel, car les utilisateurs remplissent les conditions requises pour les segments. De plus, cette méthode peut envoyer des lots de données hors ligne ou intégrées aussi souvent que toutes les 24 heures.

## Réponses requises

Par défaut, le serveur destinataire doit renvoyer le `200 OK` code pour indiquer la réception réussie. Les autres codes seront interprétés comme des échecs. Cette réponse est attendue dans les 3 000 millisecondes. En cas d’échec, [!DNL Audience Manager] 1 nouvelle tentative sera effectuée uniquement.

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
   <td colname="col3"> <p>ID indiquant si le fichier contient des ID Android ou iOS. Utilise les valeurs d’ID suivantes : </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Identifiants Android (GAID) : <code> 2014</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">ID iOS (IDFA) : <code> 2015</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>ID client utilisé par le système auquel vous envoyez des données. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>ID qui vous est attribué par votre partenaire de destination. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Nombre total d’utilisateurs dans la requête <code> POST</code> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Utilisateurs</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>Tableau d’objets utilisateur. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>UUID <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>UUID du partenaire de données. Laissez ce champ vide si votre partenaire de données n’a pas d’UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Region</i></code> </td> 
   <td colname="col2"> Tableau </td> 
   <td colname="col3"> Identifiant de région d’Audience Manager <span class="keyword"></span> où nous avons vu ce périphérique. Par exemple, si le périphérique avait une certaine activité à Paris (Europe), l’ID de région serait <code> 6</code>. Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données</a> (DCS Region IDs, Locations, and Host Names). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>Tableau d’objets de segment. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Mappage de destination de l’ID de segment. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>État</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Définit l’état d’un utilisateur dans le segment. Accepte ce qui suit : </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Actif (par défaut) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inactif, désactivé ou non segmenté. </li> 
    </ul> <p>Les utilisateurs ne sont pas segmentés lorsqu’ils sont : </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Supprimé d’un segment en fonction de la règle de segment. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Supprimé d’un segment en fonction de l’intervalle <a href="../../../features/traits/segment-ttl-explained.md"> de</a>durée de vie du segment. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Déplacé vers un état inactif s’ils n’ont pas été vus depuis 120 jours. </li> 
    </ul> <p>Tous les identifiants de partenaire synchronisés avec un <span class="keyword"> ID Audience Manager</span> recevront l’indicateur <code> "État":"0"</code> lorsqu’un utilisateur n’est pas segmenté. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Heure de la dernière qualification de segment.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sécurité

Vous pouvez sécuriser votre processus de transfert de données sortantes en temps réel en [signant des requêtes](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) HTTP à l’aide de clés privées ou en vous [!DNL Audience Manager] authentifiant via le protocole [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) .

## Exemple de code

Une réponse de données en temps réel peut ressembler à ce qui suit :

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
