---
description: L’Audience Manager reçoit une quantité énorme de données chaque jour. Cela a une incidence sur le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit comment ces intervalles de temps affectent votre compte d’Audience Manager. En outre, les calendriers et les calendriers décrits ici sont des instructions générales uniquement. Ces plannings ne constituent pas des accords de niveau de service ou des engagements liés à la diffusion de données. Adobe se réserve le droit de modifier les calendriers et les plages horaires à tout moment et sans préavis.
seo-description: L’Audience Manager reçoit une quantité énorme de données chaque jour. Cela a une incidence sur le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit comment ces intervalles de temps affectent votre compte d’Audience Manager. En outre, les calendriers et les calendriers décrits ici sont des instructions générales uniquement. Ces plannings ne constituent pas des accords de niveau de service ou des engagements liés à la diffusion de données. Adobe se réserve le droit de modifier les calendriers et les plages horaires à tout moment et sans préavis.
seo-title: Incidence de la diffusion des données et des délais de traitement des fichiers sur les rapports
solution: Audience Manager
title: Incidence de la diffusion des données et des délais de traitement des fichiers sur les rapports
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: 'Référence '
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 5%

---

# Incidence de la diffusion des données et des délais de traitement des fichiers sur les rapports{#how-data-delivery-and-file-processing-times-affect-reports}

L’Audience Manager reçoit une quantité énorme de données chaque jour. Cela a une incidence sur le temps nécessaire au traitement de vos données et à la génération des résultats des rapports. Le contenu de cette section décrit comment ces intervalles de temps affectent votre compte d’Audience Manager. En outre, les calendriers et les calendriers décrits ici sont des instructions générales uniquement. Ces plannings ne constituent pas des accords de niveau de service ou des engagements liés à la diffusion de données. Adobe se réserve le droit de modifier les calendriers et les plages horaires à tout moment et sans préavis.

## Numéros de création de rapports {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

Le tableau suivant répertorie et décrit les intervalles de temps dans nos rapports généraux et en temps réel.


| Type de données | Description |
|---|---|
| Données en temps réel | Les nombres en temps réel pour aujourd’hui sont de 00:00 à 23:59:59 UTC depuis hier. |
| Données générales du rapport | Les données des [Rapports généraux](../reporting/general-reports.md#general-reports-overview) dépendent de la réussite d’autres processus de tâche et de la quantité de données reçues pour un jour donné. La plupart du temps, les données [!UICONTROL General Report] doivent être mises à jour de 18:00 UTC par jour. |

## Transferts de fichiers entrants et sortants {#inbound-outbound-file-transfers}

[!DNL Audience Manager] traite et envoie les transferts de  [!UICONTROL Server-to-Server (S2S)] fichiers entrants et sortants selon les plannings décrits dans cette section. Compte tenu de ces plannings et des heures limites, il se peut que de nouveaux segments s’affichent entre les nombres de segments en temps réel et total.

| Type de fichier | Description |
|---|---|
| Ingestion de fichiers entrants (données hors ligne) | Le traitement des fichiers est exécuté deux fois par jour. Ces procédures assimilent les données et les préparent pour leur diffusion. Les délais d’envoi des fichiers varient, car ils sont affectés par la quantité totale de données client à traiter. Patientez 48 heures au maximum entre le moment où le fichier est chargé en Audience Manager et le moment où les données sont disponibles pour la création de rapports et l’activation. |
| Fichiers sortants (exports) | Le traitement et l&#39;envoi des fichiers ont lieu une fois par jour, vers 14h00 UTC environ. Gardez à l’esprit que le traitement et la diffusion sont affectés par le nombre total et la taille de ces fichiers. Dans certains cas, le traitement des fichiers peut être retardé pendant 24 heures. Dans ce cas, l’Audience Manager enverra 2 fichiers pour un jour particulier au lieu de 1. Dans les rares cas où l’Audience Manager doit arrêter de traiter un fichier, nous informerons nos clients. Compte tenu de ces conditions, il est difficile d&#39;estimer les délais de remise des données sortantes. Pour déterminer si vous avez reçu un ensemble complet de fichiers, vérifiez l’horodatage et recherchez les jours manquants. Il s’agit d’un horodatage UTC UNIX à 13 chiffres qui enregistre l’heure de création du fichier. Voir [Transferts de données sortantes en temps réel](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Fichiers journaux du serveur publicitaire | Le traitement des fichiers est exécuté en temps quasi réel pour ingérer les enregistrements de fichiers journaux lorsque les fichiers horaires sont prêts. Le processus de préparation des fichiers pour la création de rapports est exécuté une fois par jour. Les délais d’envoi des fichiers varient, car ils sont affectés par la quantité totale de données client à traiter. Vous devez vous attendre à une latence maximale de 48 heures entre le moment où vous chargez le fichier vers l’Audience Manager et le moment où les données sont disponibles pour la création de rapports et l’activation. |

>[!MORELIKETHIS]
>
>* [FAQ sur l’ingestion de données client entrantes](../faq/faq-inbound-data-ingestion.md)

