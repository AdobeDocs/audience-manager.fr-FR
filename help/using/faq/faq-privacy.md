---
description: Réponses aux questions et problématiques courantes concernant la confidentialité des données.
seo-description: Réponses aux questions et problématiques courantes concernant la confidentialité des données.
seo-title: ' FAQ sur la confidentialité et la rétention des données'
solution: Audience Manager
title: ' FAQ sur la confidentialité et la rétention des données'
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 3a4f23bc853a2324a4c91c6e65b14455293a5b1b

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Réponses aux questions et problématiques courantes concernant la confidentialité des données.

<!-- faq_privacy.xml -->

## FAQ sur la confidentialité {#privacy-faq}

>[!TIP]
>
>Consultez le Centre [de traitement des données personnelles](https://www.adobe.com/privacy.html) Adobe pour en savoir plus.

**Comment Audience Manager utilise-t-il les cookies et quels cookies sont-ils définis ?**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**Les clients Audience Manager aux Etats-Unis peuvent-ils cibler les utilisateurs sur les propriétés de l’UE ?**

Oui. Audience Manager travaille avec des clients qui possèdent des propriétés et des stocks internationaux. L’UE a des lois strictes sur la confidentialité, mais Audience Manager a des clients qui utilisent des données propriétaires pour le ciblage d’audience en Europe. Audience Manager peut prendre en charge le ciblage pour les publics de l’UE, mais il vous incombe de respecter les règles de confidentialité locales.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## FAQ sur la rétention des données {#data-retention-faq}

Le tableau suivant répertorie les temps de rétention des différents types de données et systèmes de stockage.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de données, source ou stockage </th> 
   <th colname="col2" class="entry"> Période de conservation des données </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Serveurs dorsaux </p> </td> 
   <td colname="col2"> <p>120-days. </p> <p> Audience Manager supprime les données utilisateur de nos serveurs principaux 120 jours après la dernière visite d’un utilisateur sur la plateforme Audience Manager. Si <span class="keyword"> Audience Manager</span> enregistre l’activité de l’utilisateur au cours de ce cycle de 120 jours, nous conservons ces données pendant encore 120 jours. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs Edge </p> </td> 
   <td colname="col2"> <p> 14-days. </p> <p>Audience Manager supprime les données utilisateur de nos serveurs Edge 14 jours après la dernière visite d’un utilisateur sur la plateforme Audience Manager. If <span class="keyword"> Audience Manager</span> records user activity in within this 14-day cycle, we will keep this data for another 14-days. If the user becomes active again after the 14-day period, there will be a delay between that first new page view and when the user becomes actionable. Il faut de 6 à 18 heures pour que le profil complet soit remis au centre du bord après plus de 14 jours d'inactivité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Raw logs </p> </td> 
   <td colname="col2"> <p>180-days (removed after 180-days of no activity). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ad Server Logs </p> </td> 
   <td colname="col2"> <p><b>Création de rapports</b> </p> <p>Log files are retained for reporting purposes for up to 30 days. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and  Audience Manager ID) in our backend storage, and matched logs stored in  Amazon S3 are retained for up to 30 days.<span class="keyword"></span><span class="keyword"></span> </p> <p><b>Fichiers journaux pratiques</b> </p> <p>Both matched and unmatched logs are retained for up to 30 days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-level profiles (authenticated profiles) </p> </td> 
   <td colname="col2"> <p>The default time-to-live (TTL) interval for inactive CRM-level profiles (Customer IDs) is 24 months. However, you can use the Audience Manager UI to reduce or extend the TTL interval for inactive CRM-level profiles between one month and 5 years. Vous pouvez y parvenir lors de la création ou de la modification d’une source de données sur plusieurs périphériques.</p> <p>For more information, see Data Source Settings in  Create a Cross-Device Data Source .<a href="../features/profile-merge-rules/merge-rules-start.md#settings"></a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobile Device IDs </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs ( IDFA, GAID) follow the cadence described in the first two rows, back-end servers and edge servers.<a href="../reference/ids-in-aam.md"></a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Flux de données client (CDF) </p> </td> 
   <td colname="col2"> <p>Un fichier CDF contient les mêmes données qu’un appel d’événement <span class="keyword"> Audience Manager</span> (/event) envoie à nos serveurs. La période de rétention est de 8 jours. Pour plus d'informations sur CDF, veuillez consulter les FAQ <a href="../features/cdf-files.md"> Intro</a> et <a href="../faq/faq-cdf.md"></a>CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappages entre ID synchronisés </p> </td> 
   <td colname="col2"> <p>La durée de vie des mappages <a href="../features/administration/usage-limits.md#id-mapping-limits"> d’</a> ID entre les identifiants de cookie Audience Manager (identifiants d’utilisateur uniques<a href="../reference/ids-in-aam.md">Audience Manager ou identifiants UUUID</a>AAM) et les identifiants de cookie tiers est limitée à 120 jours. La durée de vie du mappage des identifiants est réinitialisée chaque fois que le cookie Audience Manager est affiché sur le réseau Audience Manager. La synchronisation de mappage des identifiants la plus récente sera conservée pendant la durée de vie de l’ID utilisateur unique <a href="../reference/ids-in-aam.md">Audience Manager (UUID AAM)</a>associé.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Données entrantes </p> </td> 
   <td colname="col2"> <p>Il s’agit des données entrantes que vous envoyez à <span class="keyword"> Audience Manager</span> par FTP ou directement vers un répertoire <span class="keyword"> Amazon S3</span> . Consultez la FAQ <a href="../faq/faq-inbound-data-ingestion.md"> sur l’envoi de données client</a>entrant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Données sortantes </p> </td> 
   <td colname="col2"> <p>Il s’agit des données de lot envoyées par <span class="keyword"> Audience Manager</span> aux partenaires d’activation tiers. La période de rétention est de 8 jours. Pour plus d'informations sur les données sortantes, reportez-vous à la section Transferts <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"></a>de lots sortants. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Rétention des données de qualification des caractéristiques {#trait-qual}

Le tableau ci-dessous répertorie les options de rétention pour les qualifications de caractéristiques.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opération Trait </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Suppression d’une caractéristique </p> </td> 
   <td colname="col2"> <p>La suppression d’une caractéristique supprime les données de qualification des caractéristiques de tous les profils d’utilisateur qui étaient qualifiés pour la caractéristique dans le passé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de caractères atteinte </p> </td> 
   <td colname="col2"> <p>Nous imposons une limite de 100 000 qualifications de caractéristiques pour chaque profil utilisateur. La limite s’applique aux profils authentifiés et aux profils de périphérique. Si un profil utilisateur atteint cette limite, nous supprimerons les caractéristiques les plus anciennes, en fonction du premier entré, premier sorti. </p> <p>Pour plus de détails, lisez notre <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> limite de qualification des caractéristiques</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

