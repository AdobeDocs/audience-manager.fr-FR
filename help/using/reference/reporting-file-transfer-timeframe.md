---
description: Audience Manager reçoit quotidiennement une quantité importante de données. Cela a une incidence sur le temps nécessaire au traitement de vos données et génère des résultats de rapport. Le contenu de cette section décrit comment ces intervalles de temps affectent votre compte Audience Manager. En outre, les périodes et les planifications décrites ici sont des consignes générales uniquement. Ces planifications ne constituent pas des contrats de niveau service (SLAS) ou des engagements liés à la remise des données. Adobe se réserve le droit de modifier les périodes et les planifications à tout moment sans préavis.
seo-description: Audience Manager reçoit quotidiennement une quantité importante de données. Cela a une incidence sur le temps nécessaire au traitement de vos données et génère des résultats de rapport. Le contenu de cette section décrit comment ces intervalles de temps affectent votre compte Audience Manager. En outre, les périodes et les planifications décrites ici sont des consignes générales uniquement. Ces planifications ne constituent pas des contrats de niveau service (SLAS) ou des engagements liés à la remise des données. Adobe se réserve le droit de modifier les périodes et les planifications à tout moment sans préavis.
seo-title: Impact des rapports Envoi de données et Traitement des fichiers sur les rapports
solution: Audience Manager
title: Impact des rapports Envoi de données et Traitement des fichiers sur les rapports
uuid: 4 b 975512-f 67 e -4749-a 7 ef -168415597682
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# How Data Delivery and File Processing Times Affect Reports{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager reçoit quotidiennement une quantité importante de données. Cela a une incidence sur le temps nécessaire au traitement de vos données et génère des résultats de rapport. Le contenu de cette section décrit comment ces intervalles de temps affectent votre compte Audience Manager. En outre, les périodes et les planifications décrites ici sont des consignes générales uniquement. Ces planifications ne constituent pas des contrats de niveau service (SLAS) ou des engagements liés à la remise des données. Adobe se réserve le droit de modifier les périodes et les planifications à tout moment sans préavis.

## Reporting Numbers {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

Le tableau suivant répertorie et décrit les intervalles de temps dans nos rapports généraux et en temps réel.

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de données </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Réel - Données temporelles</b> </p> </td> 
   <td colname="col2"> <p> Les nombres en temps réel pour aujourd'hui sont pour les heures 00:00 à 23:59:59 UTC depuis hier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Données générales du rapport</b> </p> </td> 
   <td colname="col2"> <p>The data in the <a href="../reporting/general-reports.md#general-reports-overview"> General Reports</a> depends on the successful completion of other job processes and the amount of data received for a particular day. Most of the time, <span class="wintitle"> General Report</span> data should be updated by 18:00 UTC each day. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Inbound and Outbound File Transfers {#inbound-outbound-file-transfers}

[!DNL Audience Manager] traite et envoie des transferts [!UICONTROL Server-to-Server (S2S)] de fichiers entrants et sortants conformément aux planifications décrites dans cette section. Étant donné ces calendriers et les heures de coupure, il se peut que des incohérences avec les nouveaux segments entre les nombres de segments en temps réel et total.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Ingestion du fichier entrant (données hors ligne)</b> </p> </td> 
   <td colname="col2"> <p>Le traitement du fichier est exécuté deux fois par jour. Ces procédures assimilent des données et les préparent pour livraison. </p> <p>Les délais de remise des fichiers varient car ils sont affectés par la quantité totale de données client qui doivent être traitées. You should expect a maximum latency of 48 hours between the moment the file is uploaded in <span class="keyword"> Audience Manager</span> and until the data is available for reporting and activation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Fichiers sortants (Exporter)</b> </p> </td> 
   <td colname="col2"> <p>Le traitement et la diffusion des fichiers ont lieu une fois par jour, à environ 14:00 UTC. Gardez à l'esprit que le traitement et la diffusion sont affectés par le nombre total et la taille de ces fichiers. Dans certains cas, le traitement des fichiers peut différer pendant 24 heures. When this happens, <span class="keyword"> Audience Manager</span> will send 2 files for a particular day instead of 1. We will notify our customers in the rare case where <span class="keyword"> Audience Manager</span> has to stop processing a file altogether. Dans ces conditions, il est difficile d'estimer les délais de remise pour les données sortantes. </p> <p>Pour déterminer si vous avez reçu un ensemble complet de fichiers, vérifiez l'horodatage et recherchez les jours manquants. Il s'agit d'un horodatage UNIX UTC à 13 chiffres qui enregistre l'heure à laquelle le fichier a été créé. See <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> Real-Time Outbound Data Transfers</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [FAQ sur l&#39;assimilation des données client inbound](../faq/faq-inbound-data-ingestion.md)

