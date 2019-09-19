---
description: Audience Manager reçoit chaque jour une quantité énorme de données. Cela affecte le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit l’impact de ces intervalles de temps sur votre compte Audience Manager. De plus, les délais et les calendriers décrits ici ne sont que des directives générales. Ces calendriers ne constituent pas des ententes de niveau de service (SLA) ni des engagements liés à la remise des données. Adobe se réserve le droit de modifier les calendriers et les calendriers à tout moment sans préavis.
seo-description: Audience Manager reçoit chaque jour une quantité énorme de données. Cela affecte le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit l’impact de ces intervalles de temps sur votre compte Audience Manager. De plus, les délais et les calendriers décrits ici ne sont que des directives générales. Ces calendriers ne constituent pas des ententes de niveau de service (SLA) ni des engagements liés à la remise des données. Adobe se réserve le droit de modifier les calendriers et les calendriers à tout moment sans préavis.
seo-title: ' Incidence des délais de remise des données et de traitement des fichiers sur les rapports'
solution: Audience Manager
title: ' Incidence des délais de remise des données et de traitement des fichiers sur les rapports'
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


#  Incidence des délais de remise des données et de traitement des fichiers sur les rapports{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager reçoit chaque jour une quantité énorme de données. Cela affecte le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit l’impact de ces intervalles de temps sur votre compte Audience Manager. De plus, les délais et les calendriers décrits ici ne sont que des directives générales. Ces calendriers ne constituent pas des ententes de niveau de service (SLA) ni des engagements liés à la remise des données. Adobe se réserve le droit de modifier les calendriers et les calendriers à tout moment sans préavis.

## Nombres de création de rapports {#reporting-numbers}

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
   <td colname="col1"> <p> <b>Données en temps réel</b> </p> </td> 
   <td colname="col2"> <p> Les nombres en temps réel pour aujourd'hui sont pour les heures 00:00 à 23:59:59 UTC d'hier. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Données générales Du Rapport</b> </p> </td> 
   <td colname="col2"> <p>Les données contenues dans les rapports <a href="../reporting/general-reports.md#general-reports-overview"></a> généraux dépendent de la réussite d’autres processus de travail et de la quantité de données reçues pour une journée donnée. La plupart du temps, les données du rapport <span class="wintitle"></span> général doivent être mises à jour d’ici 18 h 00 UTC chaque jour. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Transferts de fichiers entrants et sortants {#inbound-outbound-file-transfers}

[!DNL Audience Manager] traite et envoie les transferts de [!UICONTROL Server-to-Server (S2S)] fichiers entrants et sortants conformément aux calendriers décrits dans cette section. Compte tenu de ces planifications et des heures de coupure, il se peut que les nouveaux segments soient incohérents entre les nombres de segments en temps réel et total.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type de fichier </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Ingestion des fichiers entrants (données hors ligne)</b> </p> </td> 
   <td colname="col2"> <p>Le traitement des fichiers est exécuté deux fois par jour. Ces procédures assimilent les données et les préparent à leur remise. </p> <p>Les délais de livraison des fichiers varient car ils sont affectés par la quantité totale de données client à traiter. Vous devez vous attendre à une latence maximale de 48 heures entre le moment où le fichier est téléchargé dans <span class="keyword"> Audience Manager</span> et jusqu’à ce que les données soient disponibles pour la création de rapports et l’activation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Fichiers sortants (Exportation)</b> </p> </td> 
   <td colname="col2"> <p>Le traitement et la livraison des dossiers ont lieu une fois par jour, vers 14h00 UTC. Gardez à l’esprit que le traitement et la remise sont affectés par le nombre total et la taille de ces fichiers. Dans certains cas, le traitement des fichiers peut être retardé de 24 heures. Dans ce cas, <span class="keyword"> Audience Manager</span> enverra 2 fichiers pour un jour donné au lieu de 1. Dans les rares cas où <span class="keyword"> Audience Manager</span> doit cesser de traiter un fichier, nous en informerons nos clients. Compte tenu de ces conditions, il est difficile d’estimer les délais de livraison des données sortantes. </p> <p>Pour déterminer si vous avez reçu un ensemble complet de fichiers, vérifiez l’horodatage et recherchez les jours manquants. Il s’agit d’un horodatage UTC UNIX à 13 chiffres qui enregistre l’heure de création du fichier. Voir Transferts <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> de données sortants en temps</a>réel. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_This]
>
>* [FAQ sur l'introduction des données client entrantes](../faq/faq-inbound-data-ingestion.md)

