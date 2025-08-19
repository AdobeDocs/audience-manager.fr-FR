---
description: Pour envoyer des données de votre propre compartiment Amazon S3 à Audience Manager, vous devez d’abord demander la configuration d’un rôle Amazon S3 dédié.
solution: Audience Manager
title: Utilisation des autorisations de compartiment entre comptes Amazon S3 pour vos fichiers entrants
feature: Inbound Data Transfers
exl-id: 56ecea5a-0621-4720-9e4c-f9086294c31f
source-git-commit: 65963c462f2a5abb1e2597b3d943628baa9d4730
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Utilisation des autorisations de compartiment entre comptes Amazon S3 pour vos fichiers entrants {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Pour envoyer des données de votre propre compartiment Amazon S3 à Audience Manager, vous devez d’abord demander la configuration d’un rôle Amazon S3 dédié.

Pour ce faire, suivez les étapes décrites ci-dessous.

1. Contactez l’assistance clientèle et demandez une autre méthode d’envoi de fichiers à Audience Manager.
2. Fournissez à l’assistance clientèle les [!DNL Amazon Resource Name (ARN)] d’un rôle dans votre compte Amazon S3 que vous utiliserez pour envoyer des fichiers. _Ce rôle doit être créé avant de contacter l’assistance clientèle_. Une fois la configuration terminée, l’assistance clientèle vous fournira les [!DNL Amazon Resource Name (ARN)] pour le rôle nouvellement créé.
3. Modifiez les autorisations de votre rôle Amazon S3 existant pour assumer le rôle fourni par l’assistance clientèle.

>[!NOTE]
>
>Lors du transfert de données entrantes vers le compartiment Audience Manager Amazon S3, veillez à utiliser la `bucket-owner-full-control` [liste de contrôle d’accès](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) afin qu’Audience Manager traite correctement les données.
>
>Exemple pour la commande Amazon Web Services : `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`
