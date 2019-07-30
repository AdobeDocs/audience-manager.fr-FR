---
description: Reportez-vous à ce document pour obtenir la liste complète des identifiants Adobe Audience Manager.
keywords: DPID ; DPUUID ; CID ; UUID ; uuid ; uuid
seo-description: Reportez-vous à ce document pour obtenir la liste complète des identifiants Adobe Audience Manager.
seo-title: Index des ID dans Audience Manager
solution: Audience Manager
title: Index des ID dans Audience Manager
uuid: 292185 ec -7 c 6 a -414 b-ab 17-800 c 21 cb 1 f 01
translation-type: tm+mt
source-git-commit: cf0cec2fdf1272f075a825b09cf2fa11a3815432

---


# Index of IDs in Audience Manager{#index-of-ids-in-audience-manager}

Reportez-vous à ce document pour obtenir la liste complète des identifiants Adobe Audience Manager.

<table frame="all" id="table_6727BA8BBF2C40E48768126B4EC9984E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Nom et description </th> 
   <th colname="col3" class="entry"> Exemple </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>AAM UUID </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> Utilisateur</span> unique Audience Manager - id </b> </p> <p> A numerical, 38-digit device ID that <span class="keyword"> Audience Manager</span> associates to each device it interacts with. Pensez à cet identifiant chaque fois que vous voyez une mention d'utilisateurs uniques dans l'interface utilisateur d'Audience Manager.<p><span class="keyword"> Audience Manager</span> tente d'enregistrer cet ID sous forme de cookie dans le domaine tiers demdex. net.</p> </p> <p>L'UUID Audience Manager est envoyé dans les appels d'événement comme signal d_ uuid. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imsorgid </p> </td> 
   <td colname="col2"> <p> <b>ID d’organisation</b> </p> <p>Il s'agit de l'identifiant fourni par une société lors de la souscription pour Experience Cloud. To learn how you can find your company's Organization ID, read <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organizations and Account Linking</a> and scroll down to Find your Organization ID.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>ID du partenaire</b> </p> <p> The PID is a company's ID in <span class="keyword"> Audience Manager</span>. <span class="keyword"> Audience Manager</span> associe un élément imsorgid à un identifiant PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>The Experience Cloud ID (ECID, legacy abbreviations MID or MCID) is derived mathematically from your Organization ID and the <span class="keyword"> Audience Manager</span> Unique User ID. Tant que ces identifiants restent constants, la génération de l'ECID correct pour un utilisateur spécifique n'est qu'un problème mathématique. Avec le même ID d'organisation et l'UUID Audience Manager, vous obtenez chaque fois la même valeur ECID. You can read more about the ECID in the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies and Experience Cloud ID</a> document. </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID de caractéristique</b> </p> <p>The Trait ID uniquely identifies traits in the <span class="keyword"> Audience Manager</span> environment. Un identifiant de caractéristique est affecté à chaque caractéristique dans l'interface utilisateur (UI). </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID de segment </b> </p> <p>The Segment ID uniquely identifies segments in the <span class="keyword"> Audience Manager</span> environment. Un identifiant de segment est affecté à chaque segment dans l'interface utilisateur. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Csegid </p> </td> 
   <td colname="col2"> <p> <b>ID de segment hérité </b> </p> <p>This ID uniquely identifies segments in the <span class="keyword"> Audience Manager</span> environment. Un identifiant de segment hérité est affecté à chaque segment dans l'interface utilisateur. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destid </p> </td> 
   <td colname="col2"> <p> <b>ID de destination </b> </p> <p>The Destination ID uniquely identifies destinations in the <span class="keyword"> Audience Manager</span> environment. Un ID est affecté à chaque destination dans l'interface utilisateur. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>Identifiant de source de données (également appelé ID de fournisseur de données)</b> </p> <p>L'ID de source de données est un namespace de noms pour les ID ou caractéristiques. Un ID est affecté à chaque source de données (fournisseur de données) dans l'interface utilisateur. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>Utilisateur unique du fournisseur de données - id </b><b>(également appelé identifiant CRM)</b> </p> <p>Un identifiant tiers. Il s'agit de l'ID par lequel vous identifiez la fin - utilisateurs dans votre propre système de gestion de la relation client. You can sync DPUUIDs with <span class="keyword"> Audience Manager</span> UUIDs and you can sync DPUUIDs from your different <span class="wintitle"> Data Sources</span> (DPIDs) in the <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"> ID synchronization process</a>. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 vn -343 fds -3432 r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifiant de la gestion de la relation client </p> </td> 
   <td colname="col2"> <p>Voir DPUUID ci-dessus. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423 vn -343 fds -3432 r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_ IC </p> </td>
   <td colname="col2"> <p> <b>ID de client, code d'intégration de l'ID client</b> </p> <p> <b>Les paires CID et CID_ IC <a href="../reference/cid.md"> sont remplacées par DPID et DPUUID</a>.</b> Elles fournissent les mêmes fonctions que DPID et DPUUID, mais elles sont plus efficaces car elles incluent l'identifiant de fournisseur de données et l'utilisateur - id (ou code d'intégration) dans une paire clé-valeur unique. </p> </td> 
   <td colname="col3"> <p><code> 81841% 013 ad 2948 b 1570 a 7 e 408 a 7 cfb 7 ff 4879 e 4 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="2"> <p>DAID </p> <p> 
     <ul id="ul_4EA61BDD0C9140C894162F50300BA9DB"> 
      <li id="li_16148BDD80194F509FF7935364B77F7A">IDFA </li> 
      <li id="li_DF7FEEF2D46A42C5B9FECD6377758B1A">GAID </li>
      <li>RIDA</li>
      <li>MAID</li>
      <li>DUID</li>
     </ul> </p> </td> 
   <td colname="col2"> <p> <b>ID de publication de périphérique</b> </p> <p>Cet identifiant propre à chaque périphérique est utilisé à des fins de publicité. Généralement fourni par le fabricant du périphérique ou du système d'exploitation du périphérique. </p> </td> 
   <td colname="col3"> <p>IDFA, GAID, Roku ID, Playstation ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de publication de périphérique - IDFA - Périphériques ios</b> </p> <p> <b>Les identifiants IDFA</b> sont des identifiants de périphérique mobile fournis par le fabricant du périphérique. Ces ID représentent les périphériques qui exécutent le système d'exploitation ios. </p> </td> 
   <td colname="col3"> <p> The format strictly consists of 32 <i>uppercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p><code> AEBE 52 E 7-03 EE -455 A-B 3 C 4-E 57283966239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de publication de périphérique - GAID - Périphériques Android</b> </p> <p><b>Les identifiants GAID</b> sont des identifiants de périphérique mobile fournis par le fabricant du périphérique. Ces ID représentent les périphériques qui exécutent le système d'exploitation Android. </p> </td> 
   <td colname="col3"> <p>The format strictly consists of 32 <i>lowercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p> <code> e 4 fe 9 bde-caa 0-47 b 6-908 d-ffba 3 fa 184 f 2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Périphériques continus Roku</b> </p> <p><b>Les</b> identifiants RIDA GAID sont des identifiants de périphérique en flux continu fournis par le fabricant des dispositifs Roku.</p> </td>
   <td colname="col3"> <p>The format strictly consists of 32 <i>lowercase</i> hexadecimal digits, displayed in five groups and separated by hyphens, in the form 8-4-4-4-12, for a total of 36 characters. </p> <p> <code> fcb 2 a 29 c -315 a -5 e 6 b-bcfd-d 889 ba 19 aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>ID de publication Microsoft - Périphériques MAID - Windows 10</b> </p> <p><b>Les identifiants MAID</b> sont des identifiants de périphérique générés par Windows 10 sur un périphérique par périphérique.</p> </td>
   <td colname="col3"> <p>Les maid sont formatés sous forme de chaînes alphanumériques.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Périphériques Samsung</b> </p> Les identifiants Samsung sont des identifiants de périphérique fournis par Samsung TV.</p> </td>
   <td colname="col3"> <p>Les identifiants Samsung duid sont formatés sous forme de chaînes alphanumériques.</p></td>
  </tr>
 </tbody> 
</table>