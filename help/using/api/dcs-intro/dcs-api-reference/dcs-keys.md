---
description: Listes et décrit la syntaxe et les attributs pris en charge (ou paires clé-valeur) que vous pouvez transmettre aux serveurs de collecte de données (DCS). Ces informations peuvent vous aider à formater vos requêtes DCS et à comprendre les paramètres renvoyés par ce système.
seo-description: Listes et décrit la syntaxe et les attributs pris en charge (ou paires clé-valeur) que vous pouvez transmettre aux serveurs de collecte de données (DCS). Ces informations peuvent vous aider à formater vos requêtes DCS et à comprendre les paramètres renvoyés par ce système.
seo-title: Attributs pris en charge pour les appels d’API DCS
solution: Audience Manager
title: Attributs pris en charge pour les appels d’API DCS
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '809'
ht-degree: 2%

---


# Attributs pris en charge pour les appels d’API DCS {#supported-attributes-for-dcs-api-calls}

Liste et décrit la syntaxe et les attributs pris en charge (ou paires clé-valeur) que vous pouvez transmettre à la [!UICONTROL Data Collection Servers] ([!DNL DCS]). Ces informations peuvent vous aider à formater vos [!DNL DCS] requêtes et à comprendre les paramètres renvoyés par ce système.

## Préfixes d’attributs {#attribute-prefixes}

Le module [!DNL DCS] repose sur des préfixes spécifiques ajoutés aux clés dans des paires clé-valeur pour classer le type de données que vous transmettez.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Préfixe de clé </th> 
   <th colname="col2" class="entry"> Réservé pour </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>Attributs définis par le client. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Attributs d’Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>Données d’en-tête HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Attributs privés définis par le client. </p> <p> Le serveur de collecte de données accepte vos propres données privées lorsque la clé comporte un <code> p_</code> préfixe. Les données privées sont utilisées pour l'évaluation des caractéristiques, mais elles ne seront ni enregistrées ni stockées dans notre système. Par exemple, supposons que vous ayez une caractéristique définie comme <code> customers = p_age&lt;25</code> et que vous la transmettiez <code> p_age=23</code> dans un appel de événement. Compte tenu de ces conditions, l’utilisateur qui satisfait aux critères de qualification par âge est admissible pour la caractéristique, mais la paire clé-valeur est supprimée après que l’ <span class="keyword"> Audience Manager</span> a reçu la demande et n’a pas été enregistrée. </p> </td>
  </tr> 
 </tbody> 
</table>

## d_ Attributs {#d-attributes}

Toutes ces options sont facultatives, sauf si vous souhaitez obtenir une réponse de la part de la [!DNL DCS]. Si vous souhaitez que le [!DNL DCS] renvoie une réponse, `d_rtbd=json` il est nécessaire.

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
   <td colname="col2"> <p>Utilisé pour identifier l’appelant qui effectue l’appel à l’API <span class="wintitle"> DCS</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Spécifie une fonction JavaScript à exécuter à l’aide de la réponse DCS <span class="wintitle"></span> en tant que paramètre de fonction de la fonction de rappel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Contient une ou plusieurs paires d’ID de fournisseur de données (<code> DPID</code>) et d’ID d’utilisateur de fournisseur de données (<code> DPUUID</code>) attribuées par <span class="keyword"> Audience Manager</span>. Si vous utilisez plusieurs paires de <code> DPID</code>s et <code> DPUUID</code>s, séparez chaque paire par le caractère non imprimable <code> %01</code>. Par exemple: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> remplace <code> d_dpid</code> et <code> d_dpuuid</code>, qui sont obsolètes mais toujours pris en charge. Voir <a href="../../../reference/cid.md">CID remplace DPID et DPUUID</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>Contient un code d’intégration et un ID utilisateur unique associé dans une seule paire clé-valeur. </p> <p><code> d_cid_ic</code> remplace <code> d_dpid</code> et <code> d_dpuuid</code>, qui sont obsolètes mais toujours pris en charge. Voir <a href="../../../reference/cid.md">CID remplace DPID et DPUUID</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>Désactiver l’utilisation de cookies tiers afin de se conformer aux règles de protection de l’enfance. Ce paramètre est défini dynamiquement par le service d’identité de l’Adobe Experience Platform Adobe et dépend de la <code> idSyncDisable3rdPartySyncing</code> configuration. Reportez-vous à la section Prise en charge <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/coppa.html" format="https" scope="external"> COPPA dans Adobe Experience Platform Identity Service</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>Facultatif. Activé sur demande du client. Contactez votre conseiller en Adobe Audience Manager ou le service à la clientèle. </p> <p>Indique que les caractéristiques et les segments doivent être renvoyés dans la <code> JSON</code> réponse. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> renvoie des ID <a href="../../../reference/ids-in-aam.md"> de segment</a> hérités pour les segments. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> renvoie des ID de segment pour les segments. </p> </li>
     </ul> </p> <p>Un exemple de réponse peut se présenter comme suit : </p> <p>
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
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
   <td colname="col2"> <p>Renvoie les données de destination de l’URL dans la <code> JSON</code> réponse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> est un attribut réservé, utilisé dans l’intégration entre Adobe Analytics et l’Audience Manager. </p> <p>Nous vous déconseillons de créer des caractéristiques qui utilisent des attributs réservés. Adobe peut modifier les attributs réservés à tout moment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>Indique la <code> JSON</code> version à utiliser dans la réponse. Normalement, vous devez définir cette valeur sur <code> d_jsonv=1</code>. La définition <code> d_jsonv=0</code> désactive la synchronisation des identifiants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Indique l’ID d’Experience Cloud défini et utilisé par le service d’ID d’ <span class="keyword"> Experience Cloud</span> . Pour plus d’informations sur l’ECID, voir <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies et Service</a>d’identité Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>Nommer l’ID d’espace. Indique quel conteneur JavaScript est utilisé. Utilisé par <span class="wintitle"> DIL</span> à pour la synchronisation des identifiants. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Permet à l’Audience Manager de distinguer les demandes mobiles des demandes de bureau. Les valeurs acceptables sont : </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Obsolète. <code> d_rs</code> est un attribut réservé, utilisé dans l’intégration héritée entre <span class="keyword"> Adobe Analytics</span> et <span class="keyword"> Audience Manager</span>. </p> <p>Nous vous déconseillons de créer des caractéristiques qui utilisent des attributs réservés. Adobe peut modifier les attributs réservés à tout moment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>Obligatoire si vous souhaitez obtenir une <code> JSON</code> réponse du <span class="wintitle"> serveur de collecte de données</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Si vous l’omettez, le <span class="wintitle"> serveur de collecte de données</span> renvoie un pixel dans l’en-tête. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">Si vous incluez ceci, le <span class="wintitle"> serveur de collecte de données</span> renvoie un <code> JSON</code> objet dans le corps de la réponse. Consultez l’exemple ci-dessous. Votre réponse pourrait être plus complexe. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> correspond à l’ID <span class="term"> de</span>score. Il s’agit d’un identifiant unique pour une caractéristique ou un segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>Transmet une source de données pour l’évaluation des caractéristiques. Seules les caractéristiques de cette source de données sont évaluées. </p> <p>Par exemple, supposons que vous possédiez : </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Caractéristique T1</b> avec : </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Règle de caractéristiques : "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Source de données (<a href="../../../reference/ids-in-aam.md"> DPID</a>) : 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">Code d'intégration DPID : ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Caractéristique T2</b> avec : </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Règle de caractéristiques : "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Source de données (DPID) : 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">Code d'intégration DPID : ic2 </li> 
     </ul> </p> <p>Dans un exemple d’appel, <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>, seule la caractéristique T1 est renvoyée. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>L'objectif est identique au <code> d_tdpid</code> paramètre décrit ci-dessus. Cependant, dans ce cas, la source de données est transmise à l’aide du code d’intégration. </p> <p>En conservant les caractéristiques décrites ci-dessus, tenez compte de l’appel d’exemple : </p> <p>En effet, <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>seul le trait T2 est renvoyé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>ID utilisateur unique. Identifie un visiteur lorsque cette valeur n’est pas disponible à partir d’un cookie. </p> </td> 
  </tr>
 </tbody>
</table>