---
description: Le processus de transfert de données en temps réel sortant renvoie les données utilisateur sous la forme d’une série d’objets JSON transmis avec une méthode POST.
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: Transferts De Données Sortantes En Temps Réel
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 2%

---

# Transferts De Données Sortantes En Temps Réel {#real-time-outbound-data-transfers}

Le processus de transfert de données en temps réel sortant fournit des données utilisateur sous la forme d’une série de messages au format [!DNL JSON] à une plateforme de destination.

<!-- c_outbound_json.xml -->

## Recommandations

Pour utiliser cette méthode, la plateforme de destination doit répondre aux exigences suivantes :

* Il doit fournir un [!DNL URL] de point d’entrée qui peut se mettre à l’échelle pour recevoir un volume élevé de messages d’Audience Manager ;
* Elle doit accepter les données au format [!DNL JSON] (`Content-type: application/json`);
* Il doit accepter des transferts de données `HTTPS` sécurisés. [!DNL Audience Manager] n&#39;enverra pas de messages via le protocole `HTTP` non sécurisé.

## Fréquence

Cette méthode de transfert de données peut envoyer des données en temps quasi réel lorsque les utilisateurs remplissent les critères pour les segments. Les messages en temps réel ne sont diffusés que lorsque l’utilisateur est en ligne et activement visible sur le réseau Audience Manager Edge. En option, cette méthode peut également envoyer des lots de données hors ligne ou intégrées aussi fréquemment que toutes les 24 heures.

## Transferts par lots

Les transferts en temps réel et par lots sont envoyés au même point d’entrée et utilisent le même format de message. Lorsque les transferts par lots sont activés, la plateforme de destination voit un pic de volume de messages pendant la diffusion des messages par lots. La plupart des qualifications de segment envoyées par le biais de messages en temps réel seront répétées dans les messages par lots. Les transferts par lots incluent uniquement les qualifications de segment (ou les disqualifications) qui ont changé depuis la livraison du dernier lot.

## Limites de taux

Aucune limite de débit n’est définie sur le débit des messages diffusés. La définition de limites de débit peut entraîner une perte de données.

## Réponses requises

Par défaut, le serveur de destinataires doit renvoyer le code `200 OK` pour indiquer une réception réussie. D&#39;autres codes seront interprétés comme des échecs. Cette réponse est attendue dans les 3 000 millisecondes. En réponse à un échec, [!DNL Audience Manager] n’effectuera qu’une seule tentative.

## Paramètres

Le tableau suivant définit les éléments du fichier de données [!DNL JSON] que vous envoyez à la destination.

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
   <td colname="col3"> <p>Identifiant qui indique le type d’identifiants d’appareil contenus dans le message, dans la propriété User.DataPartner_UUID. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android IDs (GAID) : <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS IDs (IDFA) : <code> 20915</code> </li>
     <li>Identifiants Web/de cookie : varie selon la plateforme de destination</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>Représente le compte cible dans la plateforme de destination. Cet identifiant provient de la plateforme de destination.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Identifiant de l’objet « destination » Audience Manager. Cet identifiant provient d’Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Nombre total d’utilisateurs dans la demande de <code> POST</code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>Tableau d’objets utilisateur. Par défaut, chaque message contient entre 1 et 10 utilisateurs, afin de conserver une taille de message optimale. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>UUID <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Chaîne </p> </td> 
   <td colname="col3"> <p>UUID de la plateforme de destination pour l’identifiant global d’appareil. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Tableau </td> 
   <td colname="col3"> L’identifiant de zone géographique <span class="keyword"> Audience Manager</span> où nous avons vu cet appareil. Par exemple, si l’appareil a une activité à Paris (Europe), l’ID de région est <code> 6</code>. Voir <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> des identifiants de zone géographique, des emplacements et des noms d’hôte du serveur de collecte de données</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Tableau </p> </td> 
   <td colname="col3"> <p>Tableau d’objets de segment. Pour les messages en temps réel, le tableau contient tous les segments auxquels l’utilisateur appartient. Pour les messages par lots, le tableau contient uniquement les modifications de segment depuis le dernier lot.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Identifiant du segment. Dans la plupart des cas, il s’agit de l’identifiant de segment généré par Audience Manager (un entier). Dans certains cas, si la plateforme de destination le permet, les clients peuvent définir l’identifiant du segment dans l’interface utilisateur d’Audience Manager (champ de texte ouvert), qui est ensuite reflété dans cette propriété. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Entier </p> </td> 
   <td colname="col3"> <p>Définit le statut d’un utilisateur dans le segment. Accepte les valeurs suivantes : </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: actif (par défaut) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: inactive, désactivée ou non segmentée. </li> 
    </ul> <p>Les utilisateurs ne sont pas segmentés lorsqu’ils sont : </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Supprimé d’un segment en fonction de la règle de segment. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Supprimé d’un segment en fonction de l’intervalle de durée de vie <a href="../../../features/traits/segment-ttl-explained.md"> du segment</a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Déplacement vers un état inactif s’ils n’ont pas été vus au cours des 120 derniers jours. </li>
     <li>Supprimé en raison d’une demande de modification de la confidentialité (par exemple, <span class="keyword"> RGPD</span>)</li>
    </ul> <p>Tous les identifiants de partenaire synchronisés avec un identifiant Audience Manager<span class="keyword"> </span> recevront l’indicateur <code> "Status":"0"</code> lorsqu’un utilisateur n’est pas segmenté. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Heure à laquelle la qualification du segment utilisateur a été vérifiée le plus récemment.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Sécurité

Vous pouvez sécuriser votre processus de transfert de données sortantes en temps réel en [signant des requêtes HTTP](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) à l’aide de clés privées ou en vous authentifiant [!DNL Audience Manager] via le protocole [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md).

## Requête

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
