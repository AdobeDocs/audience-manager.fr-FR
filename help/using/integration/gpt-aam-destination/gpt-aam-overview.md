---
description: Présentation de l’intégration de Google Ad Manager à l’aide des balises Google Publisher (GPT).
seo-description: Présentation de l’intégration de Google Ad Manager à l’aide des balises Google Publisher (GPT) dans l’Adobe Audience Manager (AAM).
seo-title: Intégration de Google Ad Manager à l’aide des balises Google Publisher (GPT) dans l’Adobe Audience Manager (AAM)
title: Intégration de Google Ad Manager à l’aide des balises Google Publisher (GPT)
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Integrate [!DNL Google Ad Manager] (formerly DFP) using Google Publisher Tags (GPT)

Les articles répertoriés ci-dessous offrent une vue d’ensemble de l’intégration [!DNL Google Ad Manager] à l’aide des balises Google Publisher (GPT). Vous pouvez utiliser une intégration côté serveur ou configurer GPT en tant que destination pour envoyer des données de segment d’Audience Manager à [!DNL Google Ad Manager]. Vous découvrirez également les étapes nécessaires pour assimiler les fichiers [!DNL Google Ad Manager] journaux à des rapports en Audience Manager.

* [Exigences et méthodes d’envoi de segments à Google Ad Manager à l’aide de balises Google Publisher (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Vous pouvez envoyer des segments qualifiés vers [!DNL Google Ad Manager] via une intégration côté client ou côté serveur. Les exigences et les informations connexes sur les deux méthodes sont énumérées ci-dessous.

* [Création d’une destination GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Vous pouvez envoyer des segments qualifiés vers [!DNL Google Ad Manager] via une intégration côté client (côté navigateur) ou une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour les balises Google Publisher en Audience Manager.

* [Modification de l’appel API GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Ajoutez une instruction if pour rechercher les cookies d’Audience Manager avant d’appeler la méthode .setTargeting de la balise Google Publisher.

* [Code Audience Manager pour les Google Publisher Tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt est une fonction JavaScript qui lit les données des cookies d’Audience Manager et envoie ces informations à Google Publisher Tags.
