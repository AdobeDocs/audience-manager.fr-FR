---
description: Le processus de transfert de données sortantes pour les clients utilisant Amazon Simple Enregistrement Service (Amazon S3) nous oblige à demander votre clé d'accès et clé secrète Amazon S3, afin de livrer les fichiers de données sortantes à votre compartiment.
seo-description: Le processus de transfert de données sortantes pour les clients utilisant Amazon Simple Enregistrement Service (Amazon S3) nous oblige à demander votre clé d'accès et clé secrète Amazon S3, afin de livrer les fichiers de données sortantes à votre compartiment.
seo-title: Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie
solution: Audience Manager
title: Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 14%

---


# Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Le processus [!UICONTROL Outbound Data Transfer] pour les clients utilisant [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) nécessite que nous demandions votre clé d&#39;accès et votre clé secrète [!DNL Amazon S3], afin de livrer les fichiers de données sortants à votre compartiment.

Si vous ne souhaitez pas partager votre clé d&#39;accès et votre clé secrète [!DNL Amazon S3] avec nous, contactez votre [!DNL Audience Manager] consultant ou le service à la clientèle et ils configureront [!DNL Cross-Account Bucket Permissions] pour vous. Il vous suffit d&#39;ajouter l&#39;ID de compte [!DNL Amazon S3] à une liste autorisée pour le compartiment [!DNL S3] dans lequel vous souhaitez recevoir les fichiers de données sortants, comme décrit dans la [documentation Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Votre [!DNL Audience Manager] consultant ou service à la clientèle vous fournira notre [!DNL Amazon S3] ID de compte.