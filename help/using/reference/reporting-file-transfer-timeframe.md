---
description: ' Gestionnaire de reçoit chaque jour une énorme quantité de données. Cela affecte le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit l’impact de ces intervalles de temps sur votre compte  Gestionnaire de  de. De plus, les délais et les calendriers décrits ici ne sont que des directives générales. Ces calendriers ne constituent pas des ententes de niveau de service (SLA) ni des engagements liés aux  de données. Adobe se réserve le droit de modifier les calendriers et les calendriers à tout moment sans préavis.'
seo-description: ' Gestionnaire de reçoit chaque jour une énorme quantité de données. Cela affecte le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit l’impact de ces intervalles de temps sur votre compte  Gestionnaire de  de. De plus, les délais et les calendriers décrits ici ne sont que des directives générales. Ces calendriers ne constituent pas des ententes de niveau de service (SLA) ni des engagements liés aux  de données. Adobe se réserve le droit de modifier les calendriers et les calendriers à tout moment sans préavis.'
seo-title: Incidence des  de données et des temps de traitement des fichiers sur les rapports
solution: Audience Manager
title: Incidence des  de données et des temps de traitement des fichiers sur les rapports
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: 6bdf79b17ec96ed0d54ed97ab5d69fadb68763b5

---


# Incidence des  de données et des temps de traitement des fichiers sur les rapports{#how-data-delivery-and-file-processing-times-affect-reports}

 Gestionnaire de reçoit chaque jour une énorme quantité de données. Cela affecte le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit l’impact de ces intervalles de temps sur votre compte  Gestionnaire de  de. De plus, les délais et les calendriers décrits ici ne sont que des directives générales. Ces calendriers ne constituent pas des ententes de niveau de service (SLA) ni des engagements liés aux  de données. Adobe se réserve le droit de modifier les calendriers et les calendriers à tout moment sans préavis.

## Nombre de {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

Le tableau ci-dessous  et décrit les intervalles de temps dans nos rapports généraux et en temps réel.


| Type de données | Description |
|---|---|
| Données en temps réel | Les nombres en temps réel pour aujourd&#39;hui sont pour les heures 00:00 à 23:59:59 UTC d&#39;hier. |
| Données générales Du Rapport | Les données contenues dans les rapports [](../reporting/general-reports.md#general-reports-overview) généraux dépendent de la réussite d’autres processus d’emploi et de la quantité de données reçues pour une journée donnée. La plupart du temps, [!UICONTROL General Report] les données doivent être mises à jour à 18h00 UTC chaque jour. |

## Transferts de fichiers entrants et sortants {#inbound-outbound-file-transfers}

[!DNL Audience Manager] traite et envoie les transferts de [!UICONTROL Server-to-Server (S2S)] fichiers entrants et sortants conformément aux calendriers décrits dans cette section. Compte tenu de ces planifications et des heures de coupure, il se peut que les nouveaux segments soient incohérents entre les numéros de segment en temps réel et le nombre total de segments.

| Type de fichier | Description |
|---|---|
| Ingestion des fichiers entrants (données hors ligne) | Le traitement des fichiers est exécuté deux fois par jour. Ces procédures assimilent les données et les préparent pour les . Les heures de  des fichiers varient car elles sont affectées par la quantité totale de données client à traiter. Vous devez vous attendre à une latence maximale de 48 heures entre le moment où le fichier est téléchargé dans  Gestionnaire de  de et jusqu’à ce que les données soient disponibles pour les et les. |
| Fichiers sortants (Exportation) | Le traitement des dossiers et les  ont lieu une fois par jour, vers 14h00 UTC. N’oubliez pas que le traitement et les  de sont affectés par le nombre total et la taille de ces fichiers. Dans certains cas, le traitement des fichiers peut être retardé jusqu’à 24 heures. Dans ce cas,  Gestionnaire de  enverra 2 fichiers pour un jour donné au lieu de 1. Nous avertirons nos clients dans les rares cas où  Gestionnaire  doit cesser de traiter un fichier. Compte tenu de ces conditions, il est difficile d’estimer  temps de pour les données sortantes. Pour déterminer si vous avez reçu un ensemble complet de fichiers, vérifiez l’horodatage et recherchez les jours manquants. Il s’agit d’un horodatage UTC UNIX à 13 chiffres qui enregistre l’heure de création du fichier. Voir Transferts [de données sortants en temps](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md)réel. |
| Fichiers journaux du serveur d’annonces | Le traitement des fichiers est exécuté en temps quasi réel pour importer les enregistrements de fichiers journaux, les fichiers horaires étant prêts. Le processus de préparation des fichiers pour les  de est exécuté une fois par jour. Les heures de  des fichiers varient car elles sont affectées par la quantité totale de données client à traiter. Vous devez vous attendre à une latence maximale de 48 heures entre le moment où vous téléchargez le fichier vers  Gestionnaire de  de et le moment où les données sont disponibles pour les de la  et du. |

>[!MORELIKETHIS]
>
>* [FAQ sur l&#39;introduction des données client entrantes](../faq/faq-inbound-data-ingestion.md)

