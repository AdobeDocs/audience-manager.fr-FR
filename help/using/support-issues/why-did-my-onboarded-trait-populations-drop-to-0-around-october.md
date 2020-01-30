---
description: Vers le 14 octobre 2019, j'ai remarqué que mes populations de caractéristiques embarquées pour le graphique d'ID de dispositif ont chuté à 0, où elles étaient auparavant beaucoup plus élevées.
seo-description: Vers le 14 octobre 2019, j'ai remarqué que mes populations de caractéristiques embarquées pour le graphique d'ID de dispositif ont chuté à 0, où elles étaient auparavant beaucoup plus élevées.
seo-title: Pourquoi mes populations de caractéristiques embarquées ont-elles chuté à 0 vers le 15 octobre ?
solution: Audience Manager
title: Pourquoi mes populations de caractéristiques embarquées ont-elles chuté à 0 vers le 15 octobre ?
translation-type: tm+mt
source-git-commit: eb129bbf642cb666ce3ea05ff606c051e02f4d1e

---


# Pourquoi mes populations de caractéristiques embarquées ont-elles chuté à 0 vers le 15 octobre ? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

Vers le 14 octobre 2019, j&#39;ai remarqué que mes populations de caractéristiques embarquées pour le graphique d&#39;ID de dispositif ont chuté à 0, où elles étaient auparavant beaucoup plus élevées.

![Image de la liste déroulante ID de périphérique](/help/using/support-issues/assets/device_id_populationdrop.png)

**Réponse**

Le 15 octobre, une mise à jour de la fonctionnalité de règle de fusion de profil d’Audience Manager a été modifiée afin que les données intégrées retirées d’un ID de gestion de la relation client téléchargé vers une source de données sur plusieurs périphériques ne soient plus réalisées par rapport aux ID de périphérique.  Auparavant, Audience Manager réalisait des performances par rapport à l’ID de plusieurs périphériques (ou à l’ID de gestion de la relation client) et copiait ces réalisations dans les UUID d’Audience Manager (ID de périphérique) associés.  Le changement a été apporté afin de refléter plus précisément la nature des données de caractéristiques et des profils en cours de réalisation.

Pour afficher les réalisations de caractéristiques, sélectionnez l’option &quot;ID de plusieurs périphériques&quot; dans le menu déroulant situé dans le coin supérieur droit de la vue Caractéristique.

![Afficher les réalisations par ID de plusieurs périphériques](/help/using/support-issues/assets/deviceid-crossdevice.png)

