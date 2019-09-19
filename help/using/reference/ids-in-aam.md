---
description: Consultez ce document pour obtenir la liste complète des ID Adobe Audience Manager.
keywords: DPID; DPUUID; CID; UUID; uuid; uid, uuid, uuuid, uuuid, uuuid, uuuid, uuuid, uuuid, uuuuid, uuuid, uuuuid, uuuid, uuuuid, uuuuuid, uuuid
seo-description: Consultez ce document pour obtenir la liste complète des ID Adobe Audience Manager.
seo-title: Index des ID dans Audience Manager
solution: Audience Manager
title: Index des ID dans Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: 6d2c749813871e52c3ef81581ed50f24fe7fd22c

---


# Index des ID dans Audience Manager{#index-of-ids-in-audience-manager}

Consultez ce document pour obtenir la liste complète des ID Adobe Audience Manager.

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
   <td colname="col1"> <p>UUID AAM </p> </td> 
   <td colname="col2"> <p> <b><span class="keyword"> ID utilisateur unique d’Audience Manager</span></b> </p> <p> ID numérique de périphérique à 38 chiffres associé par <span class="keyword"> Audience Manager</span> à chaque périphérique avec lequel il interagit. Pensez à cet identifiant chaque fois que vous voyez une mention d’utilisateurs uniques dans l’interface utilisateur d’Audience Manager.<p><span class="keyword"> Audience Manager</span> tente d’enregistrer cet identifiant sous forme de cookie dans le domaine tiers "demdex.net".</p> </p> <p>L’UUID d’Audience Manager est envoyé dans les appels d’événement en tant que signal d_uuid. </p> </td> 
   <td colname="col3"> <p><code> demdex = 07955261652886032950143702505894272138</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ImsOrgId </p> </td> 
   <td colname="col2"> <p> <b>ID d’organisation</b> </p> <p>Il s’agit de l’identifiant fourni à une entreprise lors de son inscription à Experience Cloud. Pour savoir comment trouver l’ID d’organisation de votre entreprise, consultez la section <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html"> Organisations et liaison</a> de compte, puis faites défiler la liste jusqu’à Rechercher votre ID d’organisation.</p> </td> 
   <td colname="col3"> <p><code> 5DC5123F5245B1D20A490D46@AdobeOrg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>PID </p> </td> 
   <td colname="col2"> <p> <b>ID du partenaire</b> </p> <p> Le PID est l’identifiant d’une société dans <span class="keyword"> Audience Manager</span>. <span class="keyword"> Audience Manager</span> associe un imsOrgId à un PID. </p> </td> 
   <td colname="col3"> <p><code> 1352</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ECID, MID </p> </td> 
   <td colname="col2"> <p> <b>Experience Cloud ID</b> </p> <p>L’ID Experience Cloud (ECID, abréviations héritées MID ou MCID) est dérivé mathématiquement de votre ID d’organisation et de l’ID utilisateur unique d’Audience Manager <span class="keyword"></span> . Tant que ces identifiants restent constants, la génération de l'ECID approprié pour un utilisateur spécifique est simplement un problème de maths. Avec le même ID d’organisation et le même UUID Audience Manager, vous obtenez à chaque fois la même valeur ECID. Vous pouvez en savoir plus sur l’ECID dans le document <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies et Experience Cloud ID</a> . </p> </td> 
   <td colname="col3"> <p><code> mid=08382830887934830189014177072406221371 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID de trait</b> </p> <p>L’ID de caractéristique identifie de manière unique les caractéristiques de l’environnement <span class="keyword"> Audience Manager</span> . Un ID de caractéristique est affecté à chaque caractéristique de l’interface utilisateur. </p> </td> 
   <td colname="col3"> <p><code> 289983</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>SID </p> </td> 
   <td colname="col2"> <p> <b>ID de segment </b> </p> <p>L’ID de segment identifie de manière unique les segments dans l’environnement <span class="keyword"> Audience Manager</span> . Un ID de segment est affecté à chaque segment dans l’interface utilisateur. </p> </td> 
   <td colname="col3"> <p><code> 4798574</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>csegID </p> </td> 
   <td colname="col2"> <p> <b>ID de segment hérité </b> </p> <p>Cet identifiant identifie de manière unique les segments dans l’environnement <span class="keyword"> Audience Manager</span> . Un ID de segment hérité est affecté à chaque segment de l’interface utilisateur. </p> </td> 
   <td colname="col3"> <p><code> 741232</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>destID </p> </td> 
   <td colname="col2"> <p> <b>ID de destination </b> </p> <p>L’ID de destination identifie de manière unique les destinations dans l’environnement <span class="keyword"> Audience Manager</span> . Un ID est affecté à chaque destination dans l’interface utilisateur. </p> </td> 
   <td colname="col3"> <p><code> 2523</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPID </p> </td> 
   <td colname="col2"> <p> <b>ID de source de données (également appelé ID du fournisseur de données)</b> </p> <p>L’ID de source de données est un espace de noms pour les ID ou les caractéristiques. Un ID est affecté à chaque source de données (fournisseur de données) dans l’interface utilisateur. </p> </td> 
   <td colname="col3"> <p><code> 39217</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p> <b>ID utilisateur unique du fournisseur de données </b> <b>(également appelé ID de gestion de la relation client)</b> </p> <p>Identifiant tiers. Il s’agit de l’identifiant par lequel vous identifiez les utilisateurs finaux dans votre propre système de gestion de la relation client. Vous pouvez synchroniser les DPUUID avec les UUID d’ <span class="keyword"> Audience Manager</span> et synchroniser les DPUUID à partir de vos différentes sources <span class="wintitle"> de données (DPID) dans le processus</span> de synchronisation des <a href="../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md"></a>identifiants. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID CRM </p> </td> 
   <td colname="col2"> <p>Voir DPUUID ci-dessus. </p> </td> 
   <td colname="col3"> <p><code> 2132-3423vn-343fds-3432r</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CID, CID_IC </p> </td>
   <td colname="col2"> <p> <b>ID client, code d’intégration d’ID client</b> </p> <p> <b>Les paires clé-valeur CID et CID_IC <a href="../reference/cid.md"> remplacent DPID et DPUUID</a>.</b> Elles fournissent les mêmes fonctions que les DPID et les DPUUID, mais sont plus efficaces car elles incluent l’ID du fournisseur de données et l’ID utilisateur (ou code d’intégration) dans une seule paire clé-valeur. </p> </td> 
   <td colname="col3"> <p><code> 81841%013ad2948b1570a7e408a7cfb7ff4879e4 </code> </p> </td> 
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
   <td colname="col2"> <p> <b>ID de publicité de périphérique</b> </p> <p>Cet identifiant propre à chaque périphérique est utilisé à des fins de publicité. Généralement fourni par le fabricant du système d’exploitation du périphérique ou du périphérique. </p> </td> 
   <td colname="col3"> <p>IDFA, GAID, ID Roku, ID de station de lecture </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de publicité de périphérique - IDFA - périphériques iOS</b> </p> <p> <b>Les ID IDFA</b> sont des identifiants de périphériques mobiles fournis par le fabricant du périphérique. Ces identifiants représentent les périphériques qui exécutent le système d’exploitation iOS. </p> </td> 
   <td colname="col3"> <p> Le format est strictement composé de 32 chiffres hexadécimaux <i>majuscules</i> , affichés en cinq groupes et séparés par des tirets, au format 8-4-4-12, pour un total de 36 caractères. </p> <p><code> AEBE52E7-03EE-455A-B3C4-E5728396239</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>ID de publicité de périphérique - GAID - périphériques Android</b> </p> <p><b>Les identifiants GAID</b> sont des identifiants de périphérique mobile fournis par le fabricant du périphérique. Ces identifiants représentent les périphériques qui exécutent le système d’exploitation Android. </p> </td> 
   <td colname="col3"> <p>Le format est strictement composé de 32 chiffres hexadécimaux <i>minuscules</i> , affichés en cinq groupes et séparés par des tirets, au format 8-4-4-12, pour un total de 36 caractères. </p> <p> <code> e4fe9bde-caa0-47b6-908d-ffba3fa184f2</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>Roku - RIDA - Périphériques de diffusion en continu Roku</b> </p> <p><b>Les ID RIDA GAID</b> sont des identifiants de périphérique de diffusion en continu fournis par le fabricant des périphériques Roku.</p> </td>
   <td colname="col3"> <p>Le format est strictement composé de 32 chiffres hexadécimaux <i>minuscules</i> , affichés en cinq groupes et séparés par des tirets, au format 8-4-4-12, pour un total de 36 caractères. </p> <p> <code> fcb2a29c-315a-5e6b-bcfd-d889ba19aada</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col2"> <p> <b>ID de publicité Microsoft - MAID - Périphériques Windows 10</b> </p> <p><b>Les identifiants MAID</b> sont des identifiants de périphérique générés par Windows 10 par périphérique et par utilisateur.</p> </td>
   <td colname="col3"> <p>Les MAID sont formatées sous la forme de chaînes alphanumériques.</p></td>
  </tr>
   <tr> 
   <td colname="col2"> <p> <b>Samsung DUID - Dispositifs Samsung</b> </p> Les DUID Samsung sont des identifiants de périphériques fournis par les téléviseurs Samsung.</p> </td>
   <td colname="col3"> <p>Les DUID Samsung sont formatés sous la forme de chaînes alphanumériques.</p></td>
  </tr>
 </tbody> 
</table>