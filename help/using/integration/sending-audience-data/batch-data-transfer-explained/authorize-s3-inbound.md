---
description: Pour envoyer des données de votre propre compartiment Amazon S3 vers Audience Manager, vous devez d’abord demander la configuration d’un rôle Amazon S3 dédié.
solution: Audience Manager
title: Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers entrants
feature: Inbound Data Transfers
source-git-commit: ff023fb57e2653ca65323313a37852d379e4b00c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---


# Utiliser les autorisations de compartiments inter-comptes Amazon S3 pour les fichiers entrants {#leverage-amazon-s-cross-account-bucket-permissions-for-your-inbound-files}

Pour envoyer des données de votre propre compartiment Amazon S3 vers Audience Manager, vous devez d’abord demander la configuration d’un rôle Amazon S3 dédié.

Pour ce faire, suivez les étapes décrites ci-dessous.

1. Contactez l’assistance clientèle et demandez une autre méthode d’envoi de fichiers à Audience Manager.
2. Fournissez à l’assistance clientèle les [!DNL Amazon Resource Name (ARN)] pour un rôle dans votre compte Amazon S3 que vous utiliserez pour envoyer des fichiers. _Ce rôle doit être créé avant de contacter l’assistance clientèle._. Une fois la configuration terminée, l’assistance clientèle vous fournira la variable [!DNL Amazon Resource Name (ARN)] pour le rôle nouvellement créé.
3. Modifiez les autorisations de votre rôle Amazon S3 existant pour assumer le rôle fourni par l’assistance clientèle.

>[!NOTE]
>
>Lors du transfert des données entrantes vers le compartiment Amazon S3 d’Audience Manager, veillez à utiliser la variable `bucket-owner-full-control` [liste de contrôle d&#39;accès](https://docs.aws.amazon.com/AmazonS3/latest/userguide/about-object-ownership.html) pour qu’Audience Manager traite correctement les données.
><br>
>Exemple pour la commande Amazon Web Services : `aws s3 cp <user_s3_uri> <AAM_s3_uri> --acl bucket-owner-full-control`.

