---
description: Le processus de transfert de données sortantes pour les clients utilisant Amazon Simple Enregistrement Service (Amazon S3) nous oblige à demander votre clé d’accès et votre clé secrète Amazon S3, afin de livrer les fichiers de données sortantes à votre compartiment.
seo-description: Le processus de transfert de données sortantes pour les clients utilisant Amazon Simple Enregistrement Service (Amazon S3) nous oblige à demander votre clé d’accès et votre clé secrète Amazon S3, afin de livrer les fichiers de données sortantes à votre compartiment.
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

Le [!UICONTROL Outbound Data Transfer] processus pour les clients qui utilisent [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) nécessite que nous leur demandions votre clé d&#39; [!DNL Amazon S3] accès et votre clé secrète, afin de leur livrer les fichiers de données sortantes.

Si vous ne souhaitez pas partager votre clé d’ [!DNL Amazon S3] accès et votre clé secrète avec nous, contactez votre [!DNL Audience Manager] consultant ou le service à la clientèle et ils vous configureront [!DNL Cross-Account Bucket Permissions] pour vous. Il vous suffit d’ajouter l’ID de [!DNL Amazon S3] compte à une liste autorisée pour le [!DNL S3] compartiment où vous souhaitez recevoir les fichiers de données sortants, comme décrit dans la documentation [](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)Amazon S3. Votre [!DNL Audience Manager] conseiller ou le service à la clientèle vous fournira notre [!DNL Amazon S3] identifiant de compte.