---
description: Présentation de l’intégration de DFP à l’aide des balises Google Publisher (GPT).
seo-description: Présentation de l’intégration de DFP à l’aide des balises Google Publisher (GPT) dans Adobe Audience Manager (AAM).
seo-title: Intégration de DFP à l’aide des balises Google Publisher (GPT) dans Adobe Audience Manager (AAM)
title: Intégration de DFP à l’aide des balises Google Publisher (GPT)
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Intégration de DFP à l’aide des balises Google Publisher (GPT)

Les articles répertoriés ci-dessous donnent un aperçu de la manière d’intégrer DFP à l’aide de balises Google Publisher (GPT). Vous pouvez utiliser une intégration côté serveur ou configurer GPT en tant que destination pour envoyer les données de segments d’Audience Manager au DFP. Vous apprendrez également les étapes nécessaires pour assimiler les fichiers journaux DFP en vue de la création de rapports dans Audience Manager.

* [Conditions requises et méthodes d’envoi de segments à DFP à l’aide de balises Google Publisher Tag (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Vous pouvez envoyer des segments qualifiés au DFP soit par le biais d’une intégration côté client, soit par le biais d’une intégration côté serveur. Les exigences et les informations connexes sur les deux méthodes sont énumérées ci-dessous.

* [Création d’une destination GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Vous pouvez envoyer des segments qualifiés au DFP via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour les balises Google Publisher dans Audience Manager.

* [Modification de l’appel de l’API setTargeting GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Ajoutez une instruction if pour rechercher les cookies d’Audience Manager avant d’appeler la méthode .setTargeting de balise Google Publisher.

* [Code Audience Manager pour les balises Google Publisher](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt est une fonction JavaScript qui lit les données de cookie Audience Manager et envoie ces informations aux balises Google Publisher.
