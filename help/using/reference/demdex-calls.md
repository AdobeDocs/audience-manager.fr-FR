---
description: ' Gestionnaire de et le service d’identité Adobe Experience Platform appellent et reçoivent des données du domaine demdex.net. Adobe semble travailler avec un domaine tiers inhabituel, mais ce n’est pas le cas. Cette section décrit les éléments d’un appel demdex.net.'
seo-description: ' Gestionnaire de et le service d’identité Adobe Experience Platform appellent et reçoivent des données du domaine demdex.net. Adobe semble travailler avec un domaine tiers inhabituel, mais ce n’est pas le cas. Cette section décrit les éléments d’un appel demdex.net.'
seo-title: Signification des appels vers le domaine Demdex
solution: Audience Manager
title: Signification des appels vers le domaine Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Signification des appels vers le domaine Demdex{#understanding-calls-to-the-demdex-domain}

 Gestionnaire de et le service d’identité Adobe Experience Platform appellent et reçoivent des données du domaine demdex.net. Adobe semble travailler avec un domaine tiers inhabituel, mais ce n’est pas le cas. Cette section décrit les éléments d’un appel demdex.net.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément d’appel </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. Il reflète le nom original de <span class="keyword"> Manager</span>avant l’acquisition (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> a acquis <span class="keyword"> Demdex</span> en 2011 et a renommé le  en tant que <span class="keyword"> Gestionnaire de  de</span>. Il est difficile de modifier ce domaine car il est étroitement lié à  Gestionnaire <span class="keyword"> de</span>de, au service <span class="wintitle"> d’</span>ID et à notre base d’utilisateurs installée. Voir <a href="../overview/aam-overview.md#history-and-background"> Historique et Arrière-plan</a>. </p> <p>Vous pouvez voir d’autres préfixes associés aux <code> demdex.net</code> appels hérités (par ex. <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>, etc.). Quel que soit le préfixe, un appel à <code><i>something</i>.demdex.net</code> est toujours un appel à <span class="keyword"> Adobe</span> et non à un domaine tiers inconnu ou suspect. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> est une abréviation de <span class="wintitle"> Correspondance avec le fournisseur de données</span>. Il indique aux systèmes internes d’ <span class="keyword"> Adobe</span> qu’un appel de  Gestionnaire <span class="keyword"> de</span> de ou du service <span class="wintitle"> d’</span> ID transmet les données client pour synchronisation ou demande un ID. Il s’agit de l’ <code> demdex.net</code> appel le plus fréquent que vous verrez de la part de <span class="keyword"> Gestionnaire</span> de  de ou du service <span class="wintitle"> d’</span>ID. </p> <p><span class="wintitle"> Concepts de base des appels DPM</span> : </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b>  Gestionnaire <span class="keyword"> de</span></b>: Un appel <span class="wintitle"> DPM</span> de <span class="keyword"> Gestionnaire de</span> de envoie des données aux serveurs <span class="wintitle"> de collecte de données et aux serveurs</span> <span class="wintitle"> de  cache de l’. </span> Voir Composants <a href="../reference/system-components/components-data-collection.md"> de collecte de</a>données. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> Service <span class="wintitle"> d’</span> ID </b>: Un appel <span class="wintitle"> DPM</span> du service <span class="wintitle"> d’</span> ID est une demande d’ID de. Reportez-vous aux sections <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies et Service</a> d’identité Adobe Experience Platform et <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> Comment le service d’identité Adobe Experience Platform demande et définit des identifiants</a>. </li> 
     </ul> </p> <p> <p>Remarque :  Les clients du service <span class="wintitle"> d’</span> ID peuvent modifier le préfixe <span class="wintitle"> DPM</span> dans le nom de domaine. Voir <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> Serveur AudienceManager et AudienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Cookies Audience Manager](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

