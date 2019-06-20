---
description: Le processus de transfert des données en temps réel sortant renvoie les données utilisateur sous la forme d'une série d'objets JSON transmis avec une méthode POST.
seo-description: Le processus de transfert des données en temps réel sortant renvoie les données utilisateur sous la forme d'une série d'objets JSON transmis avec une méthode POST.
seo-title: Transferts de données sortantes en temps réel
solution: Audience Manager
title: Transferts de données sortantes en temps réel
uuid: 1895 e 818-7 ab 8-4569-a 920-4 b 0 a 4 c 8 b 83 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Real-Time Outbound Data Transfers {#real-time-outbound-data-transfers}

The outbound real-time data transfer process returns user data as a series of [!DNL JSON] objects passed in with a `POST` method.

<!-- c_outbound_json.xml -->

## Recommandations

Pour utiliser cette méthode, nous recommandons à votre partenaire de données :

* Accepts data in [!DNL JSON] format.
* Provides a URL that can be used by the `POST` call to return data.
* Accepts secure `HTTPS` data transfers. [!DNL Audience Manager] n&#39;envoie pas ce fichier avec `HTTP` le protocole non sécurisé.

## Fréquence

Cette méthode de transfert de données peut envoyer des données en temps quasi réel lorsque les utilisateurs remplissent les critères de segments. De plus, cette méthode peut envoyer des lots de données hors ligne ou intégrées aussi fréquemment que toutes les 24 heures.

## Réponses obligatoires

By default, the recipient server must return the `200 OK` code to indicate successful receipt. D&#39;autres codes seront interprétés comme des échecs. Cette réponse est attendue sous 3 000 millisecondes. In response to a failure, [!DNL Audience Manager] will make 1 retry attempt only.

## Paramètres

The following table defines the elements in the returned [!DNL JSON] data file.

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
   <td colname="col1"> <code><i>Processtime</i></code> </td> 
   <td colname="col2"> <p>Datetime </p> </td> 
   <td colname="col3"> <p>Heure à laquelle la requête a été exécutée. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ DPID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>ID indiquant si le fichier contient des ID Android ou ios. Utilise les valeurs d'ID suivantes : </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android IDs (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS IDs (IDFA): <code> 20915</code> </li> 
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ ID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>ID client utilisé par le système auquel vous envoyez des données. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Destination_ ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>ID qui vous a été attribué par votre partenaire de destination. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_ count</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Total number of users in the <code> POST</code> request. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Utilisateurs</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>Tableau d'objets utilisateur. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ UUID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>The <span class="keyword"> Audience Manager</span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Datapartner_ UUID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>UUID du partenaire de données. Laissez vide si votre partenaire de données n'a pas de valeur UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_ Régions</i></code> </td> 
   <td colname="col2"> Tableau </td> 
   <td colname="col3"> The <span class="keyword"> Audience Manager</span> region ID where we've seen this device. For instance, if the device had some activity in Paris (Europe), the region ID would be <code> 6</code>. Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md">ID de zone géographique, emplacements et noms d’hôte du serveur de collecte de données</a> (DCS Region IDs, Locations, and Host Names). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>Tableau d'objets de segment. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment_ ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Correspondance de destination d'identifiant de segment. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>État</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Définit l'état d'un utilisateur dans le segment. Accepte les éléments suivants : </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Actif (par défaut) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inactif, désactivé ou non segmenté. </li> 
    </ul> <p>Les utilisateurs ne sont pas segmentés lorsqu'ils sont : </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Suppression d'un segment en fonction de la règle de segment. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Removed from a segment based on the segment's <a href="../../../features/traits/segment-ttl-explained.md"> time-to-live interval</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Déplacement vers un état inactif si elles n'ont pas été vues pendant les 120 derniers jours. </li> 
    </ul> <p>All partner IDs that are synced to an <span class="keyword"> Audience Manager</span> ID will receive the <code> "Status":"0"</code> flag when a user is unsegmented. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Datetime</i></code> </td> 
   <td colname="col2"> <p>Datetime </p> </td> 
   <td colname="col3"> <p>Heure à laquelle un visiteur de site est qualifié pour la caractéristique. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Sécurité

You can secure your real-time outbound data transfer process by [signing HTTP requests](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) using private keys or by having [!DNL Audience Manager] authenticate through the [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) protocol.

## Exemple de code

Une réponse de données en temps réel peut se présenter comme suit :

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
