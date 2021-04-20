---
description: Présentation de l’intégration de Google Ad Manager à l’aide des balises Google Publisher (GPT).
seo-description: Présentation de l’intégration de Google Ad Manager à l’aide des balises Google Publisher (GPT) dans Adobe Audience Manager (AAM).
seo-title: Intégration de Google Ad Manager à l’aide des balises Google Publisher (GPT) dans Adobe Audience Manager (AAM)
title: Intégration de Google Ad Manager à l’aide des balises Google Publisher (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# Intégrer [!DNL Google Ad Manager] (anciennement DFP) à l’aide des balises Google Publisher (GPT)

Les articles répertoriés ci-dessous donnent un aperçu de la manière d’intégrer [!DNL Google Ad Manager] à l’aide des balises Google Publisher (GPT). Vous pouvez utiliser une intégration côté serveur ou configurer GPT en tant que destination pour envoyer des données de segment d&#39;Audience Manager à [!DNL Google Ad Manager]. Vous apprendrez également les étapes nécessaires pour assimiler des fichiers journaux [!DNL Google Ad Manager] pour le rapports en Audience Manager.

* [Exigences et méthodes d’envoi de segments à Google Ad Manager à l’aide de balises Google Publisher (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] soit par le biais d&#39;une intégration côté client, soit par le biais d&#39;une intégration côté serveur. Les exigences et les informations connexes sur les deux méthodes sont énumérées ci-dessous.

* [Création d’une destination GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] via une intégration côté client (côté navigateur) ou côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour les balises Google Publisher en Audience Manager.

* [Modification de l’appel API GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Ajoutez une instruction if pour rechercher les cookies d’Audience Manager avant d’appeler la méthode Google Publisher Tag .setTargeting.

* [Code Audience Manager pour les Google Publisher Tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt est une fonction JavaScript qui lit les données des cookies d’Audience Manager et envoie ces informations à Google Publisher Tags.
