---
description: Le processus de transfert de données sortantes pour les clients qui utilisent Amazon Simple Storage Service (Amazon S3) nécessite que nous demandions votre clé d’accès Amazon S3 et votre clé secrète, afin de diffuser les fichiers de données sortantes dans votre compartiment.
seo-description: The Outbound Data Transfer process for customers using Amazon Simple Storage Service (Amazon S3) requires us to ask for your Amazon S3 access key and secret key, in order to deliver the outbound data files to your bucket.
seo-title: Leverage Amazon S3 Cross-Account Bucket Permissions for Your Outbound Files
solution: Audience Manager
title: Tirez parti des autorisations de compartiment entre comptes Amazon S3 pour vos fichiers sortants
uuid: 400a8d67-ebf3-48be-aa3f-498a5441f498
feature: Outbound Data Transfers
exl-id: e52f5bc0-7dc0-4c73-833c-5a778e8b5891
source-git-commit: 9c0254e8a29ffeb0353ed6faa898b74bcae7cef1
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 0%

---

# Tirez parti des autorisations de compartiment entre comptes Amazon S3 pour vos fichiers sortants {#leverage-amazon-s-cross-account-bucket-permissions-for-your-outbound-files}

Le processus de [!UICONTROL Outbound Data Transfer] pour les clients qui utilisent [!DNL Amazon Simple Storage Service] ([!DNL Amazon S3]) nécessite que nous demandions votre clé d’accès [!DNL Amazon S3] et votre clé secrète, afin de diffuser les fichiers de données sortants dans votre compartiment.

Si vous ne souhaitez pas partager votre clé d’accès [!DNL Amazon S3] et votre clé secrète avec nous, contactez votre consultant [!DNL Audience Manager] ou l’assistance clientèle et ils configureront les [!DNL Cross-Account Bucket Permissions] pour vous.

Il vous suffit d’ajouter votre identifiant de compte [!DNL Amazon S3] à une liste autorisée pour le compartiment [!DNL S3] où vous souhaitez recevoir les fichiers de données sortants, comme décrit dans la documentation [Amazon S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/example-walkthroughs-managing-access-example2.html). Votre consultant [!DNL Audience Manager] ou l’assistance clientèle vous fournira notre identifiant de compte [!DNL Amazon S3].

>[!NOTE]
>
>En raison de la limite de taille d’objet d’Amazon S3, Audience Manager prend en charge les tailles de partage allant jusqu’à 1 To. Si vous ne spécifiez aucune taille de partage, la limite de 1 To est automatiquement appliquée.

