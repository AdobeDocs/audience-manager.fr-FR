---
description: Vers le 14 octobre 2019, j’ai remarqué que mes populations de caractéristiques intégrées du graphique d’identifiant de l’appareil sont tombées à 0, alors qu’elles étaient beaucoup plus élevées auparavant.
seo-description: Vers le 14 octobre 2019, j’ai remarqué que mes populations de caractéristiques intégrées du graphique d’identifiant de l’appareil sont tombées à 0, alors qu’elles étaient beaucoup plus élevées auparavant.
seo-title: Pourquoi mes populations de caractéristiques intégrées sont-elles tombées à 0 aux alentours du 15 octobre ?
solution: Audience Manager
title: Pourquoi mes populations de caractéristiques intégrées sont-elles tombées à 0 aux alentours du 15 octobre ?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 100%

---


# Pourquoi mes populations de caractéristiques intégrées sont-elles tombées à 0 aux alentours du 15 octobre ? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Question

Vers le 14 octobre 2019, j’ai remarqué que mes populations de caractéristiques intégrées du graphique d’identifiant de l’appareil sont tombées à 0, alors qu’elles étaient beaucoup plus élevées auparavant. Comment est-ce arrivé ?

![Image de la chute de l’identifiant de l’appareil](assets/device_id_populationdrop.png)

## Réponse

Le 15 octobre, une mise à jour de la fonctionnalité de stratégie de fusion de profils d’Audience Manager a été modifiée de manière à ce que les données intégrées saisies à partir d’un identifiant de gestion de la relation client chargé sur une source de données multi-appareils ne soient plus réalisées par rapport aux identifiants d’appareil.  Auparavant, Audience Manager effectuait une réalisation par rapport à un identifiant multi-appareils (ou un identifiant de gestion de la relation client) et copiait ces réalisations sur les UUID d’Audience Manager associés (identifiants d’appareil).  Ce changement a été apporté afin de refléter plus précisément la nature des caractéristiques des données et des profils réalisés.

Pour afficher les réalisations de caractéristiques, sélectionnez l’option « Identifiant multi-appareils » dans la liste déroulante située dans le coin supérieur droit de l’affichage des caractéristiques.

![Affichage des réalisations par identifiant multi-appareils](assets/deviceid-crossdevice.png)