---
description: Présentation de l’intégration de DFP à l’aide des balises Google Publisher (GPT).
seo-description: Présentation de l’intégration de DFP à l’aide de balises Google Publisher (GPT) dans Adobe Audience Manager (AAM).
seo-title: Intégration de DFP à l’aide de balises Google Publisher (GPT) dans l’Adobe Audience Manager (AAM)
title: Intégration de DFP à l’aide de balises Google Publisher (GPT)
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 5%

---


# Intégration de DFP à l’aide de balises Google Publisher (GPT)

Les articles répertoriés ci-dessous offrent une vue d’ensemble de l’intégration de DFP à l’aide de balises Google Publisher (GPT). Vous pouvez utiliser une intégration côté serveur ou configurer GPT comme destination pour envoyer des données de segment d’Audience Manager à DFP. Vous apprendrez également les étapes nécessaires pour importer les fichiers journaux DFP pour le rapports en Audience Manager.

* [Conditions requises et méthodes d’envoi de segments à DFP à l’aide de balises Google Publisher Tag (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Vous pouvez envoyer des segments qualifiés à DFP soit par le biais d’une intégration côté client, soit par le biais d’une intégration côté serveur. Les exigences et les informations connexes sur les deux méthodes sont énumérées ci-dessous.

* [Créer une destination GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Vous pouvez envoyer des segments qualifiés à DFP via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour les balises Google Publisher en Audience Manager.

* [Modification de l’appel de l’API GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Ajoutez une instruction if pour rechercher les cookies d’Audience Manager avant d’appeler la méthode .setTargeting de la balise Google Publisher.

* [Code d’Audience Manager pour les balises Google Publisher](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt est une fonction JavaScript qui lit les données des cookies d’Audience Manager et envoie ces informations à Google Publisher Tags.
