---
description: Codes d’erreur et messages générés par les serveurs de collecte de données (DCS) répertoriés dans l’ordre numérique par identifiant de code.
title: Codes d’erreur DCS, messages et exemples
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: f8ba09b674b71045e08f6d171471cdcdd0efb265
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 3%

---

# Codes d’erreur DCS, messages et exemples {#dcs-error-codes-messages-and-examples}

Codes d&#39;erreur et messages générés par le [!UICONTROL Data Collection Servers] ([!DNL DCS]) répertoriés dans l&#39;ordre numérique par code ID.

Dans les tableaux ci-dessous, l’*italique* représente un espace réservé de variable.

## Codes d’erreur système {#system-error-codes}

| Code d’erreur | Message d’erreur | Description |
|---|---|---|
| 0 | Erreur non spécifiée | Il s’agit d’une erreur fourre-tout qui gère des événements qui ne sont pas couverts par les autres gestionnaires d’erreur. Le dépannage de cette erreur est difficile. Elle peut être causée par diverses actions ou événements inconnus. Si vous recevez cette erreur, effectuez à nouveau votre requête [!DNL DCS]. Contactez votre représentant [!DNL Adobe] si le problème persiste. |
| 1 | Configuration du nom d&#39;hôte introuvable : `hostname` | Le nom d’hôte envoyé dans la demande n’a pas été configuré par notre équipe d’approvisionnement de partenaires. Contactez votre représentant [!DNL Adobe] si ce message d’erreur s’affiche. |
| 2 | Valeur de `d_orgid` non valide (configuration introuvable pour cet ID d’organisation) : `ID` | L’ID d’organisation est incorrect. Vérifiez votre ID et effectuez une nouvelle requête. Si vous ne connaissez pas votre identifiant d’organisation ou si vous ne l’avez pas, consultez la section « Page d’administration » [Liaison d’organisations et de comptes](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) pour plus d’informations sur la manière de le trouver. |
| 10 | Impossible d’évaluer les caractéristiques | Les caractéristiques de la requête ont été évaluées en partie ou n’ont pas du tout été évaluées. Contactez votre représentant [!DNL Adobe] si le problème persiste. |

## Codes d&#39;erreur d&#39;intégration {#integration-error-codes}

| Code d’erreur | Message d’erreur | Description |
|---|---|---|
| 100 | Impossible de récupérer le nom d’hôte pour la requête | Un appel [!DNL API] n’a pas envoyé l’en-tête [!DNL HTTP] hôte dans la requête. Ajoutez l’en-tête hôte à l’appel et réessayez. La plupart des navigateurs et des clients [!DNL API] le font automatiquement. |
| 101 | Identifiant de [!DNL Experience Cloud] non valide transmis dans `ID` | L’appel [!DNL DCS] contient un ID de [!DNL Experience Cloud] non valide. Vérifiez la paire clé-valeur `d_mid=` dans la chaîne d’en-tête. Vérifiez que vous transmettez l’ID d’[!DNL Experience Cloud] correct, puis réessayez. |
| 102 | [!DNL AAM ID] non valide transmis dans la demande `ID` | L’appel [!DNL DCS] contient un ID de [!DNL Audience Manager] non valide. Vérifiez la paire clé-valeur `d_uuid=` dans la chaîne d’en-tête. Vérifiez que vous transmettez l’ID d’[!DNL Audience Manager] correct, puis réessayez. |
| 104 | Tous les ID de client ne sont pas valides | Tous les ID de client de votre appel ne sont pas valides. Vérifiez vos identifiants et réessayez. |
| 109 | Le référent `HTTP referer` n’est pas autorisé pour les `Partner ID` de partenaire. | L’en-tête `HTTP referer` de l’appel n’est pas autorisé pour l’ID de partenaire de l’appel. Vérifiez que l’en-tête du `HTTP referer` est correct. |
| 111 | Jeton `IMS` non valide reçu | Renvoyé pour les intégrations [!DNL Audience Manager] - [!DNL Adobe Target]. L’erreur est générée lorsqu’un appel est effectué au [!DNL DCS], contenant un jeton d’[!DNL IMS] non valide. Le jeton est peut-être mal formé, il a expiré ou l’utilisateur n’est peut-être pas autorisé à accéder à la ressource requise. |

## Codes D’Erreur D’Opt-Out {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de code </th> 
   <th colname="col2" class="entry"> Message </th> 
   <th colname="col3" class="entry"> Description </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>Balise d’opt-out rencontrée pour l’ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un client s’est opposé à la réception de publicités basées sur les intérêts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookies bloqués </p> </td> 
   <td colname="col3"> <p>Renvoyé lorsque le navigateur de l’utilisateur bloque les cookies tiers.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Relation de confiance rencontrée via <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>L’utilisateur a lancé un processus d’opt-out via NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Les demandes en provenance de ce pays sont bloquées par le partenaire </p> </td> 
   <td colname="col3"> <p>En fonction de l’adresse IP, le <span class="wintitle"> DCS</span> bloque les requêtes provenant de pays où le partenaire a délibérément limité le trafic. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Les demandes provenant de ce pays ne sont pas autorisées </p> </td> 
   <td colname="col3"> <p>En fonction de l’adresse IP, le <span class="wintitle"> DCS</span> bloque les requêtes provenant des pays suivants : </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">Cuba (CU) </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">Iran (IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">Corée du Nord (KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">Soudan (SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">Syrie (SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Codes d’erreur de récupération du profil {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de code </th> 
   <th colname="col2" class="entry"> Message </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> Impossible de lire les caractéristiques du cache de profil pour l’ID : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyé lorsqu’un profil utilisateur ne peut pas être lu à partir de notre stockage interne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Impossible de lire les ID d’appareil à partir du cache de profil pour l’ID de client : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyé lorsque l’ID d’appareil <a href="../../../reference/ids-in-aam.md"></a> ne peut pas être récupéré pour une règle de fusion de lien de profil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Impossible de lire le client associé pour l’ID d’appareil : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyé lorsque l’ID de client <a href="../../../reference/ids-in-aam.md"> (UUID)</a> associé à un ID d’appareil ne peut pas être récupéré pour une règle de fusion Dernière authentification dans notre stockage interne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Impossible de lire le cluster d'appareils pour l'ID : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Les identifiants d’appareil liés du même cluster de graphiques d’appareils ne peuvent pas être renvoyés pour cet identifiant d’appareil. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Impossible d'effectuer la migration car la lecture du profil a échoué pour l'appareil principal </p> </td> 
   <td colname="col3"> <p>Si vous recevez cette erreur, il se peut que nous rencontrions des problèmes d’évolutivité avec notre banque de données (<span class="wintitle"> PCS</span>). Contactez votre représentant Adobe si le problème persiste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Impossible d'effectuer la migration de <code><i>ID</i></code> vers <code><i>ID</i></code>, car la lecture du profil a échoué pour <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Si vous recevez cette erreur, il se peut que nous rencontrions des problèmes d’évolutivité avec notre banque de données (<span class="wintitle"> PCS</span>). Contactez votre représentant Adobe si le problème persiste. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Codes d&#39;avertissement d&#39;intégration {#integration-warning-codes}

| ID de code | Message | Description |
| --- | --- | --- |
| 300 | ID de client non valide `_ID_` | L’ID de client n’est pas valide (valeurs manquantes pour la source de données, codes d’intégration manquants, format non valide pour les sources de données, ID de client bloqué, ID de client vide, tentative d’accès non autorisée à une source de données qui n’appartient pas au partenaire). |
| 301 | Nombre maximal d’ID de client dépassé. Le maximum autorisé est de `_maximum allowed_`. `_maximum found_` trouvé. | Le nombre d’ID de client associés à une source de données entre appareils dépasse le nombre autorisé d’ID entre appareils par requête. Ces ID incluent des ID sur l’ensemble des appareils, des appareils mobiles ou des cookies. La limite est actuellement définie sur 10. |
| 302 | ID de client non autorisé `_ID_` | Renvoyé lorsque la source de données de l’ID client n’appartient pas à l’ID d’organisation actuel. Si vous ne connaissez pas votre identifiant d’organisation ou si vous ne l’avez pas, consultez la section « Rechercher votre identifiant d’organisation » dans [Liaisons d’organisations et de comptes](https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html) pour plus d’informations sur la manière de le trouver. |
| 303 | ID de client bloqué `_ID_` | Renvoyé lorsque l’ID de client a été identifié comme malveillant et a été ajouté à une liste bloquée. |
| 304 | ID de source de données bloqué `_ID_` | Renvoyé lorsque l’ID de la source de données a été identifié comme malveillant et a été ajouté à une liste bloquée |
| 306 | ID d’appareil déclaré bloqué `_ID_` | L’ID d’appareil a été identifié comme malveillant et a été ajouté à une liste bloquée. Cela peut se produire lorsque nous recevons un nombre extrême de requêtes DCS contenant cet ID d’appareil en peu de temps. |
| 307 | Opération de profil bloquée pour `_ID_` | Une action de lecture/écriture a été bloquée car un ID a été identifié comme malveillant et a été ajouté à une liste bloquée. Voir code d&#39;erreur 306. |
| 309 | L’ID de client `_ID_` a été ignoré, car il dépassait la limite des ID de client déclarés par demande | En rapport avec l’erreur 301. Cette erreur indique quel ID de client a été ignoré car la limite a été dépassée.<br><br>Par exemple, si 12 ID de client sont déclarés lors de l’appel DCS, deux d’entre eux seront ignorés. Afin de relayer ceux qui ont été ignorés, cette erreur apparaîtra deux fois dans la réponse (une fois pour chacun des ID de client ignorés ). |
| 310 | L’ID de client a été ignoré car il dépassait la limite pour un espace de noms donné. L’ID de l’espace de noms est `_ID_`, l’ID du client est `_ID_`. | Ce code d’erreur est renvoyé si plus de 3 identifiants de client sont déclarés pour le même espace de noms ( `DPID`) lors d’un appel DCS.<br><br>`https://partner.demdex.net/event?d_rtbd=json&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one`<br><br>Dans cet exemple de requête DCS, il existe 4 identifiants déclarés pour le même espace de noms (avec le code d’intégration un). L&#39;un des ID est ignoré et l&#39;erreur 310 est renvoyée. |
| 311 | La requête contient des paramètres non valides | Le DCS renvoie ce code d’erreur lorsqu’au moins un paramètre d’URL n’est pas correctement encodé. Dans ce cas, le serveur de collecte de données ignore l’ensemble de la requête.<br><br>`http(s)://partner.demdex.net/event?d_event=imp&d_rtbd=json&d_src=38454&d_site=%esid!&d_creative=%ecid!&d_adgroup=%eaid!&d_placement=%epid!&d_campaign=%ebuy!&d_adsrc=48123`<br><br>Dans l’exemple de requête ci-dessus, la séquence `%` est incorrectement codée. Par conséquent, le DCS n&#39;en tiendra pas compte.<br><br>L’exemple correctement encodé doit se présenter comme suit :<br><br>`http(s)://partner.demdex.net/event?d_event=imp&d_rtbd=json&d_src=38454&d_site=%25esid!&d_creative=%25ecid!&d_adgroup=%25eaid!&d_placement=%25epid!&d_campaign=%25ebuy!&d_adsrc=48123` |
| 312 | La requête contient un ID d’appareil global non valide | Le serveur de collecte de données renvoie ce code d’erreur lorsque la requête contient un ID de périphérique global non valide. DCS ignore l’ID non valide et renvoie une erreur 312 avec les erreurs spécifiques de l’ID non valide. Consultez les sections [Sources de données globales](../../../features/global-data-sources.md) et [Index des identifiants dans Audience Manager](../../../reference/ids-in-aam.md) pour obtenir des informations détaillées sur les formats d’identifiant publicitaire d’appareil corrects et les sources de données globales correspondantes.<br><br>Exemple d’appel incorrect : `"http://partner.demdex.net/event?d_rtbd=json&d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"`<br><br>Explication : un IDFA (20915 DPID) doit être un identifiant en majuscules. L’identifiant fourni dans la requête est en minuscules. |
| 313 | L’ID de CMP n’est pas présent dans le GCL | Lorsque la `gdpr=1` et la chaîne de caractères IAB TC sont générées par un ID de CMP qui n’est pas présent dans la version mise en cache d’Audience Manager de la liste globale de CMP au moment de l’évaluation, le plug-in Audience Manager pour IAB TCF ignore la chaîne de caractères IAB TC et traite la requête comme d’habitude. La macro IAB TCF v2.2 ${GDPR} est définie sur 0 et la macro ${GDPR\_CONSENT\_XXX} est vide. |
| 314 | L’ID de CMP est marqué comme supprimé dans GCL. | Lorsque `gdpr=1` et la chaîne IAB TC sont générées par une CMP marquée comme supprimée dans notre version mise en cache de la liste globale de CMP, le plug-in Audience Manager pour IAB TCF ignore la chaîne TC et traite la demande comme d’habitude, si le temps d’évaluation est passé le temps de suppression de la liste globale de CMP. La macro IAB TCF v2.2 ${GDPR} est définie sur 0 et la macro ${GDPR\_CONSENT\_XXX} est vide. |
| 315 | Chaîne de consentement indiquant aucun consentement | Lorsqu’aucun consentement n’est fourni, le module externe Audience Manager pour IAB TCF désinscrit l’utilisateur de la collecte de données supplémentaire ou interrompt complètement l’appel si aucun contexte de partenaire n’est détecté. |

## Exemples de messages de code d’erreur {#sample-error-codes}

Le [!DNL DCS] renvoie des codes d’erreur et des messages dans un objet [!DNL JSON] ou dans un en-tête X- dans la chaîne de réponse HTTP.

### Exemple de code d’erreur et de message DCS

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### X-Error

Les codes d’erreur capturés par l’en-tête X- apparaissent dans la chaîne d’URL comme suit : `X-Error: 101,102`.

[Conditions de concurrence et gestion des erreurs](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
