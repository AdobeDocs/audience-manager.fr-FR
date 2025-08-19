---
description: Présentation de l’intégration de Google Ad Manager à l’aide de Google Publisher Tags (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Intégrer Google Ad Manager à l’aide de Google Publisher Tags (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Intégrer [!DNL Google Ad Manager] (anciennement DFP) à l’aide de Google Publisher Tags (GPT)

Les articles répertoriés ci-dessous présentent un aperçu sur la manière d’intégrer [!DNL Google Ad Manager] à l’aide de Google Publisher Tags (GPT). Vous pouvez utiliser une intégration côté serveur ou configurer GPT comme destination pour envoyer des données de segment Audience Manager à [!DNL Google Ad Manager]. Vous apprendrez également les étapes nécessaires pour ingérer des fichiers journaux [!DNL Google Ad Manager] pour la création de rapports dans Audience Manager.

* [Exigences et méthodes relatives à l’envoi de segments à Google Ad Manager à l’aide de Google Publisher Tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

  Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] via une intégration côté client ou côté serveur. Les conditions requises et les informations associées concernant les deux méthodes sont répertoriées ci-dessous.

* [Créer une destination GPT](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

  Vous pouvez envoyer des segments qualifiés à [!DNL Google Ad Manager] par le biais d’une intégration côté client (côté navigateur) ou côté serveur. Si vous choisissez l’intégration côté client, vous devez créer une destination basée sur des cookies pour les balises Google Publisher dans Audience Manager.

* [Modifier l’appel API setTargeting GPT](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

  Ajoutez une instruction if pour vérifier les cookies Audience Manager avant d’appeler la méthode Google Publisher Tag .setTargeting.

* [Code Audience Manager pour les balises de l’éditeur Google](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

  AamGpt est une fonction JavaScript qui lit les données de cookie Audience Manager et envoie ces informations aux balises de l’éditeur Google.
