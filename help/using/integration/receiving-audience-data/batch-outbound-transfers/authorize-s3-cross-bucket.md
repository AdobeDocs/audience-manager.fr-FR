---
description: Le processus de transfert des données sortantes pour les clients utilisant Amazon Simple Storage Service (Amazon S3) nécessite que nous demandions votre clé d’accès Amazon S3 et votre clé secrète, afin de livrer les fichiers de données sortants dans votre compartiment.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 7302fafa537ad15144a64cc96f7150c5b0233c12
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 12%

---

# Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

La variable [!UICONTROL Outbound Data Transfer] processus pour les clients qui utilisent [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) requiert que nous demandions à [!DNL Amazon S3] clé d’accès et clé secrète, afin de déposer les fichiers de données sortants dans votre compartiment.

Si vous ne souhaitez pas partager votre [!DNL Amazon S3] clé d&#39;accès et clé secrète avec nous, contactez votre [!DNL Audience Manager] consultant ou assistance clientèle ; ils configureront [!DNL Cross-Account Bucket Permissions] pour vous.

Il vous suffit d’ajouter notre [!DNL Amazon S3] ID de compte à une liste autorisée pour la variable [!DNL S3] compartiment où vous souhaitez recevoir les fichiers de données sortants, comme décrit dans la section [Documentation d’Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Votre [!DNL Audience Manager] notre conseiller ou l’assistance clientèle vous fournira [!DNL Amazon S3] ID de compte.
