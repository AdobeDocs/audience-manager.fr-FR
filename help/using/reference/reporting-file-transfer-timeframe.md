---
description: L'Audience Manager reçoit chaque jour une quantité énorme de données. Cela affecte le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit comment ces intervalles de temps affectent votre compte d’Audience Manager. En outre, les échéanciers et les calendriers décrits ici ne sont que des directives générales. Ces calendriers ne constituent pas des accords de niveau de service ou des engagements liés à la diffusion de données. Adobe se réserve le droit de modifier les calendriers et les calendriers à tout moment sans préavis.
seo-description: L'Audience Manager reçoit chaque jour une quantité énorme de données. Cela affecte le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit comment ces intervalles de temps affectent votre compte d’Audience Manager. En outre, les échéanciers et les calendriers décrits ici ne sont que des directives générales. Ces calendriers ne constituent pas des accords de niveau de service ou des engagements liés à la diffusion de données. Adobe se réserve le droit de modifier les calendriers et les calendriers à tout moment sans préavis.
seo-title: Incidence de la diffusion des données et des délais de traitement des fichiers sur les rapports
solution: Audience Manager
title: Incidence de la diffusion des données et des délais de traitement des fichiers sur les rapports
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 5%

---


# Incidence de la diffusion des données et des délais de traitement des fichiers sur les rapports{#how-data-delivery-and-file-processing-times-affect-reports}

L&#39;Audience Manager reçoit chaque jour une quantité énorme de données. Cela affecte le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit comment ces intervalles de temps affectent votre compte d’Audience Manager. En outre, les échéanciers et les calendriers décrits ici ne sont que des directives générales. Ces calendriers ne constituent pas des accords de niveau de service ou des engagements liés à la diffusion de données. Adobe se réserve le droit de modifier les calendriers et les calendriers à tout moment sans préavis.

## Numéros de Rapports {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

Le tableau suivant liste et décrit les intervalles de temps dans nos rapports généraux et en temps réel.


| Type de données | Description |
|---|---|
| Données en temps réel | Les nombres en temps réel pour aujourd&#39;hui sont pour les heures 00:00 à 23:59:59 UTC d&#39;hier. |
| Données générales du rapport | Les données des rapports [](../reporting/general-reports.md#general-reports-overview) généraux dépendent de la réussite d&#39;autres processus d&#39;emploi et de la quantité de données reçues pour une journée donnée. La plupart du temps, [!UICONTROL General Report] les données doivent être mises à jour à 18h00 UTC chaque jour. |

## Transferts de fichiers entrants et sortants {#inbound-outbound-file-transfers}

[!DNL Audience Manager] traite et envoie les transferts de [!UICONTROL Server-to-Server (S2S)] fichiers entrants et sortants conformément aux planifications décrites dans cette section. Compte tenu de ces planifications et des heures limites, il se peut que de nouveaux segments s’affichent entre les numéros de segment en temps réel et le nombre total de segments.

| Type de fichier | Description |
|---|---|
| Envoi d&#39;un fichier entrant par importation (données hors ligne) | Le traitement des fichiers est exécuté deux fois par jour. Ces procédures assimilent les données et les préparent à la diffusion. Les durées de diffusion des fichiers varient car elles sont affectées par la quantité totale de données client à traiter. Vous devez vous attendre à une latence maximale de 48 heures entre le moment où le fichier est téléchargé en Audience Manager et jusqu’à ce que les données soient disponibles pour le rapports et l’activation. |
| Fichiers sortants (exportation) | Le traitement des dossiers et la diffusion ont lieu une fois par jour, vers 14h00 UTC. N’oubliez pas que le traitement et la diffusion sont affectés par le nombre total et la taille de ces fichiers. Dans certains cas, le traitement des fichiers peut être retardé jusqu&#39;à 24 heures. Dans ce cas, l&#39;Audience Manager enverra 2 fichiers pour un jour donné au lieu de 1. Nous informerons nos clients dans les rares cas où l&#39;Audience Manager doit arrêter de traiter un fichier. Compte tenu de ces conditions, il est difficile d&#39;estimer le temps de diffusion des données sortantes. Pour déterminer si vous avez reçu un ensemble complet de fichiers, vérifiez l’horodatage et recherchez les jours manquants. Il s’agit d’un horodatage UTC UNIX à 13 chiffres qui enregistre l’heure de création du fichier. See [Real-Time Outbound Data Transfers](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Fichiers journaux du serveur d’annonces | Le traitement des fichiers est exécuté en temps quasi réel afin d’assimiler les enregistrements de fichiers journaux lorsque les fichiers horaires sont prêts. Le processus de préparation des fichiers pour le rapports est exécuté une fois par jour. Les durées de diffusion des fichiers varient car elles sont affectées par la quantité totale de données client à traiter. Vous devez vous attendre à une latence maximale de 48 heures entre le moment où vous téléchargez le fichier vers l’Audience Manager et le moment où les données sont disponibles pour le rapports et l’activation. |

>[!MORELIKETHIS]
>
>* [FAQ sur l’ingestion de données client entrantes](../faq/faq-inbound-data-ingestion.md)

