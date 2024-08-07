---
description: Présentation de l’intégration de Google Ad Manager à l’aide de Google Publisher Tags (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Intégration de Google Ad Manager à l’aide des balises de l’éditeur Google (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Intégrer [!DNL Google Ad Manager] (anciennement DFP) à l’aide de Google Publisher Tags (GPT)

Les articles répertoriés ci-dessous fournissent une vue d’ensemble de l’intégration de [!DNL Google Ad Manager] à l’aide de Google Publisher Tags (GPT). Vous pouvez utiliser une intégration côté serveur ou configurer GPT en tant que destination pour envoyer des données de segment d’Audience Manager à [!DNL Google Ad Manager]. Vous découvrirez également les étapes nécessaires à l’ingestion de fichiers journaux [!DNL Google Ad Manager] pour la création de rapports dans Audience Manager.

* [Conditions requises et méthodes d’envoi de segments à Google Ad Manager à l’aide de balises de l’éditeur Google (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

  Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] par le biais d’une intégration côté client ou côté serveur. Les exigences et les informations connexes relatives aux deux méthodes sont répertoriées ci-dessous.

* [Création d’une destination GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

  Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] par le biais d’une intégration côté client (côté navigateur) ou d’une intégration côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur les cookies pour les balises de l’éditeur Google dans Audience Manager.

* [Modification de l’appel de l’API GPT setTargeting](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

  Ajoutez une instruction if pour rechercher les cookies d’Audience Manager avant d’appeler la méthode Google Publisher Tag .setTargeting .

* [Code d’Audience Manager pour les balises de l’éditeur Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

  AamGpt est une fonction JavaScript qui lit les données de cookie d’Audience Manager et envoie ces informations à Google Publisher Tags.
