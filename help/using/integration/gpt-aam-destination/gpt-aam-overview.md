---
description: Présentation de l’intégration de Google Ad Manager à l’aide de Google Publisher Tags (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Intégrer Google Ad Manager à l’aide de Google Publisher Tags (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
TQID: https://experienceleague.adobe.com/29V5C3MbEondd3-qWLBfi3jaGid1I1UM9nYIl9nZWVo
product_v2: id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2: id: a8b0238e-1d43-4679-a3b4-5ba1bad83baaid: a99472c1-6aae-4c7a-8aa0-f60636369620
subfeature_v2: id: a49258d4-867f-4130-b875-d72c001bdf6c
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 212
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
