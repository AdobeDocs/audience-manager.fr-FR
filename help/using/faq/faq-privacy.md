---
description: Réponses aux questions et problématiques courantes concernant la confidentialité des données.
seo-description: Réponses aux questions et problématiques courantes concernant la confidentialité des données.
seo-title: FAQ sur la rétention des données et la confidentialité
solution: Audience Manager
title: FAQ sur la rétention des données et la confidentialité
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: Data Governance and Privacy
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# FAQ sur la rétention des données et la confidentialité {#privacy-and-data-retention-faq}

Réponses aux questions et problématiques courantes concernant la confidentialité des données.

<!-- faq_privacy.xml -->

## FAQ sur la confidentialité {#privacy-faq}

>[!TIP]
>
>Pour plus d’informations, consultez le [Centre de traitement des données personnelles Adobe](https://www.adobe.com/fr/privacy.html).

**De quelle manière Audience Manager utilise-t-il les cookies, et quels cookies définit-il ?**

Voir [Cookies d’Audience Manager](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-am.html).

**Les clients d’Audience Manager situés aux États-Unis peuvent-ils cibler les utilisateurs de propriétés européennes ?**

Oui. Audience Manager travaille avec des clients possédant des propriétés ainsi qu’un inventaire internationaux. Les lois européennes portant sur la confidentialité sont strictes, mais certains clients d’Audience Manager utilisent des données propriétaires pour cibler des audiences en Europe. Audience Manager peut prendre en charge le ciblage des audiences européennes, mais il relève de votre responsabilité de respecter les réglementations locales en matière de confidentialité.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## FAQ sur la rétention des données {#data-retention-faq}

Le tableau suivant répertorie les temps de rétention pour différents types de données et systèmes de stockage.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type, source ou stockage des données </th> 
   <th colname="col2" class="entry"> Période de rétention des données </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Serveurs principaux </p> </td> 
   <td colname="col2"> <p>120 jours. </p> <p> Audience Manager supprime les données utilisateur de nos serveurs principaux 120 jours après la dernière visite d’un utilisateur sur la plateforme Audience Manager. Si <span class="keyword"> Audience Manager</span> enregistre une activité utilisateur au cours de ce cycle de 120 jours, nous conserverons ces données pendant 120 jours supplémentaires. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Serveurs Edge </p> </td> 
   <td colname="col2"> <p> 14 jours. </p> <p>Audience Manager supprime les données utilisateur de nos serveurs Edge 14 jours après la dernière visite d’un utilisateur sur la plateforme Audience Manager. Si <span class="keyword"> Audience Manager</span> enregistre une activité utilisateur au cours de ce cycle de 14 jours, nous conserverons ces données pendant 14 jours supplémentaires. Si l’utilisateur est de nouveau actif après la période de 14 jours, un délai s’écoulera entre cette première nouvelle visite de page et le moment où l’utilisateur deviendra exploitable. Il faut entre 6 et 18 heures pour que le profil complet soit réintégré au centre Edge après plus de 14 jours d’inactivité. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Journaux bruts </p> </td> 
   <td colname="col2"> <p>180 jours (retirés après 180 jours sans activité). </p> <p>Les journaux bruts sont des données reçues par un serveur Edge au moyen d’appels HTTP ou à partir de fichiers intégrés envoyés à <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Journaux du serveur de publicités </p> </td> 
   <td colname="col2"> <p><b>Création de rapports</b> </p> <p>Les fichiers journaux sont conservés à des fins de création de rapports pendant un maximum de 30 jours. Nous ne conservons pas les journaux sans correspondance (c.-à-d. les journaux pour lesquels il n’existe aucune synchronisation d’identifiant entre un identifiant de serveur de publicités d’un visiteur et un identifiant <span class="keyword">Audience Manager</span>) dans notre serveur principal de stockage, et les journaux mis en correspondance stockés dans <span class="keyword">Amazon S3</span> sont conservés pendant un maximum de 30 jours. </p> <p><b>Fichiers journaux pratiques</b> </p> <p>Les journaux avec ou sans correspondance sont conservés pendant un maximum de 30 jours. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profils au niveau CRM (profils authentifiés) </p> </td> 
   <td colname="col2"> <p>La durée de vie par défaut des profils au niveau CRM (identifiants client) inactifs est de 24 mois. Cependant, vous pouvez utiliser l’interface utilisateur de l’Audience Manager pour réduire ou étendre l’intervalle TTL pour les profils inactifs au niveau de la gestion de la relation client entre un mois et 5 ans. Pour ce faire, vous pouvez créer ou modifier une source de données multi-appareils.</p> <p>Pour plus d’informations, voir les paramètres de source de données dans la <a href="../features/profile-merge-rules/merge-rules-start.md#settings">création d’une source de données multi-appareils</a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identifiants d’appareil mobile </p> </td> 
   <td colname="col2"> <p>Les conditions de rétention des identifiants d’appareil mobile (<a href="../reference/ids-in-aam.md">IDFA, GAID</a>) suivent le circuit décrit dans les deux premières lignes, les serveurs principaux et les serveurs Edge. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Flux de données client (CDF) </p> </td> 
   <td colname="col2"> <p>Un fichier CDF contient les mêmes données que celles envoyées à nos serveurs par un appel d’événement (/event) <span class="keyword">Audience Manager</span>. La période de rétention est de 8 jours. Pour plus d’informations sur le flux de données client, consultez la <a href="../features/cdf-files.md">présentation du flux de données client</a> et la <a href="../faq/faq-cdf.md">FAQ sur le flux de données client</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mappages entre des identifiants synchronisés </p> </td> 
   <td colname="col2"> <p>La durée de vie des <a href="../features/administration/usage-limits.md#id-mapping-limits">mappages d’identifiants</a> entre les identifiants de cookie Audience Manager (<a href="../reference/ids-in-aam.md">identifiants utilisateur uniques d’Audience Manager ou UUID AAM</a>) et les identifiants de cookie tiers est limitée à 120 jours. La durée de vie du mappage des identifiants est réinitialisée chaque fois que le cookie Audience Manager est détecté sur le réseau Audience Manager. La synchronisation du mappage des identifiants la plus récente sera conservée pendant la durée de vie de l’<a href="../reference/ids-in-aam.md">identifiant utilisateur unique Audience Manager (UUID AAM)</a> associé.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Données entrantes </p> </td> 
   <td colname="col2"> <p>Il s’agit des données entrantes que vous envoyez à <span class="keyword">Audience Manager</span> par FTP ou directement vers un répertoire <span class="keyword">Amazon S3</span>. Voir <a href="../faq/faq-inbound-data-ingestion.md">FAQ sur l’ingestion de données client entrantes</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Données sortantes </p> </td> 
   <td colname="col2"> <p>Il s’agit des données par lots qu’envoie <span class="keyword">Audience Manager</span> aux partenaires d’activation tiers. La période de rétention est de 8 jours. Pour plus d’informations sur les données sortantes, reportez-vous aux <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">transferts sortants par lots</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Rétention des données de qualification de caractéristiques {#trait-qual}

Le tableau ci-dessous répertorie les options de rétention pour les qualifications de caractéristiques.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opération sur caractéristique </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Suppression d’une caractéristique </p> </td> 
   <td colname="col2"> <p>La suppression d’une caractéristique retire les données de qualification de caractéristiques de tous les profils utilisateur qui s’étaient qualifiés pour cette caractéristique dans le passé. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite de caractéristiques atteinte </p> </td> 
   <td colname="col2"> <p>Chaque profil d’utilisateur peut se qualifier pour un maximum de 100 000 caractéristiques. Cette limite s’applique aux profils authentifiés et aux profils d’appareils. Si un profil utilisateur atteint cette limite, nous supprimerons les qualifications de caractéristiques les plus anciennes, selon la méthode du premier entré, premier sorti. </p> <p>Pour plus d’informations, reportez-vous à notre <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit">limite de qualification de caractéristiques</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

