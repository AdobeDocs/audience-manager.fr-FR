---
description: Le processus de transfert des données sortantes pour les clients utilisant Amazon Simple Storage Service (Amazon S3) nécessite que nous demandions votre clé d’accès Amazon S3 et votre clé secrète, afin de livrer les fichiers de données sortants dans votre compartiment.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 7302fafa537ad15144a64cc96f7150c5b0233c12
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 0%

---

# Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Le processus [!UICONTROL Outbound Data Transfer] pour les clients utilisant [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) nécessite que nous demandions votre clé d’accès et votre clé secrète [!DNL Amazon S3], afin de livrer les fichiers de données sortants dans votre compartiment.

Si vous ne souhaitez pas partager votre clé d’accès et votre clé secrète [!DNL Amazon S3] avec nous, contactez votre consultant [!DNL Audience Manager] ou l’assistance clientèle. Ils configureront [!DNL Cross-Account Bucket Permissions] pour vous.

Il vous suffit d’ajouter l’ID de compte [!DNL Amazon S3] à une liste autorisée pour le compartiment [!DNL S3] où vous souhaitez recevoir les fichiers de données sortants, comme décrit dans la [documentation Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Votre consultant [!DNL Audience Manager] ou l’assistance clientèle vous fournira l’ID de compte [!DNL Amazon S3].
