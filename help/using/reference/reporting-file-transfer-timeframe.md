---
description: Audience Manager reçoit une quantité énorme de données chaque jour. Cela affecte le temps nécessaire au traitement des données et à la génération des résultats du rapport. Le contenu de cette section décrit l’impact de ces intervalles de temps sur votre compte Audience Manager. De plus, les échéanciers et les calendriers décrits ici ne sont que des lignes directrices générales. Ces calendriers ne constituent pas des accords de niveau de service (SLA) ou des engagements liés à la diffusion des données. Adobe se réserve le droit de modifier les délais et horaires à tout moment et sans préavis.
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: Impact des délais de diffusion des données et de traitement des fichiers sur les rapports
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 1%

---

# Impact des délais de diffusion des données et de traitement des fichiers sur les rapports{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager reçoit une quantité énorme de données chaque jour. Cela affecte le temps nécessaire au traitement des données et à la génération des résultats du rapport. Le contenu de cette section décrit l’impact de ces intervalles de temps sur votre compte Audience Manager. De plus, les échéanciers et les calendriers décrits ici ne sont que des lignes directrices générales. Ces calendriers ne constituent pas des accords de niveau de service (SLA) ou des engagements liés à la diffusion des données. Adobe se réserve le droit de modifier les délais et horaires à tout moment et sans préavis.

## Numéros de reporting {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

Le tableau suivant répertorie et décrit les intervalles de temps dans nos rapports généraux et en temps réel.


| Type de données | Description |
|---|---|
| Données En Temps Réel | Les nombres en temps réel pour aujourd’hui correspondent aux heures comprises entre 00 :00 et 23:59:59 UTC par rapport à hier. |
| Données générales du rapport | Les données contenues dans les [Rapports généraux](../reporting/general-reports.md#general-reports-overview) dépendent de la réussite d’autres processus de traitement et de la quantité de données reçues pour un jour donné. La plupart du temps, [!UICONTROL General Report] données doivent être mises à jour à 18 :00 UTC par jour. |

## Transferts de fichiers entrants et sortants {#inbound-outbound-file-transfers}

[!DNL Audience Manager] traite et envoie les transferts de fichiers [!UICONTROL Server-to-Server (S2S)] entrants et sortants selon les plannings décrits dans cette section. Compte tenu de ces planifications et des heures limites, vous pouvez voir des incohérences avec les nouveaux segments entre les numéros de segment en temps réel et total.

| Type de fichier | Description |
|---|---|
| Ingestion de fichiers entrants (données hors ligne) | Le traitement des fichiers est exécuté deux fois par jour. Ces procédures ingèrent des données et les préparent pour la diffusion. Les délais de livraison des fichiers varient car ils sont affectés par la quantité totale de données client qui doit être traitée. Vous devez vous attendre à une latence maximale de 48 heures entre le moment où le fichier est chargé dans Audience Manager et le moment où les données sont disponibles pour le compte rendu des performances et l’activation. |
| Fichiers sortants (d’exportation) | Le traitement et la livraison des fichiers ont lieu une fois par jour, à environ 14 :00 UTC. Gardez à l’esprit que le traitement et la diffusion sont affectés par le nombre et la taille totaux de ces fichiers. Dans certains cas, le traitement des fichiers peut être retardé jusqu’à 24 heures. Dans ce cas, Audience Manager envoie 2 fichiers pour un jour donné au lieu de 1. Nous avertirons nos clients dans les rares cas où Audience Manager doit arrêter complètement le traitement d’un fichier. Dans ces conditions, il est difficile d&#39;estimer les délais de livraison des données sortantes. Pour déterminer si vous avez reçu un ensemble complet de fichiers, vérifiez l’horodatage et recherchez les jours manquants. Il s’agit d’un horodatage UTC UNIX à 13 chiffres qui enregistre l’heure de création du fichier. Voir [Transferts De Données Sortantes En Temps Réel](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Fichiers journaux du serveur de publicités | Le traitement des fichiers est exécuté en temps quasi réel pour ingérer les enregistrements de fichiers journaux lorsque les fichiers horaires sont prêts. Le processus de préparation des fichiers pour le compte rendu des performances est exécuté une fois par jour. Les délais de livraison des fichiers varient car ils sont affectés par la quantité totale de données client qui doit être traitée. Vous devez vous attendre à une latence maximale de 48 heures entre le moment où vous chargez le fichier vers Audience Manager et le moment où les données sont disponibles pour la création de rapports et l’activation. |

>[!MORELIKETHIS]
>
>* [FAQ sur l’ingestion de données client entrantes](../faq/faq-inbound-data-ingestion.md)
