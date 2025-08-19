---
description: Codes d’erreur et messages générés par les serveurs de collecte de données (DCS) répertoriés dans l’ordre numérique par identifiant de code.
title: Codes d’erreur DCS, messages et exemples
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 5044a38c751abace922008f00b9ff463ea9c7e57
workflow-type: tm+mt
source-wordcount: '1517'
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
| 2 | Valeur de `d_orgid` non valide (configuration introuvable pour cet ID d’organisation) : `ID` | L’ID d’organisation est incorrect. Vérifiez votre ID et effectuez une nouvelle requête. Si vous ne connaissez pas votre identifiant d’organisation ou si vous ne l’avez pas, consultez la section « Page d’administration » [Liaison d’organisations et de comptes](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=fr) pour plus d’informations sur la manière de le trouver. |
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
   <td colname="col3"> <p>L’ID de client n’est pas valide (valeurs manquantes pour la source de données, codes d’intégration manquants, format non valide pour les sources de données, ID de client bloqué, ID de client vide, tentative d’accès non autorisée à une source de données qui n’appartient pas au partenaire). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Nombre maximal d’ID de client dépassé. Le maximum autorisé est de <code><i>maximum allowed</i></code>. <code><i>maximum found</i></code> trouvé.</p> </td> 
   <td colname="col3"> <p>Le nombre d’ID de client associés à une source de données entre appareils dépasse le nombre autorisé d’ID entre appareils par requête. Ces ID incluent des ID sur l’ensemble des appareils, des appareils mobiles ou des cookies. La limite est actuellement définie sur 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>ID de client non autorisé <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyé lorsque la source de données de l’ID client n’appartient pas à l’ID d’organisation actuel. Si vous ne connaissez pas votre identifiant d’organisation ou si vous ne l’avez pas, reportez-vous à la section « Rechercher votre identifiant d’organisation » de la section Liaison d’organisations et de comptes <a href="https://experiencecloud.adobe.com/resources/help/fr_FR/mcloud/organizations.html" format="https" scope="external"></a> pour savoir comment le trouver. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>ID de client bloqué <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyé lorsque l’ID de client a été identifié comme malveillant et a été ajouté à une liste bloquée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID de source de données bloqué <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Renvoyé lorsque l’ID de la source de données a été identifié comme malveillant et a été ajouté à une liste bloquée </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>ID d’appareil déclaré bloqué <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>L’ID d’appareil a été identifié comme malveillant et a été ajouté à une liste bloquée. Cela peut se produire lorsque nous recevons un nombre extrême de requêtes <span class="wintitle"> DCS</span> contenant cet ID d’appareil dans un délai court. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Opération de profil bloquée pour <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Une action de lecture/écriture a été bloquée car un ID a été identifié comme malveillant et a été ajouté à une liste bloquée. Voir code d'erreur 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>L’ID de client <code><i>ID</i></code> a été ignoré, car il dépassait la limite des ID de client déclarés par demande </p> </td> 
   <td colname="col3"> <p>En rapport avec l’erreur 301. Cette erreur indique quel ID de client a été ignoré car la limite a été dépassée. </p> <p>Par exemple, si 12 ID de client sont déclarés lors de l’appel <span class="wintitle"> DCS</span>, deux d’entre eux seront ignorés. Afin de relayer ceux qui ont été ignorés, cette erreur apparaîtra deux fois dans la réponse (une fois pour chacun des ID de client ignorés ). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>L’ID de client a été ignoré car il dépassait la limite pour un espace de noms donné. L’ID de l’espace de noms est <code><i>ID</i></code>, l’ID du client est <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Ce code d’erreur est renvoyé si plus de 3 ID client ont été déclarés pour le même espace de noms (<code> DPID</code>) lors d’un <span class="wintitle"> appel de DCS</span>. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one </code> </p> <p>Dans cet exemple <span class="wintitle"> requête DCS</span>, il existe 4 identifiants déclarés pour le même espace de noms (avec le code d’intégration un). L'un des ID est ignoré et l'erreur 310 est renvoyée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>La requête contient des paramètres non valides </p> </td> 
   <td colname="col3"> <p>Le <span class="wintitle"> DCS</span> renvoie ce code d’erreur lorsqu’au moins un paramètre d’URL n’est pas correctement encodé. Dans ce cas, le <span class="wintitle"> DCS</span> ignore l’ensemble de la requête. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>Dans l’exemple de requête ci-dessus, la séquence <code> %</code> est incorrectement codée. Par conséquent, le <span class="wintitle"> DCS</span> ne le prendra pas en compte. </p> <p>L’exemple correctement encodé doit se présenter comme suit : </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>La requête contient un ID d’appareil global non valide </p> </td> 
   <td colname="col3"> <p>Le <span class="wintitle">DCS</span> renvoie ce code d’erreur lorsque la requête contient un identifiant global d’appareil non valide. DCS ignore l’ID non valide et renvoie une erreur 312 avec les erreurs spécifiques de l’ID non valide. Consultez les sections <a href="../../../features/global-data-sources.md" format="dita" scope="local">Sources de données globales</a> et <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Index des identifiants dans Audience Manager</a> pour obtenir des informations détaillées sur les formats d’identifiant publicitaire d’appareil corrects et les sources de données globales correspondantes.</p>
   <p>Exemple d’appel incorrect : <code>"http://partner.demdex.net/event?d_rtbd=json&d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Explication : un <span class="keyword">IDFA (20915 DPID)</span> doit être un identifiant en majuscules. L’identifiant fourni dans la requête est en minuscules.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>L’ID de CMP n’est pas présent dans le GCL</p> </td> 
   <td colname="col3"> <p>Lorsque la <code>gdpr=1</code> et la chaîne de caractères IAB TC sont générées par un ID de CMP qui n’est pas présent dans la version mise en cache d’Audience Manager de la liste globale de CMP au moment de l’évaluation, le plug-in Audience Manager pour IAB TCF ignore la chaîne de caractères IAB TC et traite la requête comme d’habitude. La macro ${GDPR} de IAB TCF v2.2 est définie sur 0 et la macro ${GDPR_CONSENT_XXX} est vide.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>L’ID de CMP est marqué comme supprimé dans GCL.</p> </td> 
   <td colname="col3"> <p>Lorsque <code>gdpr=1</code> et la chaîne IAB TC sont générées par une CMP marquée comme supprimée dans notre version mise en cache de la liste globale de CMP, le plug-in Audience Manager pour IAB TCF ignore la chaîne TC et traite la demande comme d’habitude, si le temps d’évaluation est passé le temps de suppression de la liste globale de CMP. La macro ${GDPR} de IAB TCF v2.2 est définie sur 0 et la macro ${GDPR_CONSENT_XXX} est vide.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>Chaîne de consentement indiquant aucun consentement</p> </td> 
   <td colname="col3"> <p>Lorsqu’aucun consentement n’est fourni, le module externe Audience Manager pour IAB TCF désinscrit l’utilisateur de la collecte de données supplémentaire ou interrompt complètement l’appel si aucun contexte de partenaire n’est détecté.</p>
   </td>
  </tr>

</tbody>
</table>

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
