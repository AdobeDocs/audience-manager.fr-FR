---
description: Audience Manager et le service Experience Cloud ID effectuent des appels au domaine demdex.net et en reçoivent des données. Adobe semble travailler avec un domaine tiers inhabituel, mais ce n’est pas le cas. Cette section décrit les éléments d’un appel demdex.net.
seo-description: Audience Manager et le service Experience Cloud ID effectuent des appels au domaine demdex.net et en reçoivent des données. Adobe semble travailler avec un domaine tiers inhabituel, mais ce n’est pas le cas. Cette section décrit les éléments d’un appel demdex.net.
seo-title: Signification des appels vers le domaine Demdex
solution: Audience Manager
title: Signification des appels vers le domaine Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Signification des appels vers le domaine Demdex{#understanding-calls-to-the-demdex-domain}

Audience Manager et le service Experience Cloud ID effectuent des appels au domaine demdex.net et en reçoivent des données. Adobe semble travailler avec un domaine tiers inhabituel, mais ce n’est pas le cas. Cette section décrit les éléments d’un appel demdex.net.

<table id="table_B846CBEDDA4C4AD19416F7C27FC325C6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elément Appel </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> demdex.net</code> </p> </td> 
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. Il reflète le nom d’origine de <span class="keyword"> Audience Manager</span>avant l’acquisition (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> a acquis <span class="keyword"> Demdex</span> en 2011 et l’a renommée <span class="keyword"> Audience Manager</span>. Il est difficile de modifier ce domaine car il est étroitement lié à <span class="keyword"> Audience Manager</span>, au service <span class="wintitle"> d’</span>ID et à notre base d’utilisateurs installée. Voir <a href="../overview/aam-overview.md#history-and-background"> Historique et Arrière-plan</a>. </p> <p>Vous pouvez voir d’autres préfixes associés aux <code> demdex.net</code> appels hérités (par ex. <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>, etc.). Quel que soit le préfixe, un appel à <code><i>something</i>.demdex.net</code> est toujours un appel à <span class="keyword"> Adobe</span> et non à un domaine tiers inconnu ou suspect. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> est une abréviation de <span class="wintitle"> Correspondance avec le fournisseur de données</span>. Il indique aux systèmes internes d’Adobe <span class="keyword"> qu’un appel d’</span> Audience Manager <span class="keyword"> ou du service</span> d’ <span class="wintitle"></span> ID transmet les données client pour synchronisation ou demande un ID. Il s’agit de l’ <code> demdex.net</code> appel le plus fréquent que vous verrez à partir d’ <span class="keyword"> Audience Manager</span> ou du service <span class="wintitle"> d’</span>ID. </p> <p><span class="wintitle"> Concepts de base des appels DPM</span> : </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span> </b>: Un appel <span class="wintitle"> DPM</span> d’Audience Manager <span class="keyword"> envoie des données aux serveurs</span> de collecte de données et aux serveurs <span class="wintitle"> de mise en cache de</span> <span class="wintitle"> profils. </span> Voir Composants <a href="../reference/system-components/components-data-collection.md"> de collecte de</a>données. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> Service <span class="wintitle"> d’</span> ID </b>: Un appel <span class="wintitle"> DPM</span> du service <span class="wintitle"> d’</span> ID est une demande d’identifiant visiteur. Voir <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_cookies.html" format="https" scope="external"> Cookies et Service</a> d’ID Experience Cloud et <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_id_request.html" format="https" scope="external"> Comment le service d’ID Experience Cloud demande et définit des ID</a>. </li> 
     </ul> </p> <p> <p>Remarque :  Les clients du service <span class="wintitle"> d’</span> ID peuvent modifier le préfixe <span class="wintitle"> DPM</span> dans le nom de domaine. Voir <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-subdomain-config.html" format="https" scope="external"> Serveur AudienceManager et AudienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Service Experience Cloud ID](https://marketing.adobe.com/resources/help/en_US/mcvid/)
>* [Cookies Audience Manager](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html)

