---
description: Réponses aux questions et problématiques courantes concernant la confidentialité des données.
seo-description: Réponses aux questions et problématiques courantes concernant la confidentialité des données.
seo-title: FAQ sur la confidentialité et la rétention des données
solution: Audience Manager
title: FAQ sur la confidentialité et la rétention des données
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

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
   <td colname="col2"> <p>120 jours. </p> <p> Audience Manager supprime les données utilisateur de nos serveurs principaux 120 jours après la dernière visite d’un utilisateur sur la plateforme Audience Manager. Si <span class="keyword"> Audience Manager</span> enregistre l’activité de l’utilisateur au cours de ce cycle de 120 jours, nous conservons ces données pendant encore 120 jours. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs Edge </p> </td> 
   <td colname="col2"> <p> 14 jours. </p> <p>Audience Manager supprime les données utilisateur de nos serveurs Edge 14 jours après la dernière visite d’un utilisateur sur la plateforme Audience Manager. Si <span class="keyword"> Audience Manager</span> enregistre l’activité de l’utilisateur au cours de ce cycle de 14 jours, nous conservons ces données pendant encore 14 jours. Si l’utilisateur devient actif à nouveau après la période de 14 jours, un délai s’écoulera entre cette première nouvelle page vue et le moment où l’utilisateur pourra agir. Il faut de 6 à 18 heures pour que le profil complet soit remis au centre du bord après plus de 14 jours d'inactivité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Journaux bruts </p> </td> 
   <td colname="col2"> <p>180 jours (supprimé après 180 jours sans activité). </p> <p>Les journaux bruts sont des données reçues par un serveur Edge via des appels HTTP ou à partir de fichiers intégrés envoyés à <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Journaux du serveur d’annonces publicitaires </p> </td> 
   <td colname="col2"> <p><b>Création de rapports</b> </p> <p>Les fichiers journaux sont conservés pour la création de rapports pendant 30 jours au maximum. Nous ne conservons pas les journaux non concordants (c’est-à-dire les journaux pour lesquels il n’existe aucune synchronisation d’ID entre l’ID du serveur d’annonces d’un visiteur et l’ID Audience Manager <span class="keyword"> ) dans notre stockage principal. Les journaux correspondants stockés dans</span> Amazon S3 <span class="keyword"></span> sont conservés pendant 30 jours au maximum. </p> <p><b>Fichiers journaux pratiques</b> </p> <p>Les journaux correspondants et non correspondants sont conservés pendant 30 jours au maximum. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profils au niveau CRM (profils authentifiés) </p> </td> 
   <td colname="col2"> <p>L’intervalle de temps de vie (TTL) par défaut pour les profils CRM inactifs (ID de client) est de 24 mois. Vous pouvez toutefois utiliser l’interface utilisateur d’Audience Manager pour réduire ou étendre l’intervalle TTL pour les profils CRM inactifs d’un mois à 5 ans. Vous pouvez y parvenir lors de la création ou de la modification d’une source de données sur plusieurs périphériques.</p> <p>Pour plus d’informations, voir Paramètres de source de données dans <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Création d’une source de données multiterminaux </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de périphérique mobile </p> </td> 
   <td colname="col2"> <p>Les conditions de rétention des ID de périphérique mobile (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) suivent la cadence décrite dans les deux premières lignes, les serveurs principaux et les serveurs Edge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Flux de données client (CDF) </p> </td> 
   <td colname="col2"> <p>Un fichier CDF contient les mêmes données qu’un appel d’événement <span class="keyword"> Audience Manager</span> (/event) envoie à nos serveurs. La période de rétention est de 8 jours. Pour plus d'informations sur CDF, veuillez consulter les FAQ <a href="../features/cdf-files.md"> Intro</a> et <a href="../faq/faq-cdf.md"></a>CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappages entre ID synchronisés </p> </td> 
   <td colname="col2"> <p>Les mappages entre les ID synchronisés peuvent être conservés pendant la durée de vie de l’ID utilisateur unique d’Audience Manager associé (UUID AAM) <a href="../reference/ids-in-aam.md"></a>. </p> </td> 
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

