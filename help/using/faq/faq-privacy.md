---
description: Réponses aux questions et problématiques courantes concernant la confidentialité des données.
seo-description: Réponses aux questions et problématiques courantes concernant la confidentialité des données.
seo-title: FAQ sur la confidentialité et la rétention des données
solution: Audience Manager
title: FAQ sur la confidentialité et la rétention des données
uuid: ef 558 fca -35 ff -44 f 1-8527-f 8 bee 9 f 2 c 7 e 9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Privacy and Data Retention FAQ{#privacy-and-data-retention-faq}

Réponses aux questions et problématiques courantes concernant la confidentialité des données.

<!-- faq_privacy.xml -->

## Privacy FAQ {#privacy-faq}

>[!TIP]
>
>Visit the [Adobe Privacy Center](https://www.adobe.com/privacy.html) for more information.

**Comment Audience Manager utilise-t-il les cookies et quels cookies sont-ils définis ?**

See [Audience Manager Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html).

**Les clients Audience Manager aux Etats-Unis peuvent-ils cibler des utilisateurs sur des propriétés européennes ?**

Oui. Audience Manager fonctionne avec les clients qui possèdent des propriétés et des stocks internationaux. L&#39;UE possède des lois de confidentialité strictes, mais Audience Manager dispose de clients qui utilisent des données propriétaires pour le ciblage d&#39;audience en Europe. Audience Manager peut prendre en charge le ciblage des audiences européennes, mais il vous incombe de respecter les réglementations locales sur la confidentialité.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## FAQ sur la rétention des données {#data-retention-faq}

Le tableau suivant répertorie les temps de rétention pour différents types de données et systèmes de stockage.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de données, Source ou Stockage </th> 
   <th colname="col2" class="entry"> Période de conservation des données </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Serveurs dorsaux </p> </td> 
   <td colname="col2"> <p>120 jours. </p> <p> Audience Manager supprime les données utilisateur de nos serveurs dorsaux 120 jours après la dernière consultation d'un utilisateur sur la plate-forme Audience Manager. If <span class="keyword"> Audience Manager</span> records user activity within this 120-day cycle, we will keep this data for another 120-days. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs Edge </p> </td> 
   <td colname="col2"> <p> 14 jours. </p> <p>Audience Manager supprime les données utilisateur de nos serveurs Edge 14 jours après la dernière consultation d'un utilisateur sur la plate-forme Audience Manager. If <span class="keyword"> Audience Manager</span> records user activity in within this 14-day cycle, we will keep this data for another 14-days. Si l'utilisateur revient à nouveau après la période de 14 jours, il y aura un délai entre cette première page vue et le moment où l'utilisateur devient exploitable. Il faut 6 à 18 heures pour rétablir le profil complet au centre du bord après plus de 14 jours d'inactivité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Journaux bruts </p> </td> 
   <td colname="col2"> <p>180 jours (après 180 jours d'aucune activité). </p> <p>Raw logs are data received by an edge server via HTTP calls or from onboarded files sent in to <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Journaux du serveur d'annonces </p> </td> 
   <td colname="col2"> <p><b>Création de rapports</b> </p> <p>Les fichiers journaux sont conservés à des fins de création de rapports pendant 30 jours au maximum. We do not persist unmatched logs (i.e. logs for which there is no ID sync between a visitor's ad server ID and <span class="keyword"> Audience Manager</span> ID) in our backend storage, and matched logs stored in <span class="keyword"> Amazon S3</span> are retained for up to 30 days. </p> <p><b>Fichiers journaux pratiques</b> </p> <p>Les journaux correspondants et non correspondants sont conservés pendant 30 jours au maximum. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profils de niveau CRM (profils authentifiés) </p> </td> 
   <td colname="col2"> <p>L'intervalle de temps à Live (TTL) par défaut pour les profils de niveau CRM inactifs (ID de client) est de 24 mois. Cependant, vous pouvez utiliser l'interface utilisateur d'Audience Manager pour réduire ou étendre l'intervalle TTL des profils de niveau CRM inactifs entre un mois et 5 ans. Vous pouvez y parvenir lors de la création ou de la modification d'une source de données multiterminaux.</p> <p>For more information, see Data Source Settings in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create a Cross-Device Data Source </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de périphérique mobile </p> </td> 
   <td colname="col2"> <p>The retention conditions for mobile device IDs (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) follow the cadence described in the first two rows, back-end servers and edge servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Flux de données client (CDF) </p> </td> 
   <td colname="col2"> <p>A CDF file contains the same data that an <span class="keyword"> Audience Manager</span> event call (/event) sends to our servers. La période de rétention est de 8 jours. For more details about CDF, please refer to <a href="../features/cdf-files.md"> CDF Intro</a> and <a href="../faq/faq-cdf.md"> CDF FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappages entre les identifiants synchronisés </p> </td> 
   <td colname="col2"> <p>Mappings between synchronized IDs may be kept for the life of the associated <a href="../reference/ids-in-aam.md"> Audience Manager Unique User ID (AAM UUID)</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Données entrantes </p> </td> 
   <td colname="col2"> <p>This is inbound data you send to <span class="keyword"> Audience Manager</span> by FTP or directly to an <span class="keyword"> Amazon S3</span> directory. See the <a href="../faq/faq-inbound-data-ingestion.md"> Inbound Customer Data Ingestion FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Données sortantes </p> </td> 
   <td colname="col2"> <p>This is the batch data that <span class="keyword"> Audience Manager</span> sends to third party activation partners. La période de rétention est de 8 jours. For more details about Outbound data, please refer to <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Outbound Batch Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait Qualification Data Retention {#trait-qual}

Le tableau ci-dessous répertorie les options de rétention des caractéristiques de caractéristiques.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opération de caractéristique </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Suppression d'une caractéristique </p> </td> 
   <td colname="col2"> <p>La suppression d'une caractéristique supprime les données de qualification de caractéristique de tous les profils utilisateur qui sont qualifiés pour la caractéristique par le passé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de caractéristiques atteinte </p> </td> 
   <td colname="col2"> <p>Nous imposons une limite de 100 000 caractéristiques pour chaque profil utilisateur. La limite s'applique aux profils authentifiés et aux profils de périphérique. Si un profil utilisateur atteint cette limite, nous supprimerons les critères de caractéristiques les plus anciennes, sur une base initiale, initiale. </p> <p>For more details, read our <a href="../features/traits/trait-qualification-reference.md#trait-qualification-limit"> Trait Qualification Limit</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

