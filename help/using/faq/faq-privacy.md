---
description: Réponses aux questions et problématiques courantes concernant la confidentialité des données.
seo-description: Réponses aux questions et problématiques courantes concernant la confidentialité des données.
seo-title: FAQ sur la confidentialité et la rétention des données
solution: Audience Manager
title: FAQ sur la confidentialité et la rétention des données
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 5%

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Réponses aux questions et problématiques courantes concernant la confidentialité des données.

<!-- faq_privacy.xml -->

## FAQ sur la confidentialité {#privacy-faq}

>[!TIP]
>
>Pour plus d&#39;informations, consultez le Centre [de confidentialité](https://www.adobe.com/privacy.html) Adobe.

**Comment l&#39;Audience Manager utilise-t-elle les cookies et quels cookies est-elle définie ?**

See [Audience Manager Cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html).

**Les clients d&#39;Audience Manager aux États-Unis peuvent-ils utiliser des cibles sur les propriétés de l&#39;UE ?**

Oui. Audience Manager travaille avec des clients qui ont des biens et des stocks internationaux. L&#39;UE a des lois strictes sur la protection des renseignements personnels, mais l&#39;Audience Manager a des clients qui utilisent des données propriétaires pour cibler les audiences en Europe. L&#39;Audience Manager peut soutenir le ciblage des audiences de l&#39;UE, mais il est de votre responsabilité de respecter les réglementations locales en matière de confidentialité.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## FAQ sur la rétention des données {#data-retention-faq}

Le tableau suivant liste les temps de rétention pour différents types de données et systèmes d&#39;enregistrement.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de données, source ou Enregistrement </th> 
   <th colname="col2" class="entry"> Période de conservation des données </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Serveurs back-end </p> </td> 
   <td colname="col2"> <p>120 jours. </p> <p> L'Audience Manager supprime les données utilisateur de nos serveurs principaux 120 jours après la dernière visite d'un utilisateur sur la plateforme d'Audience Manager. Si <span class="keyword"> l'Audience Manager</span> enregistre l'activité des utilisateurs dans ce cycle de 120 jours, nous conserverons ces données pendant 120 jours supplémentaires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs Edge </p> </td> 
   <td colname="col2"> <p> 14 jours. </p> <p>L'Audience Manager supprime les données utilisateur de nos serveurs Edge 14 jours après la dernière visite d'un utilisateur sur la plateforme d'Audience Manager. Si <span class="keyword"> l'Audience Manager</span> enregistre l'activité des utilisateurs dans ce cycle de 14 jours, nous conserverons ces données pendant 14 jours supplémentaires. Si l’utilisateur est de nouveau actif après la période de 14 jours, un délai s’écoulera entre cette première nouvelle vue de page et le moment où l’utilisateur pourra agir. Il faut entre 6 et 18 heures pour que le profil complet soit remis au centre de bord après plus de 14 jours d'inactivité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Journaux bruts </p> </td> 
   <td colname="col2"> <p>180 jours (enlevé après 180 jours sans activité). </p> <p>Les journaux bruts sont des données reçues par un serveur Edge via des appels HTTP ou à partir de fichiers intégrés envoyés à <span class="keyword"> l'Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Journaux du serveur d’annonces </p> </td> 
   <td colname="col2"> <p><b>Création de rapports</b> </p> <p>Les fichiers journaux sont conservés à des fins de rapports pendant 30 jours au maximum. Nous ne conservons pas les journaux non concordants (c.-à-d. les journaux pour lesquels il n’existe aucune synchronisation d’ID entre un ID de serveur d’visiteurs et un ID d’Audience Manager <span class="keyword"> ) dans notre enregistrement principal, et les journaux correspondants stockés dans</span> Amazon S3 <span class="keyword"></span> sont conservés pendant 30 jours au maximum. </p> <p><b>Fichiers journaux pratiques</b> </p> <p>Les journaux correspondants et non correspondants sont conservés pendant 30 jours au maximum. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>profils au niveau de la gestion de la relation client (profils authentifiés) </p> </td> 
   <td colname="col2"> <p>L’intervalle de durée de vie par défaut pour les profils inactifs au niveau de la gestion de la relation client (ID de client) est de 24 mois. Cependant, vous pouvez utiliser l’interface utilisateur de l’Audience Manager pour réduire ou étendre l’intervalle TTL pour les profils inactifs au niveau de la gestion de la relation client entre un mois et 5 ans. Pour ce faire, vous pouvez créer ou modifier une source de données sur plusieurs périphériques.</p> <p>Pour plus d’informations, voir Paramètres de source de données dans <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Création d’une source de données sur plusieurs périphériques </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de périphérique mobile </p> </td> 
   <td colname="col2"> <p>Les conditions de rétention des identifiants de périphériques mobiles (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) suivent la cadence décrite dans les deux premières lignes, les serveurs principaux et les serveurs Edge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Flux de données client (CDF) </p> </td> 
   <td colname="col2"> <p>Un fichier CDF contient les mêmes données qu'un appel de événement <span class="keyword"> Audience Manager</span> (/événement) envoyé à nos serveurs. La période de rétention est de 8 jours. Pour plus d'informations sur CDF, consultez la FAQ <a href="../features/cdf-files.md"> sur</a> CDF Intro <a href="../faq/faq-cdf.md"> et</a>CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappages entre les ID synchronisés </p> </td> 
   <td colname="col2"> <p>La durée de vie des mappages <a href="../features/administration/usage-limits.md#id-mapping-limits"> d’</a> ID entre les identifiants de cookie d’Audience Manager (identifiants d’utilisateur uniques d’<a href="../reference/ids-in-aam.md">Audience Manager ou UUID</a>AAM) et les identifiants de cookie tiers est limitée à 120 jours. La durée de vie du mappage des identifiants est réinitialisée chaque fois que le cookie d’Audience Manager est visible sur le réseau d’Audiences Manager. La synchronisation de mappage des identifiants la plus récente sera conservée pendant la durée de vie de l’ID utilisateur unique d’ <a href="../reference/ids-in-aam.md">Audience Manager (UUID AAM)</a>associé.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Données entrantes </p> </td> 
   <td colname="col2"> <p>Il s’agit des données entrantes que vous envoyez à <span class="keyword"> l’Audience Manager</span> par FTP ou directement vers un répertoire <span class="keyword"> Amazon S3</span> . Consultez la FAQ <a href="../faq/faq-inbound-data-ingestion.md"> sur l'importation des données client</a>entrantes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Données sortantes </p> </td> 
   <td colname="col2"> <p>Il s'agit des données de lot envoyées par <span class="keyword"> Audience Manager</span> à des partenaires d'activation tiers. La période de rétention est de 8 jours. Pour plus d'informations sur les données sortantes, reportez-vous à la section Transferts <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"></a>de lots sortants. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Conservation des données de qualification des caractéristiques {#trait-qual}

Le tableau ci-dessous liste les options de rétention pour les qualifications de caractéristiques.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opération de caractéristiques </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Suppression d’une caractéristique </p> </td> 
   <td colname="col2"> <p>La suppression d’une caractéristique supprime les données de qualification des caractéristiques de tous les profils d’utilisateurs qui s’étaient qualifiés pour cette caractéristique dans le passé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de caractéristiques atteinte </p> </td> 
   <td colname="col2"> <p>Nous imposons une limite de 100 000 qualifications de caractéristiques pour chaque profil utilisateur. La limite s’applique aux profils authentifiés et aux profils de périphériques. Si un profil utilisateur atteint cette limite, nous supprimerons les caractéristiques les plus anciennes, en fonction du premier entré et du premier sorti. </p> <p>Pour plus de détails, lisez notre <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit"> limite</a>de qualification des caractéristiques. </p> </td> 
  </tr> 
 </tbody> 
</table>

