---
description: L'Audience Manager et le service d'identité de l'Adobe Experience Platform appellent et reçoivent les données du domaine demdex.net. Il peut sembler que Adobe travaille avec un domaine tiers inhabituel, mais ce n'est pas le cas. Cette section décrit les éléments d’un appel demdex.net.
seo-description: L'Audience Manager et le service d'identité de l'Adobe Experience Platform appellent et reçoivent les données du domaine demdex.net. Il peut sembler que Adobe travaille avec un domaine tiers inhabituel, mais ce n'est pas le cas. Cette section décrit les éléments d’un appel demdex.net.
seo-title: Signification des appels vers le domaine Demdex
solution: Audience Manager
title: Signification des appels vers le domaine Demdex
uuid: c06dae3a-f169-4712-80fb-d6d448dce51a
translation-type: tm+mt
source-git-commit: d219f6fa1e2a8396b049f86391142c00e263b629
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 5%

---


# Signification des appels vers le domaine Demdex{#understanding-calls-to-the-demdex-domain}

[!DNL Audience Manager] et le service d&#39;identité de l&#39;Adobe Experience Platform appelle et reçoit les données du domaine demdex.net. Il peut sembler que Adobe travaille avec un domaine tiers inhabituel, mais ce n&#39;est pas le cas. Cette section décrit les éléments d’un `demdex.net` appel.

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
   <td colname="col2"> <p>This is a legacy domain controlled by <span class="keyword"> Adobe</span>. Il reflète le nom original de l' <span class="keyword"> Audience Manager</span>avant l'acquisition (<span class="keyword"> Demdex</span>). <span class="keyword"> Adobe</span> a acquis <span class="keyword"> Demdex</span> en 2011 et a renommé la société en <span class="keyword"> Audience Manager</span>. Il est difficile de modifier ce domaine car il est étroitement lié à l’ <span class="keyword"> Audience Manager</span>, au service <span class="wintitle"> d’</span>ID et à notre base d’utilisateurs installée. Voir <a href="../overview/aam-overview.md#history-and-background"> Historique et arrière-plan</a>. </p> <p>D’autres préfixes peuvent être associés à des <code> demdex.net</code> appels hérités (par ex. <code> dcs.demdex.net</code>, <code> fast.demdex.net</code>etc.). Quel que soit le préfixe, un appel à <code><i>something</i>.demdex.net</code> est toujours un appel à <span class="keyword"> Adobe</span> et non à un domaine tiers inconnu ou suspect. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dpm</code> </p> </td> 
   <td colname="col2"> <p><span class="wintitle"> DPM</span> est l’abréviation de <span class="wintitle"> Data Provider Match</span>. Il indique aux systèmes <span class="keyword"> Adobe</span> internes qu’un appel d’ <span class="keyword"> Audience Manager</span> ou du service <span class="wintitle"> d’</span> ID transmet les données client pour synchronisation ou demande un identifiant. Il s’agit de l’ <code> demdex.net</code> appel le plus fréquent que vous verrez depuis <span class="keyword"> l’Audience Manager</span> ou le service <span class="wintitle"> d’</span>ID. </p> <p><span class="wintitle"> Concepts de base des appels DPM</span> : </p> <p> 
     <ul id="ul_44023BB060774518BE414EE10820C141"> 
      <li id="li_0F94D1988A6944BA885FD40AB26FC49F"> <b> <span class="keyword"> Audience Manager</span> </b>: Un appel <span class="wintitle"> DPM</span> d’ <span class="keyword"> Audience Manager</span> envoie des données aux serveurs <span class="wintitle"> de collecte de données et aux serveurs</span> <span class="wintitle"> de mise en cache de Profil. </span> Voir Composants <a href="../reference/system-components/components-data-collection.md"></a>de collecte de données. </li> 
      <li id="li_5A7EA9EE16EE4D828F0A24AE2B969122"> <b> <span class="wintitle"> Service</span> d’ID </b>: Un appel <span class="wintitle"> DPM</span> du service <span class="wintitle"> d’</span> ID est une demande d’ID de visiteur. Voir <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies et Adobe Experience Platform Identity Service</a> et <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/id-request.html" format="https" scope="external"> How the Adobe Experience Platform Identity Service request and Sets ID</a>(en anglais). </li> 
     </ul> </p> <p> <p>Remarque :  <span class="wintitle"> Les clients du service</span> d’ID peuvent modifier le préfixe <span class="wintitle"> DPM</span> dans le nom de domaine. Voir <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/subdomain-config.html" format="https" scope="external"> AudienceManager Server et audienceManagerServerSecure</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)
>* [Cookies Audience Manager](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html)

