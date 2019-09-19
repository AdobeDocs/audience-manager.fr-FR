---
description: Codes d’erreur et messages générés par les serveurs de collecte de données (DCS) répertoriés dans l’ordre numérique par ID de code.
seo-description: Codes d’erreur et messages générés par les serveurs de collecte de données (DCS) répertoriés dans l’ordre numérique par ID de code.
seo-title: Codes, messages et exemples d’erreur des serveurs de collecte de données
solution: Audience Manager
title: Codes, messages et exemples d’erreur des serveurs de collecte de données
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Codes, messages et exemples d’erreur des serveurs de collecte de données {#dcs-error-codes-messages-and-examples}

Codes d’erreur et messages générés par le [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]) répertoriés dans l’ordre numérique par ID de code.

In the tables below, *italics* represents a variable placeholder.

## Codes d'erreur système {#system-error-codes}

<table id="table_43F4321BEA6A4D1BBDFE2E9FB4402914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de code </th> 
   <th colname="col2" class="entry"> Message d’erreur </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>0 </p> </td> 
   <td colname="col2"> <p>Erreur non spécifiée </p> </td> 
   <td colname="col3"> <p>Il s’agit d’une erreur fourre-tout qui gère les événements qui ne sont pas couverts par les autres gestionnaires d’erreur. La résolution de cette erreur est difficile. Elle peut être causée par divers événements ou actions inconnus. </p> <p>Si vous recevez cette erreur, essayez à nouveau votre demande <span class="wintitle"> DCS</span> . Contactez votre représentant Adobe si le problème persiste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>1 </p> </td> 
   <td colname="col2"> <p>Impossible de trouver la configuration du nom d'hôte : <code><i>hostname</i></code> </p> </td> 
   <td colname="col3"> <p>Le nom d’hôte envoyé dans la demande n’a pas été configuré par notre équipe de mise en service partenaire. Contactez votre représentant Adobe si ce message d’erreur s’affiche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>2 </p> </td> 
   <td colname="col2"> <p>Valeur <code> d_orgid</code> non valide (impossible de trouver une configuration pour cet ID d'organisation) : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>L'ID d'organisation est incorrect. </p> <p>Vérifiez votre ID et réessayez. Si vous ne connaissez pas ou ne possédez pas votre ID d’organisation, consultez la section "Page d’administration" dans Administration <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html" format="https" scope="external"> d’</a> Experience Cloud pour savoir comment le trouver. </p> </td> 
  </tr>
 </tbody>
</table>

## Codes d’erreur d’intégration {#integration-error-codes}

<table id="table_EFF06FB3D045459BA7802872AF22DF79"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de code </th> 
   <th colname="col2" class="entry"> Message </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>100 </p> </td> 
   <td colname="col2"> <p>Impossible de récupérer le nom d'hôte pour la requête </p> </td> 
   <td colname="col3"> <p>Un appel d’API n’envoyait pas l’en-tête HTTP hôte dans la requête. </p> <p>Ajoutez l’en-tête hôte à l’appel et réessayez. Notez que la plupart des navigateurs et des clients API le font automatiquement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>101 </p> </td> 
   <td colname="col2"> <p>ID Experience Cloud non valide transmis dans <code><i>l’ID</i></code> </p> </td> 
   <td colname="col3"> <p>L’appel <span class="wintitle"> DCS</span> contient un <span class="keyword"> ID Experience Cloud</span> non valide. </p> <p>Vérifiez la paire <code> d_mid=</code> clé-valeur dans la chaîne d’en-tête. Assurez-vous de transmettre le bon <span class="keyword"> ID Experience Cloud</span> et réessayez la requête. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>102 </p> </td> 
   <td colname="col2"> <p>ID aam non valide transmis dans l' <code><i>ID de requête</i></code> </p> </td> 
   <td colname="col3"> <p>L’appel <span class="wintitle"> DCS</span> contient un ID Audience Manager <span class="keyword"></span> non valide. </p> <p>Vérifiez la paire <code> _uuid=</code> clé-valeur dans la chaîne d’en-tête. Assurez-vous de transmettre l’ID <span class="keyword"> Audience Manager</span> correct et réessayez la requête. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>104 </p> </td> 
   <td colname="col2"> <p>Tous les identifiants de client ne sont pas valides </p> </td> 
   <td colname="col3"> <p>Tous les ID de client de votre appel ne sont pas valides. Vérifiez vos identifiants et réessayez. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>111 </p> </td> 
   <td colname="col2"> <p>Jeton IMS <span class="wintitle"></span> non valide reçu </p> </td> 
   <td colname="col3"> <p>Retour pour Audience Manager - Intégrations Adobe Target. L’erreur est générée lorsqu’un appel est effectué au serveur de collecte de données, contenant un jeton IMS non valide. Le jeton peut être mal formé, avoir expiré ou l’utilisateur ne peut pas être autorisé à accéder à la ressource requise. </p> </td>
  </tr>
 </tbody>
</table>

## Codes d’erreur d’exclusion {#opt-out-error-codes}

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
   <td colname="col2"> <p>Balise d’exclusion rencontrée pour l’ <code><i>ID d’ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un client a choisi de ne pas recevoir de publicité ciblée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookies bloqués </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsque le navigateur de l’utilisateur bloque les cookies tiers.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Relation de confiance rencontrée via <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>L’utilisateur a lancé un processus d’exclusion via NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p> Les demandes de ce pays sont bloquées par le partenaire </p> </td> 
   <td colname="col3"> <p>En fonction de l’adresse IP, le <span class="wintitle"> DCS</span> bloque les demandes des pays où le partenaire a délibérément limité le trafic. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Les demandes de ce pays ne sont pas autorisées </p> </td> 
   <td colname="col3"> <p>En fonction de l’adresse IP, le <span class="wintitle"> serveur de collecte de données</span> bloque les demandes des pays suivants : </p> <p> 
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

## Codes d'erreur de récupération de profil {#profile-retrieval-error-codes}

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
   <td colname="col2"> <p> Impossible de lire les caractéristiques du cache de profil pour l'ID : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsqu’un profil utilisateur ne peut pas être lu à partir de notre stockage interne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Impossible de lire les ID de périphérique du cache de profil pour l'ID de client : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsque l’ID <a href="../../../reference/ids-in-aam.md"> du</a> périphérique ne peut pas être récupéré pour une règle de fusion Lien de profil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Impossible de lire le client associé pour l'ID de périphérique : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsque l’ID <a href="../../../reference/ids-in-aam.md"> client (UUID)</a> associé à un ID de périphérique ne peut pas être récupéré pour une règle de dernière fusion authentifiée à partir de notre stockage interne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Impossible de lire la grappe de périphériques pour l'ID : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Les ID de périphérique liés d’une même grappe graphique de périphériques ne peuvent pas être renvoyés pour cet ID de périphérique. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Impossible d'effectuer la migration car la lecture du profil a échoué pour le périphérique principal </p> </td> 
   <td colname="col3"> <p>Si vous recevez cette erreur, nous rencontrons peut-être des problèmes d’évolutivité avec notre banque de données (<span class="wintitle"> PCS</span>). Contactez votre représentant Adobe si le problème persiste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Impossible d'effectuer la migration de <code><i>l'ID</i></code> vers l' <code><i>ID</i></code>, car la lecture du profil a échoué pour <code><i>l'ID</i></code> </p> </td>
   <td colname="col3"> <p>Si vous recevez cette erreur, nous rencontrons peut-être des problèmes d’évolutivité avec notre banque de données (<span class="wintitle"> PCS</span>). Contactez votre représentant Adobe si le problème persiste. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Codes d’avertissement d’intégration {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID de code </th> 
   <th colname="col2" class="entry"> Message </th> 
   <th colname="col3" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>ID de client <code><i>non valide</i></code> </p> </td> 
   <td colname="col3"> <p>L’ID de client n’est pas valide (valeurs manquantes pour la source de données, codes d’intégration manquants, format non valide pour les sources de données, ID de client bloqué, ID de client vide, tentative d’accès non autorisé à une source de données qui n’appartient pas au partenaire). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Nombre maximal d’identifiants de client dépassé. Le maximum autorisé est le <code><i>maximum autorisé</i></code>. Le <code><i>maximum trouvé</i></code>est.</p> </td> 
   <td colname="col3"> <p>Le nombre d’ID de client associés à une source de données inter-périphériques dépasse le nombre autorisé d’ID inter-périphériques par requête. Ces identifiants comprennent des ID inter-périphériques, mobiles ou de cookies. La limite est actuellement définie sur 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID de client non autorisé <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsque la source de données d’ID de client n’est pas détenue par l’ID d’organisation actuel. Si vous ne connaissez pas ou ne possédez pas votre ID d’organisation, consultez la section "Trouver votre ID d’organisation" dans <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organisations et liaison</a> de compte pour savoir comment le trouver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID client <code><i>bloqué</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsque l’identifiant du client a été identifié comme étant malveillant et a été mis sur liste noire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID <code><i>de source de données bloqué</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsque l’ID de source de données a été identifié comme étant malveillant et a été mis sur liste noire. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>ID <code><i>de périphérique déclaré bloqué</i></code> </p> </td> 
   <td colname="col3"> <p>L’ID de périphérique a été identifié comme étant malveillant et a été mis sur liste noire. Cela peut se produire lorsque nous recevons un nombre extrême de demandes <span class="wintitle"> DCS</span> contenant cet ID de périphérique en peu de temps. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Opération de profil bloquée pour <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Une action de lecture/écriture a été bloquée car un identifiant a été identifié comme étant malveillant et a été mis sur liste noire. Voir le code d’erreur 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>L’ID <code><i>de client</i></code> a été ignoré car il dépassait la limite des ID de client déclarés par requête. </p> </td> 
   <td colname="col3"> <p>Lié à l’erreur 301. Cette erreur indique l’ID de client ignoré car la limite a été dépassée. </p> <p>Par exemple, s’il existe 12 ID de client déclarés dans l’appel <span class="wintitle"> DCS</span> , deux d’entre eux sont ignorés. Afin de relayer ceux qui ont été ignorés, cette erreur apparaîtra deux fois dans la réponse (une fois pour chaque ID de client ignoré). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>L’ID de client a été ignoré car il dépassait la limite d’un espace de noms donné. L’ID d’espace de noms est <code><i>ID</i></code>, l’ID de client est <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Ce code d’erreur est renvoyé s’il existe plus de 3 ID de client déclarés pour le même espace de noms (<code> DPID</code>) sur un appel <span class="wintitle"> DCS</span> . </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>Dans cet exemple de demande <span class="wintitle"> DCS</span> , il existe 4 identifiants déclarés pour le même espace de noms (avec le code d’intégration 1). L’un des ID est ignoré et l’erreur 310 est renvoyée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La requête contient des paramètres non valides </p> </td> 
   <td colname="col3"> <p>Le <span class="wintitle"> serveur de collecte de données</span> renvoie ce code d’erreur lorsqu’au moins un paramètre d’URL n’est pas correctement codé. Dans ce cas, le serveur de collecte de données <span class="wintitle"></span> ignore l’intégralité de la requête. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy !&amp;d_adsrc=48123</code> </p> <p>Dans l'exemple de requête ci-dessus, la séquence % <code></code> est incorrectement codée. Par conséquent, le <span class="wintitle"> SDC</span> ne s'en souviendra pas. </p> <p>L’exemple codé correctement doit se présenter comme suit : </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy !&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La requête contient un ID de périphérique global non valide </p> </td> 
   <td colname="col3"> <p>Le <span class="wintitle">serveur de collecte de données</span> renvoie ce code d’erreur lorsque la requête contient un ID de périphérique global non valide. DCS ignore l’ID non valide et renvoie une erreur 312 avec les erreurs spécifiques de l’ID non valide. Consultez la section Sources <a href="../../../features/global-data-sources.md" format="dita" scope="local">de données</a> globales et <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Index des identifiants dans Audience Manager</a> pour obtenir des informations détaillées sur les formats d’ID publicitaires de périphérique et les sources de données globales correspondantes.</p>
   <p>Exemple d’appel incorrect : <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explication : Un <span class="keyword">IDFA (DPID 20915)</span> doit être un ID en majuscules. L’ID fourni dans la requête est en minuscules.</p>
   </td>
  </tr>

</tbody>
</table>

## Exemples de messages de code d’erreur {#sample-error-codes}

Le [!UICONTROL DCS] renvoie les codes d’erreur et les messages dans un [!DNL JSON] objet ou dans un en-tête X dans la chaîne de réponse HTTP.

### Exemple de code d’erreur DCS et de message

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

Les codes d’erreur capturés par l’en-tête X s’affichent dans la chaîne d’URL comme ceci `X-Error: 101,102`.

[Conditions de race et gestion des erreurs](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)