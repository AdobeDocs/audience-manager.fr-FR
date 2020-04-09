---
description: Vers le 14 octobre 2019, j'ai remarqué que mes populations de caractéristiques embarquées pour le graphique d'ID de dispositif ont chuté à 0, où elles étaient auparavant beaucoup plus élevées.
seo-description: Vers le 14 octobre 2019, j'ai remarqué que mes populations de caractéristiques embarquées pour le graphique d'ID de dispositif ont chuté à 0, où elles étaient auparavant beaucoup plus élevées.
seo-title: Pourquoi mes populations de caractéristiques embarquées ont-elles chuté à 0 vers le 15 octobre ?
solution: Audience Manager
title: Pourquoi mes populations de caractéristiques embarquées ont-elles chuté à 0 vers le 15 octobre ?
translation-type: tm+mt
source-git-commit: 0487a15c5fcd0e653bedf0e7fd8326f5cc363660

---


# Pourquoi mes populations de caractéristiques embarquées ont-elles chuté à 0 vers le 15 octobre ? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Question

Vers le 14 octobre 2019, j&#39;ai remarqué que mes populations de caractéristiques embarquées pour le graphique d&#39;ID de dispositif ont chuté à 0, où elles étaient auparavant beaucoup plus élevées. Pourquoi est-ce arrivé ?

![Image de la liste déroulante des ID de périphérique](assets/device_id_populationdrop.png)

## Réponse

Le 15 octobre, une mise à jour de  fonctionnalité de règle de fusion  Manager de a été modifiée afin que les données embarquées d’un ID de gestion de la relation client téléchargé vers une source de données sur plusieurs périphériques ne soient plus réalisées par rapport aux ID de périphérique.  Auparavant  Gestionnaire  de réalisait à la fois l’ID de plusieurs périphériques (ou ID de gestion de la relation client) et la copie de ces réalisations dans les UUID de gestionnaire de (ID de périphérique) associés.  Le changement a été apporté afin de refléter plus précisément la nature des données de caractéristiques et les  en cours de réalisation.

Pour  les réalisations de caractéristiques, sélectionnez l’option &quot;ID multi-périphériques&quot; dans la liste déroulante dans le coin supérieur droit du de caractéristiques.

![Réalisations  par ID de plusieurs périphériques](assets/deviceid-crossdevice.png)