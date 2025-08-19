---
description: Vous pouvez, de manière optionnelle, compresser les fichiers de données lors de leur envoi vers Audience Manager.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: Compression des fichiers pour le transfert de données entrantes
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Compression des fichiers pour le transfert de données entrantes{#file-compression-for-inbound-data-transfer-files}

Vous pouvez compresser les fichiers de données lors de leur envoi à Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager prend en charge la compression gzip (`.gz`) pour les transferts de données entrants et asynchrones.

Audience Manager prend également en charge les fichiers non compressés.

>[!IMPORTANT]
>
>Nous ne prenons pas en charge le chiffrement des fichiers entrants compressés à l’aide de gzip (`.gz`).
>
>Pour chiffrer et compresser les fichiers entrants, utilisez le chiffrement [PGP](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). Le chiffrement [!DNL PGP] inclut la compression de fichiers.

## Compression Amazon S3

Pour la diffusion vers [!DNL Amazon S3], vous devez utiliser des fichiers `.gz` ou non compressés. Les fichiers compressés doivent faire 1 Go ou moins. Si les fichiers sont plus volumineux, veuillez discuter du processus de transfert de fichiers avec l’assistance clientèle. Bien que [!DNL Audience Manager] puissiez gérer des fichiers très volumineux, il existe peut-être des moyens de réduire la taille du fichier ou de rendre le transfert de données plus efficace.

>[!IMPORTANT]
>
>Votre client [!DNL FTP] doit utiliser le mode binaire pour transférer des fichiers compressés ou chiffrés. Les fichiers compressés ou chiffrés envoyés en mode [!DNL ASCII] corrompront le fichier de transfert de données.

## Bonnes pratiques

* Les fichiers doivent être [!DNL .gzip] compressés (et avoir une extension de fichier [!DNL .gz]).
* La taille maximale du fichier compressé `.gz` est de 1 Go.
* Les tailles de partage optimales, pour un traitement le plus rapide/le plus précoce de vos fichiers, sont d’environ 1 Go sans compression ou 200 à 300 Mo compressés.
* [!DNL Amazon S3] impose sa propre limite de taille de fichier de 5 Go aux fichiers chargés.
