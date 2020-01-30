---
description: Cette page comprend les principaux problèmes signalés au service à la clientèle d’Audience Manager.
seo-description: Cette page comprend les principaux problèmes signalés au service à la clientèle d’Audience Manager.
seo-title: Assistance clientèle - Problèmes les plus fréquemment signalés
solution: Audience Manager
title: Assistance clientèle - Problèmes les plus fréquemment signalés
translation-type: tm+mt
source-git-commit: f9d57da86b7e8962353b01b693a2359cade7b024

---


# Assistance clientèle - Problèmes les plus fréquemment signalés{#most-frequent-issues}

Cette page comprend les principaux problèmes signalés au service à la clientèle d’Audience Manager en 2019.

## Pourquoi nos utilisateurs en lecture seule peuvent-ils créer, modifier ou supprimer des caractéristiques et des segments ?

**Question**

Pourquoi nos utilisateurs en lecture seule peuvent-ils créer, modifier ou supprimer des caractéristiques et des segments ?

**Réponse**

Outre la création de groupes et d’autorisations dans la section Administration, vous devez contacter le service d’assistance clientèle (amsupport@adobe.com) afin qu’un représentant puisse activer les RBAC (Role Based Access Controls) pour votre compte.

<br> 

## Pourquoi mes populations de caractéristiques embarquées ont-elles chuté à 0 vers le 15 octobre ? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

Vers le 14 octobre 2019, j&#39;ai remarqué que mes populations de caractéristiques embarquées pour le graphique d&#39;ID de dispositif ont chuté à 0, où elles étaient auparavant beaucoup plus élevées.

![Image de la liste déroulante ID de périphérique](/help/using/support-issues/assets/device_id_populationdrop.png)

**Réponse**

Le 15 octobre, une mise à jour de la fonctionnalité de règle de fusion de profil d’Audience Manager a été modifiée afin que les données intégrées retirées d’un ID de gestion de la relation client téléchargé vers une source de données sur plusieurs périphériques ne soient plus réalisées par rapport aux ID de périphérique.  Auparavant, Audience Manager réalisait des performances par rapport à l’ID de plusieurs périphériques (ou à l’ID de gestion de la relation client) et copiait ces réalisations dans les UUID d’Audience Manager (ID de périphérique) associés.  Le changement a été apporté afin de refléter plus précisément la nature des données de caractéristiques et des profils en cours de réalisation.

Pour afficher les réalisations de caractéristiques, sélectionnez l’option &quot;ID de plusieurs périphériques&quot; dans le menu déroulant situé dans le coin supérieur droit de la vue Caractéristique.

![Afficher les réalisations par ID de plusieurs périphériques](/help/using/support-issues/assets/deviceid-crossdevice.png)

<br> 

## Pourquoi mes caractéristiques ou segments ne s’affichent-ils pas dans la page des rapports de chevauchement ?

Explication des raisons pour lesquelles les caractéristiques et les segments peuvent ne pas s’afficher dans la page des rapports de chevauchement.

**Question**

Pourquoi les utilisateurs ne voient-ils pas certaines caractéristiques et certains segments répertoriés dans la page des rapports de chevauchement lorsqu’ils tentent d’exécuter un rapport de chevauchement ?

**Réponse**

Un nombre minimum de visiteurs uniques doit être satisfait pour qu’une caractéristique ou un segment soit répertorié dans les rapports de chevauchement.


* Pour les caractéristiques : 28 000 sur une période de 14 jours
* Pour les segments : 7 000 utilisateurs en temps réel sur une période de 14 jours

Pour plus d’informations à ce sujet, consultez la page Echantillonnage des [données et taux d’erreur dans les rapports](/help/using/reporting/report-sampling.md)Audience Manager sélectionnés.