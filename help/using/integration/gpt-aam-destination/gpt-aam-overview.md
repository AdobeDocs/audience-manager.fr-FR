---
description: Présentation de l'intégration de DFP à l'aide de Balises Google Publisher (GPT).
seo-description: Présentation de l'intégration de DFP à l'aide de Balises Google Publisher (GPT) dans Adobe Audience Manager (AAM).
seo-title: Intégration de DFP à l'aide de balises Google Publisher (GPT) dans Adobe Audience Manager (AAM)
title: Intégration de DFP à l'aide de balises Google Publisher (GPT)
translation-type: tm+mt
source-git-commit: a1960a65058622c198bb07d7c20c1e21e2eaf00a

---


# Intégration de DFP à l'aide de balises Google Publisher (GPT)

Les articles répertoriés ci-dessous fournissent une vue d'ensemble de l'intégration de DFP à l'aide de Balises Google Publisher (GPT). Vous pouvez utiliser une intégration côté serveur ou configurer GPT comme destination pour envoyer les données de segment Audience Manager au DFP. Vous découvrirez également les étapes nécessaires à l'assimilation des fichiers journaux DFP pour la création de rapports dans Audience Manager.

* [Conditions requises et méthodes d’envoi de segments à DFP à l’aide de balises Google Publisher Tag (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Vous pouvez envoyer des segments qualifiés au DFP via un côté client ou via une intégration côté serveur. Les exigences et les informations associées au sujet des deux méthodes sont répertoriées ci-dessous.

* [Création d'une destination GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Vous pouvez envoyer des segments qualifiés au DFP via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l'intégration côté client, vous devez créer une destination basée sur cookie pour les balises Google Publisher dans Audience Manager.

* [Modification de l'appel de l'API settargeting GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Ajoutez une instruction if pour rechercher les cookies Audience Manager avant d'appeler la méthode Google Publisher Tag. settargeting.

* [Code Audience Manager pour les balises Google Publisher](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   Aamgpt est une fonction JavaScript qui lit les données du cookie Audience Manager et envoie ces informations aux balises Google Publisher.
