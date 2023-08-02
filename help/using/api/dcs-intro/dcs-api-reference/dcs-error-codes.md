---
description: Codes d’erreur et messages générés par les serveurs de collecte de données (DCS) répertoriés dans l’ordre numérique par identifiant de code.
title: Codes, messages et exemples d’erreur des serveurs de collecte de données
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 5044a38c751abace922008f00b9ff463ea9c7e57
workflow-type: tm+mt
source-wordcount: '1520'
ht-degree: 4%

---

# Codes, messages et exemples d’erreur des serveurs de collecte de données {#dcs-error-codes-messages-and-examples}

Codes d’erreur et messages générés par la variable [!UICONTROL Data Collection Servers] ([!DNL DCS]) répertoriés dans l’ordre numérique par identifiant de code.

Dans les tableaux ci-dessous, *italique* représente un espace réservé de variable.

## Codes d’erreur système {#system-error-codes}

| Code d’erreur | Message d’erreur | Description |
|---|---|---|
| 0 | Erreur non spécifiée | Il s’agit d’une erreur fourre-tout qui gère les événements qui ne sont pas couverts par les autres gestionnaires d’erreurs. La résolution de cette erreur est difficile. Elle peut être causée par une variété d’actions ou d’événements inconnus. Si vous recevez cette erreur, essayez votre [!DNL DCS] redemandez. Contactez votre [!DNL Adobe] si le problème persiste. |
| 1 | Impossible de trouver la configuration pour le nom d’hôte : `hostname` | Le nom d’hôte envoyé dans la demande n’a pas été configuré par notre équipe de configuration de partenaire. Contactez votre [!DNL Adobe] si ce message d’erreur s’affiche. |
| 2 | Non valide `d_orgid` valeur (impossible de trouver une configuration pour cet ID d’organisation) : `ID` | L’ID d’organisation est incorrect. Vérifiez votre ID et relancez la requête. Si vous ne connaissez pas votre ID d’organisation ou le possédez, consultez la section &quot;Page d’administration&quot;. [Liaison d’organisations et de comptes](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html) pour plus d’informations sur la manière de le trouver. |
| 10 | Impossible d’évaluer les caractéristiques | Les caractéristiques de la requête ont été partiellement évaluées ou n’ont pas du tout été évaluées. Contactez votre [!DNL Adobe] si le problème persiste. |

## Codes d’erreur d’intégration {#integration-error-codes}

| Code d’erreur | Message d’erreur | Description |
|---|---|---|
| 100 | Impossible de récupérer le nom d’hôte de la requête | Un [!DNL API] L’appel n’a pas envoyé l’hôte [!DNL HTTP] dans la requête. Ajoutez l’en-tête hôte à l’appel et réessayez. La plupart des navigateurs et [!DNL API] les clients effectuent cette opération automatiquement. |
| 101 | Non valide [!DNL Experience Cloud] id transmis `ID` | La variable [!DNL DCS] contient un appel non valide [!DNL Experience Cloud] ID. Vérifiez les `d_mid=` paire clé-valeur dans la chaîne d’en-tête. Assurez-vous que vous transmettez le bon [!DNL Experience Cloud] Identifiant et relancez la requête. |
| 102 | Non valide [!DNL AAM ID] requête transmise `ID` | La variable [!DNL DCS] contient un appel non valide [!DNL Audience Manager] ID. Vérifiez les `d_uuid=` paire clé-valeur dans la chaîne d’en-tête. Assurez-vous que vous transmettez le bon [!DNL Audience Manager] Identifiant et relancez la requête. |
| 104 | Tous les ID de client ne sont pas valides | Tous les ID de client de votre appel ne sont pas valides. Vérifiez vos identifiants et réessayez. |
| 109 | Référent `HTTP referer` n’est pas autorisé pour le partenaire `Partner ID` | La variable `HTTP referer` L’en-tête de l’appel n’est pas autorisé pour l’ID de partenaire de l’appel. Vérifiez que la variable `HTTP referer` L’en-tête est correct. |
| 111 | Non valide `IMS` token reçu | Renvoyée pour [!DNL Audience Manager] - [!DNL Adobe Target] intégrations. L’erreur est générée lorsqu’un appel est effectué à la fonction [!DNL DCS], contenant un caractère non valide [!DNL IMS] jeton. Le jeton peut être mal formé, arrivé à expiration ou l’utilisateur peut ne pas être autorisé à accéder à la ressource requise. |

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
   <td colname="col2"> <p>Balise d’exclusion rencontrée pour l’ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Un client s’est désinscrit de la réception de publicités basées sur les intérêts. </p> </td> 
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
   <td colname="col2"> <p>Les demandes en provenance de ce pays sont bloquées par le partenaire </p> </td> 
   <td colname="col3"> <p>Selon l’adresse IP, la variable <span class="wintitle"> DCS</span> bloque les demandes provenant de pays où le partenaire a délibérément limité le trafic. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Les demandes provenant de ce pays ne sont pas autorisées </p> </td> 
   <td colname="col3"> <p>Selon l’adresse IP, la variable <span class="wintitle"> DCS</span> bloque les demandes des pays suivants : </p> <p> 
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

## Codes d’erreur de récupération de profil {#profile-retrieval-error-codes}

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
   <td colname="col3"> <p>Renvoyée lorsqu’un profil utilisateur ne peut pas être lu à partir de notre stockage interne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Impossible de lire les identifiants d’appareil du cache de profil pour l’ID de client : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>renvoyée lorsque la variable <a href="../../../reference/ids-in-aam.md"> identifiant de l’appareil</a> ne peut pas être récupéré pour une règle de fusion de lien de profil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Impossible de lire le client associé pour l’ID d’appareil : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>renvoyée lorsque la variable <a href="../../../reference/ids-in-aam.md"> ID de client (UUID)</a> Les associés à un ID d’appareil ne peuvent pas être récupérés pour une règle de dernière fusion authentifiée de notre stockage interne. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Impossible de lire la grappe d’appareils pour l’ID : <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Les identifiants d’appareil liés d’une même grappe de graphiques d’appareil ne peuvent pas être renvoyés pour cet identifiant d’appareil. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Impossible d’effectuer la migration, car la lecture du profil a échoué pour le périphérique Principal. </p> </td> 
   <td colname="col3"> <p>Si cette erreur s’affiche, nous pouvons rencontrer des problèmes d’évolutivité avec notre banque de données (<span class="wintitle"> PCS</span>). Contactez votre représentant d’Adobe si le problème persiste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Impossible d’effectuer la migration depuis <code><i>ID</i></code> to <code><i>ID</i></code>, car la lecture du profil a échoué pour <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Si cette erreur s’affiche, nous pouvons rencontrer des problèmes d’évolutivité avec notre banque de données (<span class="wintitle"> PCS</span>). Contactez votre représentant d’Adobe si le problème persiste. </p> </td> 
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
   <td colname="col2"> <p>Nombre maximal d’identifiants de client dépassé. Maximum autorisé <code><i>maximum allowed</i></code>. Trouvé est <code><i>maximum found</i></code>.</p> </td> 
   <td colname="col3"> <p>Le nombre d’ID de client associés à une source de données multi-appareils dépasse le nombre autorisé d’ID multi-appareils par demande. Ces identifiants comprennent des identifiants multi-appareils, mobiles ou de cookies. La limite est actuellement définie sur 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID de client non autorisé <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsque la source de données de l’ID de client n’est pas détenue par l’ID d’organisation actuel. Si vous ne connaissez pas ou ne possédez pas votre ID d’organisation, reportez-vous à la section "Trouver votre ID d’organisation" de la section <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organisations et liaison de comptes</a> pour plus d’informations sur la manière de le trouver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID de client bloqué <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsque l’ID de client a été identifié comme étant malveillant et a été ajouté à une liste bloquée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>Identifiant de source de données bloqué <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyée lorsque l’identifiant de source de données a été identifié comme malveillant et a été ajouté à une liste bloquée </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Identifiant de périphérique déclaré bloqué <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>L’identifiant de l’appareil a été identifié comme étant malveillant et a été ajouté à une liste bloquée. Cela peut se produire lorsque nous recevons un nombre extrême de <span class="wintitle"> DCS</span> demandes contenant cet identifiant d’appareil dans un délai court. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Opération de profil bloqué pour <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Une action de lecture/écriture a été bloquée car un identifiant a été identifié comme étant malveillant et a été ajouté à une liste bloquée Voir le code d’erreur 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>ID de client <code><i>ID</i></code> a été ignoré car il dépassait la limite des ID de client déclarés par requête. </p> </td> 
   <td colname="col3"> <p>Lié à l’erreur 301. Cette erreur indique quel ID de client a été ignoré car la limite a été dépassée. </p> <p>Par exemple, s’il existe 12 ID de client déclarés sur la variable <span class="wintitle"> DCS</span> appelez, deux d’entre eux seront ignorés. Pour indiquer ceux qui ont été ignorés, cette erreur apparaîtra deux fois dans la réponse (une fois pour chacun des ID de client ignoré ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>L’ID de client a été ignoré car il dépassait la limite d’un espace de noms donné. L’identifiant d’espace de noms est <code><i>ID</i></code>, l’ID de client est <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Ce code d’erreur est renvoyé s’il existe plus de 3 ID de client déclarés pour le même espace de noms (<code> DPID</code>) sur un <span class="wintitle"> DCS</span> appelez . </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one&amp;d_cid_ic=one </code> </p> <p>Dans cet exemple <span class="wintitle"> DCS</span> 4 id sont déclarés pour le même espace de noms (avec le code d’intégration 1). L’un des identifiants est ignoré et l’erreur 310 est renvoyée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La requête contient des paramètres non valides </p> </td> 
   <td colname="col3"> <p>La variable <span class="wintitle"> DCS</span> renvoie ce code d’erreur lorsqu’au moins un paramètre d’URL n’est pas correctement codé. Dans ce cas, la variable <span class="wintitle"> DCS</span> ignore l’intégralité de la requête. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>Dans l’exemple de requête ci-dessus, la fonction <code> %</code> La séquence est incorrectement codée. Par conséquent, la <span class="wintitle"> DCS</span> ne s'en souciera pas. </p> <p>L’exemple correctement codé doit ressembler à ceci : </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La requête contient un identifiant de périphérique global non valide </p> </td> 
   <td colname="col3"> <p>La variable <span class="wintitle">DCS</span> renvoie ce code d’erreur lorsque la requête contient un identifiant de périphérique global non valide. Le serveur de collecte de données ignore l’ID non valide et renvoie une erreur 312 avec les erreurs spécifiques de l’ID non valide. Voir <a href="../../../features/global-data-sources.md" format="dita" scope="local">Sources de données globales</a> et <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Index des identifiants en Audience Manager</a> pour obtenir des informations détaillées sur les formats d’ID de publicité d’appareil corrects et les sources de données globales correspondantes.</p>
   <p>Exemple d'appel incorrect : <code>"http://partner.demdex.net/event?d_rtbd=json&amp;d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explication : un <span class="keyword">IDFA (DPID 20915)</span> doit être un identifiant en majuscules. L’identifiant fourni dans la requête est en minuscules.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>ID de CMP non présent dans GCL</p> </td> 
   <td colname="col3"> <p>When <code>gdpr=1</code> et la chaîne IAB TC est générée par un ID de CMP qui n’est pas présent dans la version mise en cache de la liste globale de CMP en Audience Manager au moment de l’évaluation, le module externe d’Audience Manager pour IAB TCF ignore la chaîne IAB TC et traite la demande comme d’habitude. IAB TCF v2.2 ${GDPR} La macro est définie sur 0 et le ${GDPR_CONSENT_XXX} macro est vide.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>L’ID de CMP est marqué comme supprimé dans GCL</p> </td> 
   <td colname="col3"> <p>When <code>gdpr=1</code> et la chaîne IAB TC est générée par une CMP qui est marquée comme supprimée dans notre version mise en cache de la liste de CMP globale, le module externe d’Audience Manager pour IAB TCF ignore la chaîne TC et traite la demande comme d’habitude, si l’heure d’évaluation est postérieure à l’heure de suppression de la liste de CMP globale. IAB TCF v2.2 ${GDPR} La macro est définie sur 0 et le ${GDPR_CONSENT_XXX} macro est vide.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>La chaîne de consentement indique qu’il n’y a pas de consentement</p> </td> 
   <td colname="col3"> <p>Lorsqu’aucun consentement n’est fourni, le module d’Audience Manager pour le TCF de l’IAB exclut l’utilisateur de la collecte des données supplémentaire ou supprime complètement l’appel s’il n’y a aucun contexte de partenaire détecté.</p>
   </td>
  </tr>

</tbody>
</table>

## Exemples de messages de code d’erreur {#sample-error-codes}

La variable [!DNL DCS] renvoie les codes d’erreur et les messages dans un [!DNL JSON] ou dans un en-tête X dans la chaîne de réponse HTTP.

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

Les codes d’erreur capturés par l’en-tête X apparaissent dans la chaîne d’URL comme ceci, `X-Error: 101,102`.

[Conditions de race et gestion des erreurs](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
