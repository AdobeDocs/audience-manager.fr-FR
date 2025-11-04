---
description: Répertorie et décrit la syntaxe et les attributs pris en charge (ou les paires clé-valeur) que vous pouvez transmettre aux serveurs de collecte de données (DCS). Ces informations peuvent vous aider à formater vos requêtes DCS et à comprendre les paramètres renvoyés par ce système.
seo-description: Lists and describes the syntax and supported attributes (or key-value pairs) you can pass in to the Data Collection Servers (DCS). This information can help you format your DCS requests and understand the parameters returned by this system.
seo-title: Supported Attributes for DCS API Calls
solution: Audience Manager
title: Attributs pris en charge pour les appels API DCS
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
feature: DCS
exl-id: 1bdd7dcd-9411-4b0a-a236-059eb5faf00d
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 2%

---

# Attributs pris en charge pour les appels de [!DNL DCS] [!DNL API] {#supported-attributes-for-dcs-api-calls}

Répertorie et décrit la syntaxe et les attributs pris en charge (ou les paires clé-valeur) que vous pouvez transmettre au [!UICONTROL Data Collection Servers] ([!DNL DCS]). Ces informations peuvent vous aider à formater vos requêtes [!DNL DCS] et à comprendre les paramètres renvoyés par ce système.

## Préfixes d’attribut {#attribute-prefixes}

Le [!DNL DCS] repose sur des préfixes spécifiques ajoutés aux clés dans les paires clé-valeur pour classer le type de données que vous transmettez.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Préfixe Clé </th> 
   <th colname="col2" class="entry"> Réservé Pour </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>Attributs définis par le client. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> les attributs Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>Données d’en-tête HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Attributs privés définis par le client. </p> <p> Le serveur de collecte de données accepte vos propres données privées lorsque la clé comporte un préfixe <code> p_</code>. Les données privées sont utilisées pour l'évaluation des caractéristiques, mais elles ne seront pas consignées ni stockées dans notre système. Supposons, par exemple, que vous ayez une caractéristique définie comme <code> customers = p_age&lt;25</code> et que vous transmettiez des <code> p_age=23</code> dans un appel d’événement. Compte tenu de ces conditions, l’utilisateur qui répond aux critères de qualification basés sur l’âge est qualifié pour la caractéristique, mais la paire clé-valeur est abandonnée après <span class="keyword"> réception de la demande par Audience Manager</span> et n’est pas consignée. </p> </td>
  </tr> 
 </tbody> 
</table>

## [!DNL d_] Attributs {#d-attributes}

Tous ces éléments sont facultatifs, à moins que vous ne souhaitiez une réponse du [!DNL DCS]. Si vous souhaitez que le [!DNL DCS] renvoie une réponse, `d_rtbd=json` est obligatoire.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribut </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_caller</code> </p> </td> 
   <td colname="col2"> <p>Utilisé pour identifier l’appelant qui effectue l’appel à l’API <span class="wintitle"> DCS</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Spécifie une fonction JavaScript que vous souhaitez exécuter à l’aide de la réponse <span class="wintitle"> DCS</span> en tant que paramètre de fonction de la fonction de rappel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Contient une ou plusieurs paires d’ID de fournisseur de données (<code> DPID</code>) et d’ID d’utilisateur de fournisseur de données (<code> DPUUID</code>) attribuées par <span class="keyword"> Audience Manager</span>. Si vous utilisez plusieurs paires de <code> DPID</code> et de <code> DPUUID</code>, séparez chaque paire par le <code> %01</code> de caractères non imprimables. Par exemple : <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> remplace <code> d_dpid</code> et <code> d_dpuuid</code>, qui sont obsolètes mais toujours pris en charge. Voir <a href="../../../reference/cid.md"> CID remplace DPID et DPUUID</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>Contient un code d’intégration et un ID utilisateur unique associé dans une seule paire clé-valeur. </p> <p><code> d_cid_ic</code> remplace <code> d_dpid</code> et <code> d_dpuuid</code>, qui sont obsolètes mais toujours pris en charge. Voir <a href="../../../reference/cid.md"> CID remplace DPID et DPUUID</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>Désactivez l’utilisation des cookies tiers afin de respecter les réglementations relatives à la protection des enfants. Ce paramètre est défini de manière dynamique par le service d’identités d’Adobe Adobe Experience Platform et dépend de la configuration <code> idSyncDisable3rdPartySyncing</code>. Voir Prise <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/coppa.html?lang=fr" format="https" scope="external"> charge de la loi COPPA dans le service d’identités Adobe Experience Platform</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>Facultatif. Activé à la demande du client. Contactez votre consultant Adobe Audience Manager ou l’assistance clientèle. </p> <p>Indique que les caractéristiques et les segments doivent être renvoyés dans la réponse <code> JSON</code>. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> renvoie <a href="../../../reference/ids-in-aam.md"> identifiants de segment hérités</a> pour les segments. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> renvoie les identifiants des segments. </p> </li>
     </ul> </p> <p>Un exemple de réponse peut ressembler à celui ci-dessous : </p> <p>
     <code class="syntax javascript">
      &lbrace;
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      &rbrace;
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>Obsolète. Voir <code> d_cid</code> et <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>Obsolète. Voir <code> d_cid</code> et <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>Renvoie les données de destination de l’URL dans la réponse <code> JSON</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> est un attribut réservé, utilisé dans l’intégration entre Adobe Analytics et Audience Manager. </p> <p>Nous vous déconseillons de créer des caractéristiques qui utilisent des attributs réservés. Adobe peut modifier les attributs réservés à tout moment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>Indique la version <code> JSON</code> à utiliser dans la réponse. Normalement, vous devez définir ce paramètre sur <code> d_jsonv=1</code>. La définition de <code> d_jsonv=0</code> désactive les synchronisations des identifiants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Spécifie l'Experience Cloud ID défini et utilisé par le service <span class="keyword"> Experience Cloud</span> ID. Pour plus d’informations sur l’ECID, voir Cookies <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=fr" format="https" scope="external"> et service d’identités Experience Cloud</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>Identifiant de l’espace de noms. Indique quel conteneur JavaScript est utilisé. Utilisé par <span class="wintitle"> DIL</span> pour la synchronisation des identifiants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Permet à Audience Manager de distinguer les requêtes mobiles des requêtes de bureau. Les valeurs acceptables sont : </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Obsolète. <code> d_rs</code> est un attribut réservé, utilisé dans l’ancienne intégration entre <span class="keyword"> Adobe Analytics</span> et <span class="keyword"> Audience Manager</span>. </p> <p>Nous vous déconseillons de créer des caractéristiques qui utilisent des attributs réservés. Adobe peut modifier les attributs réservés à tout moment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>Obligatoire si vous souhaitez une réponse <code> JSON</code> du <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Si vous l’omettez, le <span class="wintitle"> DCS</span> renvoie un pixel dans l’en-tête. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">Si vous l’incluez, le <span class="wintitle"> DCS</span> renvoie un objet <code> JSON</code> dans le corps de la réponse. Voir l’exemple ci-dessous. Votre réponse pourrait être plus complexe. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      &lbrace;
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      &rbrace;
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> signifie <span class="term"> identifiant de score</span>. Il s’agit d’un identifiant unique pour une caractéristique ou un segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>Transmet une source de données pour l’évaluation des caractéristiques. Seules les caractéristiques de cette source de données sont évaluées. </p> <p>Supposons, par exemple, que vous ayez : </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Trait T1</b> avec : </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Règle de caractéristique : « <code> key1 == val1</code> » </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Source de données (<a href="../../../reference/ids-in-aam.md"> DPID</a>) : 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">Code d'intégration DPID : ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Trait T2</b> avec : </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Règle de caractéristique : « <code> key2 == val2</code> » </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Source de données (DPID) : 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">Code d'intégration DPID : ic2 </li> 
     </ul> </p> <p>Dans un exemple d’appel, <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>, seule la caractéristique T1 est renvoyée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>L'objectif est identique au paramètre <code> d_tdpid</code> décrit ci-dessus. Cependant, dans ce cas, la source de données est transmise à l’aide du code d’intégration. </p> <p>En conservant les caractéristiques décrites ci-dessus, considérez l’exemple d’appel : </p> <p>Par <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>, seul le caractère T2 est renvoyé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>ID utilisateur unique. Identifie un visiteur ou une visiteuse lorsque cette valeur n’est pas disponible à partir d’un cookie. </p> </td> 
  </tr>
 </tbody>
</table>

## h_ Attributes

Ces en-têtes contiennent des informations telles que des demandes de données et de réponses dans un appel HTTP.

| Attribut | Description |
| --- | --- |
| `h_host` | Il est défini sur le nom d’hôte de collecte de données spécifique du client. Il apparaît comme `host name .demdex.net`. Voir [Signification des appels vers le domaine Demdex](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=fr). |
| `h_user-agent` | Définissez sur la valeur de l’en-tête `User-Agent`. |
| `h_accept-language` | Définissez sur la valeur de l’en-tête `Accept-Language`. |
| `h_referer` | Définissez sur la valeur de l’en-tête `Referer`. |
| `h_referrer` | Définissez sur la valeur de l’en-tête `Referrer`. |
| `h_date` | Définissez sur la valeur de l’en-tête `Date`. |
