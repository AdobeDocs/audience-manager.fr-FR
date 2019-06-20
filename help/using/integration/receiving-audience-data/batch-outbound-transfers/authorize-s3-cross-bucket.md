---
description: Le processus de transfert de données sortant pour les clients qui utilisent Amazon Simple Storage Service (Amazon S 3) exige que nous demandions votre clé d'accès Amazon S 3 et votre clé secrète, afin de fournir les fichiers de données sortants à votre compartiment.
seo-description: Le processus de transfert de données sortant pour les clients qui utilisent Amazon Simple Storage Service (Amazon S 3) exige que nous demandions votre clé d'accès Amazon S 3 et votre clé secrète, afin de fournir les fichiers de données sortants à votre compartiment.
seo-title: Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie
solution: Audience Manager
title: Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie
uuid: 400 a 8 d 67-ebf 3-48 be-aa 3 f -498 a 5441 f 498
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers de sortie {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

[!UICONTROL Outbound Data Transfer] Le processus des clients utilisant [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) nécessite que nous demandions votre clé [!DNL Amazon S3] d&#39;accès et votre clé secrète, afin de fournir les fichiers de données sortants à votre compartiment.

If you&#39;d rather not share your [!DNL Amazon S3] access key and secret key with us, contact your [!DNL Audience Manager] consultant or Customer Care and they will set up [!DNL Cross-Account Bucket Permissions] for you. You only need to whitelist our [!DNL Amazon S3] account ID for the [!DNL S3] bucket where you wish to receive the outbound data files, as described in the [Amazon S3 documentation](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Your [!DNL Audience Manager] consultant or Customer Care will provide you with our [!DNL Amazon S3] account ID.