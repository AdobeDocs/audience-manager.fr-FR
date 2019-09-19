---
description: Adobe respecte toutes les normes du secteur en matière de gestion des exclusions. Lisez la suite pour obtenir des informations complètes sur les types d’exclusion pris en charge par Audience Manager.
seo-description: Adobe respecte toutes les normes du secteur en matière de gestion des exclusions. Lisez la suite pour obtenir des informations complètes sur les types d’exclusion pris en charge par Audience Manager.
seo-title: Gestion des exclusions
solution: Audience Manager
title: Gestion des exclusions
uuid: 61b43e0e-bfe3-497e-ade2-6a942a98407e
translation-type: tm+mt
source-git-commit: 50a6627568bd472dae1cfbdf5c6c824622766df1

---


# Gestion des exclusions{#opt-out-management}

Adobe respecte toutes les normes du secteur en matière de gestion des exclusions. Lisez la suite pour obtenir des informations complètes sur les types d’exclusion pris en charge par Audience Manager.

## Exclusion globale {#global-opt-out}

L’exclusion globale représente une exclusion dans Audience Manager et dans d’autres solutions Adobe Experience Cloud pour toutes les marques. Le tableau ci-dessous répertorie les méthodes utilisées pour l’exclusion globale :

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exclusion pour </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>La page <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Vos choix de confidentialité </a> propose des fonctionnalités d’1 clic qui permettent aux utilisateurs finaux de contrôler et d’exclure la collecte de données par les solutions publicitaires Adobe Experience Cloud (y compris Audience Manager). Consultez plus particulièrement la section réservée aux <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> clients professionnels </a> de la page Choix de confidentialité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Appels d’API directs vers Audience Manager </p> </td> 
   <td colname="col2"> <p>Vous pouvez vous désabonner de la collecte de données par toutes les marques d’Audience Manager en appelant l’API DCS ci-dessous et inclure l’ID utilisateur <a href="../../reference/ids-in-aam.md"> d’Audience Manager </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" —cookie "demdex=12345678901234567890123456789012345678;dextp=12;ST=12" </code> </p> <p>Par conséquent, nous définirons les cookies <code>demdex=NOTARGET</code> et <code>dextp=NOTARGET</code> pour l’ID utilisateur d’Audience Manager envoyé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Appareils mobiles </p> </td> 
   <td colname="col2"> <p>Voir les paramètres d’exclusion et de confidentialité pour : </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html" format="https" scope="external"> Périphériques Android </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html" format="https" scope="external"> Appareils iOS </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Vos utilisateurs finaux peuvent également se désabonner de la collecte de données globale en visitant les sites Web de nos partenaires du secteur.

* [La Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Suite aux demandes d’exclusion décrites ci-dessus :

* Audience Manager cessera la collecte, la segmentation ou l’activation de toutes les données.
* Les données historiques sont supprimées du profil utilisateur au bout de 120 jours.

## Exclusion au niveau partenaire {#partner-opt-out}

L’exclusion au niveau du partenaire permet de s’exclure de la collecte de données par des partenaires Audience Manager spécifiques. L’exclusion au niveau du partenaire fonctionne avec les appels d’ID [](../../features/declared-ids.md) déclarés et d’ID de périphérique, comme décrit dans les sections ci-dessous.

### Exclusion au niveau du partenaire avec appels d’ID déclarés

Suite à une exclusion au niveau du partenaire avec un appel d’ID déclaré :

* Le dernier ID de périphérique (ID[utilisateur unique](../../reference/ids-in-aam.md)Audience Manager) lié à l’ID [](../../reference/ids-in-aam.md) CRM est retiré de la collecte de données.
* Audience Manager interrompt la collecte, la segmentation ou l’activation des données pour le dernier ID de périphérique lié à l’ID CRM.
* Aucune donnée d’historique n’est supprimée.

<br/>

**Appels d’exclusion**

Lorsqu’Audience Manager reçoit une demande d’exclusion au niveau du partenaire, le fichier JSON renvoyé par le serveur de collecte de données contient le code [d’erreur 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), avec le message [!UICONTROL "Encountered opt out tag"], au lieu de l’ID utilisateur d’Audience Manager.

<!-- 

<p> 
 <ul id="ul_65EF2E1ED8F24457A35299E38AFE1DBE"> 
  <li id="li_832D0B507BC64782A5D3662FD5173A37">Audience Manager can pass in a declared ID opt-out alongside an Audience Manager UUID in the URL. </li> 
  <li id="li_D6C41CB385C5401D98156E5A3D79AAEE">The declared ID opt-out is stored in the Profile Cache Server (PCS) on a per-partner basis. There is no platform-level opt-out using declared IDs. Additionally, Audience Manager opts the user out from that particular region on the edge (the opt-out does not cross DCS regions). </li> 
 </ul> </p>

 -->

<!-- 

<p>See <a href="../../overview/data-security-and-privacy/data-privacy.md"> Data Privacy </a> for more information about opting-out of data collection. </p>

 -->



**Exemples**

Vous pouvez faire une demande d’exclusion d’ID déclarée avec les paires `d_cid` et `d_cid_ic` clé-valeur. Les paramètres hérités, comme `d_dpid` et `d_dpuuid` fonctionnent toujours, sont considérés comme obsolètes. Voir [CID remplace DPID et DPUUID](../../reference/cid.md). In the examples, *italics* indicates a variable placeholder.

**Exclusions avec CID et CID_IC**

Pour obtenir une description et une syntaxe, voir Variables [d’URL et Syntaxe pour les ID](../../features/declared-ids.md#variables-and-syntax)déclarés.

| Exclusion à l’aide de | Exemple de code |
|--- |--- |
| ID de fournisseur de données et ID d’utilisateur. | `https://domain name/demoptout.jpg?d_cid=123%01987...` |
| Code d’intégration et ID utilisateur. | `https://domain name/demoptout?d_cid_ic=456%01321...` |
| Plusieurs paires clé-valeur d_cid et d_cid_ic. | `https://domain name/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

### Exclusion au niveau partenaire avec appels d'ID de périphérique

Vous pouvez vous exclure de la collecte de données sur un ID de périphérique donné pour une marque en lançant les appels suivants à l’API [](/help/using/api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md)DCS :

| Exclusion à l’aide de | Exemple de code |
|--- |--- |
| Un ID utilisateur unique Audience Manager (`uuid`). | `http://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Un ID Experience Cloud (`mid`) | `http://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

En savoir plus sur `uuid`Audience Manager `mid` et `imsOrgId` dans l’ [](/help/using/reference/ids-in-aam.md)index des identifiants.

Suite à une exclusion au niveau du partenaire avec un appel d’ID de périphérique :

* L’ID de périphérique est retiré de la collecte de données.
* Audience Manager interrompt la collecte, la segmentation ou l’activation des données pour le partenaire, à partir de l’ID du périphérique.
* Aucune donnée d’historique n’est supprimée.
