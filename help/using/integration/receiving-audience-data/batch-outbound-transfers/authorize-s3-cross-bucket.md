---
description: Le processus de transfert de données sortantes pour les clients utilisant Amazon Simple Storage Service (Amazon S3) nous oblige à demander votre clé d’accès Amazon S3 et votre clé secrète, afin de livrer les fichiers de données sortantes à votre compartiment.
seo-description: Le processus de transfert de données sortantes pour les clients utilisant Amazon Simple Storage Service (Amazon S3) nous oblige à demander votre clé d’accès Amazon S3 et votre clé secrète, afin de livrer les fichiers de données sortantes à votre compartiment.
seo-title: Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie
solution: Audience Manager
title: Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Le [!UICONTROL Outbound Data Transfer] processus pour les clients qui utilisent [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) nécessite que nous demandions votre clé [!DNL Amazon S3] d'accès et votre clé secrète, afin de livrer les fichiers de données sortantes à votre compartiment.

Si vous préférez ne pas partager votre clé d’ [!DNL Amazon S3] accès et votre clé secrète avec nous, contactez votre [!DNL Audience Manager] consultant ou le service à la clientèle et ils vous configureront [!DNL Cross-Account Bucket Permissions] . Il vous suffit d’indiquer l’ID de [!DNL Amazon S3] compte du [!DNL S3] compartiment dans lequel vous souhaitez recevoir les fichiers de données sortants, comme décrit dans la documentation [](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html)Amazon S3. Votre [!DNL Audience Manager] conseiller ou le service à la clientèle vous indiquera l’ID de [!DNL Amazon S3] compte.