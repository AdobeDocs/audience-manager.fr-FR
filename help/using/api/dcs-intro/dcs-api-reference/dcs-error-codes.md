---
description: Codes d’erreur et messages générés par les serveurs de collecte de données (DCS) répertoriés par ID de code dans l’ordre numérique.
seo-description: Codes d’erreur et messages générés par les serveurs de collecte de données (DCS) répertoriés par ID de code dans l’ordre numérique.
seo-title: Codes, messages et exemples d’erreur des serveurs de collecte de données
solution: Audience Manager
title: Codes, messages et exemples d’erreur des serveurs de collecte de données
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
translation-type: tm+mt
source-git-commit: ff245c2cca417e9b1fd51460ddbadd25d5696006
workflow-type: tm+mt
source-wordcount: '1509'
ht-degree: 3%

---


# Codes, messages et exemples d’erreur des serveurs de collecte de données {#dcs-error-codes-messages-and-examples}

Codes d’erreur et messages générés par le [!UICONTROL Data Collection Servers] ([!DNL DCS]) répertorié dans l’ordre numérique par ID de code.

In the tables below, *italics* represents a variable placeholder.

## Codes d&#39;erreur système {#system-error-codes}

|Code d&#39;erreur|Message d&#39;erreur|Description|
|—|—|—|
|0|Erreur non spécifiée|Il s&#39;agit d&#39;une erreur fourre-tout qui traite les événements qui ne sont pas couverts par les autres gestionnaires d&#39;erreurs. La résolution de cette erreur est difficile. Elle peut être causée par une variété d&#39;actions ou de événements inconnus. Si vous recevez cette erreur, réessayez votre [!DNL DCS] demande. Contactez votre [!DNL Adobe] représentant si le problème persiste.|
|1|Impossible de trouver la configuration du nom d&#39;hôte : `hostname`|Le nom d&#39;hôte envoyé dans la demande n&#39;a pas été configuré par notre équipe de mise en service partenaire. Contactez votre [!DNL Adobe] représentant si ce message d’erreur s’affiche.|
|2|Valeur non `d_orgid` valide (impossible de trouver une configuration pour cet ID d&#39;organisation) : `ID`|L&#39;ID d&#39;organisation est incorrect. Vérifiez votre ID et réessayez. Si vous ne connaissez pas ou ne possédez pas votre ID d&#39;organisation, consultez la section &quot;Page d&#39;administration&quot; [Organisations et liens](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html) de compte pour en savoir plus sur la manière de le trouver.|

## Codes d’erreur d’intégration {#integration-error-codes}

|Code d&#39;erreur|Message d&#39;erreur|Description|
|—|—|—|
|100|Impossible de récupérer le nom d&#39;hôte pour la requête|Un [!DNL API] appel n&#39;a pas envoyé l&#39;en-tête d&#39;hôte [!DNL HTTP] dans la requête. Ajoutez l’en-tête hôte sur l’appel, puis réessayez. La plupart des navigateurs et [!DNL API] des clients effectuent cette opération automatiquement. |
|101|ID [!DNL Experience Cloud] non valide transmis `ID`|L&#39; [!DNL DCS] appel contient un [!DNL Experience Cloud] ID non valide. Vérifiez la paire `d_mid=` clé-valeur dans la chaîne d’en-tête. Assurez-vous de transmettre l’ [!DNL Experience Cloud] identifiant correct et réessayez la demande. |
|102|Non valide [!DNL AAM ID] transmis dans la requête `ID`|L&#39; [!DNL DCS] appel contient un [!DNL Audience Manager] ID non valide. Vérifiez la paire `d_uuid=` clé-valeur dans la chaîne d’en-tête. Assurez-vous de transmettre l’ [!DNL Audience Manager] identifiant correct et réessayez la demande. |
|104|Tous les ID de client ne sont pas valides | Tous les ID de client de votre appel ne sont pas valides. Vérifiez vos identifiants et réessayez.|
|109|Le référent `HTTP referer` n&#39;est pas autorisé pour le partenaire `Partner ID`|L&#39; `HTTP referer` en-tête de l&#39;appel n&#39;est pas autorisé pour l&#39;ID de partenaire de l&#39;appel. Vérifiez que l’ `HTTP referer` en-tête est correct.|
|111|Jeton `IMS` non valide reçu|Renvoyé pour [!DNL Audience Manager] - [!DNL Adobe Target] intégrations. L&#39;erreur est générée lorsqu&#39;un appel est lancé vers le [!DNL DCS], contenant un [!DNL IMS] jeton non valide. Le jeton peut être mal formé, expiré ou l&#39;utilisateur peut ne pas être autorisé à accéder à la ressource requise.|

## Codes d&#39;erreur d&#39;exclusion {#opt-out-error-codes}

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
   <td colname="col2"> <p>Balise opt-out pour l’identifiant rencontrée <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un client a choisi de ne pas recevoir de publicité basée sur les intérêts. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Cookies bloqués </p> </td> 
   <td colname="col3"> <p>Retourné lorsque le navigateur de l’utilisateur bloque les cookies tiers.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Relation de confiance rencontrée via <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>L’utilisateur a initié un processus d’exclusion via NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Les demandes de ce pays sont bloquées par le partenaire </p> </td> 
   <td colname="col3"> <p>En fonction de l’adresse IP, le <span class="wintitle"> DCS</span> bloque les demandes des pays où le partenaire a délibérément limité le trafic. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Les demandes de ce pays ne sont pas autorisées </p> </td> 
   <td colname="col3"> <p>En fonction de l’adresse IP, le serveur de collecte de données <span class="wintitle"></span> bloque les demandes des pays suivants : </p> <p> 
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

## Codes d&#39;erreur de récupération de Profil {#profile-retrieval-error-codes}

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
   <td colname="col2"> <p> Impossible de lire les caractéristiques du cache de profil pour l'identifiant : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retourné lorsqu’un profil utilisateur ne peut pas être lu à partir de notre enregistrement interne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Impossible de lire les ID de périphérique du cache de profil pour l'ID de client : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Retourné lorsque l'ID <a href="../../../reference/ids-in-aam.md"> de</a> périphérique ne peut pas être récupéré pour une règle de fusion Lien de Profil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Impossible de lire le client associé pour l'ID de périphérique : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsque l’ID <a href="../../../reference/ids-in-aam.md"> client (UUID)</a> associé à un ID de périphérique ne peut pas être récupéré pour une règle de dernière fusion authentifiée à partir de notre enregistrement interne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Impossible de lire la grappe de périphériques pour l'ID : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Les ID de périphérique liés provenant d'une même grappe graphique de périphériques ne peuvent pas être renvoyés pour cet ID de périphérique. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Impossible d'effectuer la migration car la lecture du profil a échoué pour le périphérique principal </p> </td> 
   <td colname="col3"> <p>Si vous recevez cette erreur, nous rencontrons peut-être des problèmes d’évolutivité avec notre banque de données (<span class="wintitle"> PCS</span>). Contactez votre représentant Adobe si le problème persiste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Impossible d'effectuer la migration de <code><i>ID</i></code> vers <code><i>ID</i></code>, car la lecture du profil a échoué pour <code><i>ID</i></code> </p> </td>
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
   <td colname="col2"> <p>ID de client non valide <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>L’ID de client n’est pas valide (valeurs manquantes pour la source de données, codes d’intégration manquants, format non valide pour les sources de données, ID de client bloqué, ID de client vide, tentative d’accès non autorisé à une source de données qui n’appartient pas au partenaire). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Nombre maximal d'identifiants de client dépassé. Le maximum autorisé est <code><i>maximum allowed</i></code>. On l'a trouvé <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>Le nombre d’ID de client associés à une source de données sur plusieurs périphériques dépasse le nombre autorisé d’ID sur plusieurs périphériques par requête. Ces identifiants comprennent des identifiants interpériphériques, mobiles ou de cookies. La limite est actuellement fixée à 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID client non autorisé <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsque la source de données d’ID de client n’est pas détenue par l’ID d’organisation actuel. Si vous ne connaissez pas ou ne possédez pas votre ID d’organisation, consultez la section "Rechercher votre ID d’organisation" dans <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organisations et liaison de compte</a> pour plus d’informations sur la manière de le trouver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID client bloqué <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyé lorsque l’identifiant du client a été identifié comme étant malveillant et a été ajouté à une liste de refus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID de source de données bloqué <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyé lorsque l’identifiant de source de données a été identifié comme étant malveillant et a été ajouté à une liste de refus. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>ID de périphérique déclaré bloqué <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>L'ID de périphérique a été identifié comme étant malveillant et a été ajouté à une liste de refus. Cela peut se produire lorsque nous recevons un nombre extrême de demandes <span class="wintitle"> DCS</span> contenant cet ID de périphérique en peu de temps. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Opération de profil bloqué pour <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Une action de lecture/écriture a été bloquée car un identifiant a été identifié comme étant malveillant et a été ajouté à une liste de refus Voir code d'erreur 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>L’ID de client <code><i>ID</i></code> a été ignoré car il dépassait la limite des identifiants de client déclarés par demande. </p> </td> 
   <td colname="col3"> <p>Lié à l’erreur 301. Cette erreur indique l’ID de client qui a été ignoré car la limite a été dépassée. </p> <p>Par exemple, s’il y a 12 ID de client déclarés lors de l’appel <span class="wintitle"> DCS</span> , deux d’entre eux seront ignorés. Afin de relayer ceux qui ont été ignorés, cette erreur apparaîtra deux fois dans la réponse (une fois pour chacun des ID de client ignorés). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>L’ID de client a été ignoré car il dépassait la limite d’un espace de nommage donné. ID d’Espace de nommage <code><i>ID</i></code>, ID de client <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Ce code d’erreur est renvoyé s’il existe plus de 3 ID de client déclarés pour le même espace de nommage (<code> DPID</code>) lors d’un appel <span class="wintitle"> DCS</span> . </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>Dans cet exemple de demande <span class="wintitle"> DCS</span> , 4 identifiants sont déclarés pour le même espace de nommage (avec le code d’intégration 1). L’un des ID est ignoré et l’erreur 310 est renvoyée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La requête contient des paramètres non valides </p> </td> 
   <td colname="col3"> <p>Le <span class="wintitle"> serveur de collecte de données</span> renvoie ce code d’erreur lorsqu’au moins un paramètre d’URL n’est pas correctement codé. Dans ce cas, le serveur <span class="wintitle"> de collecte de données</span> ignore la totalité de la demande. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>Dans l’exemple de requête ci-dessus, la <code> %</code> séquence est incorrectement codée. Par conséquent, le <span class="wintitle"> DCS</span> ne s'en souviendra pas. </p> <p>L’exemple correctement codé doit se présenter comme suit : </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La demande contient un ID de périphérique global non valide </p> </td> 
   <td colname="col3"> <p>Le <span class="wintitle">serveur de collecte de données</span> renvoie ce code d’erreur lorsque la requête contient un ID de périphérique global non valide. DCS ignore l’ID non valide et renvoie une erreur 312 avec les erreurs spécifiques de l’ID non valide. Consultez la section Sources <a href="../../../features/global-data-sources.md" format="dita" scope="local">de données</a> globales et <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Index des identifiants dans l’Audience Manager</a> pour obtenir des informations détaillées sur les formats d’ID publicitaires des périphériques et les sources de données globales correspondantes.</p>
   <p>Exemple d’appel incorrect : <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explication : Un <span class="keyword">IDFA (DPID 20915)</span> doit être un ID en majuscules. L’ID fourni dans la demande est en minuscules.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>ID CMP non présent dans GCL</p> </td> 
   <td colname="col3"> <p>Lorsque <code>gdpr=1</code> et la chaîne TC IAB est générée par un ID CMP qui n’est pas présent dans la version mise en cache de l’Audience Manager de la Liste CMP globale au moment de l’évaluation, le module externe d’Audience Manager pour le TCF IAB ignore la chaîne TC IAB et traite la demande comme d’habitude. La macro IAB TCF v2.0 ${GDPR} est définie sur 0 et la macro ${GDPR_CONSENT_XXX} est vide.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>ID CMP marqué comme supprimé dans GCL</p> </td> 
   <td colname="col3"> <p>Lorsque <code>gdpr=1</code> et la chaîne TC IAB est générée par un CMP marqué comme supprimé dans notre version mise en cache de la Liste CMP globale, le module externe d’Audience Manager pour le TCF IAB ignore la chaîne TC et traite la demande comme d’habitude, si l’heure d’évaluation est postérieure à l’heure de suppression de la Liste CMP globale. La macro IAB TCF v2.0 ${GDPR} est définie sur 0 et la macro ${GDPR_CONSENT_XXX} est vide.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>La chaîne de consentement indique qu’il n’y a pas consentement</p> </td> 
   <td colname="col3"> <p>Si aucun consentement n’est fourni, le module d’Audience Manager pour IAB TCF désactive l’utilisateur de la collecte de données ultérieure ou supprime complètement l’appel s’il n’y a aucun contexte de partenaire détecté.</p>
   </td>
  </tr>

</tbody>
</table>

## Exemples de messages de code d’erreur {#sample-error-codes}

Le [!DNL DCS] renvoie des codes d’erreur et des messages dans un [!DNL JSON] objet ou dans un en-tête X dans la chaîne de réponse HTTP.

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

Les codes d’erreur capturés par l’en-tête X s’affichent dans la chaîne URL comme ceci `X-Error: 101,102`.

[Conditions de race et gestion des erreurs](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)