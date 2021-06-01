---
description: Vous pouvez, au choix, compresser les fichiers de données lors de leur envoi à Audience Manager.
seo-description: Vous pouvez, au choix, compresser les fichiers de données lors de leur envoi à Audience Manager.
seo-title: Compression de fichiers pour les fichiers de transfert de données entrants.
solution: Audience Manager
title: Compression de fichiers pour les fichiers de transfert de données entrants.
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Transferts des données entrantes
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 11%

---

# Compression de fichiers pour les fichiers de transfert de données entrants{#file-compression-for-inbound-data-transfer-files}.

Vous pouvez compresser les fichiers de données lors de leur envoi à Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager prend en charge la compression gzip (`.gz`) pour les transferts de données asynchrones entrants.

Audience Manager prend également en charge les fichiers non compressés.

>[!IMPORTANT]
>
>Nous ne prenons pas en charge le cryptage sur les fichiers entrants compressés à l’aide de gzip (`.gz`).
>
>Pour chiffrer et compresser les fichiers entrants, utilisez [Chiffrement PGP](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] le chiffrement inclut la compression de fichiers.

## Compression Amazon S3

Pour une diffusion vers [!DNL Amazon S3], vous devez utiliser `.gz` ou des fichiers non compressés. Les fichiers compressés doivent être de 1 Go ou moins. Si les fichiers sont plus volumineux, discutez du processus de transfert et de fichier avec l’assistance clientèle. Bien que [!DNL Audience Manager] puisse gérer des fichiers très volumineux, il existe des moyens de réduire la taille du fichier ou de rendre le transfert des données plus efficace.

>[!IMPORTANT]
>
>Votre client [!DNL FTP] doit utiliser le mode binaire pour transférer des fichiers compressés ou chiffrés. Les fichiers compressés ou chiffrés envoyés en mode [!DNL ASCII] corrompent le fichier de transfert de données.

## Bonnes pratiques

* Les fichiers doivent être [!DNL .gzip] compressés (et avoir une extension de fichier [!DNL .gz]).
* La taille de fichier compressé maximale d’un fichier `.gz` compressé est de 1 Go.
* Les tailles de partage optimales, pour un traitement le plus rapide/le plus ancien de vos fichiers, sont d’environ 1 Go décompressées ou de 200 à 300 Mo compressées.
* [!DNL Amazon S3] impose sa propre limite de taille de fichier de 5 Go aux fichiers chargés.
