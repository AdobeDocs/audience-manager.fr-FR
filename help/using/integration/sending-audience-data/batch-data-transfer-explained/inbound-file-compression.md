---
description: Vous pouvez également compresser les fichiers de données lors de leur envoi vers Audience Manager.
seo-description: Vous pouvez également compresser les fichiers de données lors de leur envoi vers Audience Manager.
seo-title: Compression de fichiers pour les fichiers de transfert de données entrants
solution: Audience Manager
title: Compression de fichiers pour les fichiers de transfert de données entrants
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
translation-type: tm+mt
source-git-commit: b2e0b560a944f2ad63a48476be647f1355712342

---


# Compression de fichiers pour les fichiers de transfert de données entrants{#file-compression-for-inbound-data-transfer-files}

Vous pouvez compresser les fichiers de données lors de leur envoi à Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager prend en charge la compression gzip (`.gz`) pour les transferts de données asynchrones entrants.

Audience Manager prend également en charge les fichiers non compressés.

>[!IMPORTANT]
>
>Nous ne prenons pas en charge le chiffrement des fichiers entrants compressés à l’aide de gzip (`.gz`).
>
> Pour chiffrer et compresser des fichiers entrants, utilisez le chiffrement [](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)PGP. [!DNL PGP] le chiffrement inclut la compression de fichiers.

## Compression Amazon S3

Pour la diffusion vers [!DNL Amazon S3], vous devez utiliser `.gz` ou décompresser des fichiers. Les fichiers compressés doivent être de 1 Go ou moins. Si les fichiers sont plus volumineux, discutez-en avec le service à la clientèle et transférez-les. Bien [!DNL Audience Manager] qu’il soit possible de gérer des fichiers très volumineux, il peut être possible de réduire la taille du fichier ou de rendre le transfert des données plus efficace.

>[!IMPORTANT]
>
>Votre [!DNL FTP] client doit utiliser le mode binaire pour transférer des fichiers compressés ou chiffrés. Les fichiers compressés ou chiffrés envoyés en [!DNL ASCII] mode corrompent le fichier de transfert de données.

## Bonnes pratiques

* Les fichiers doivent être [!DNL .gzip] compressés (avec une extension de [!DNL .gz] fichier).
* La taille de fichier compressé maximale pour un fichier `.gz` compressé est de 1 Go.
* Les tailles de fractionnement optimales, pour le traitement le plus rapide/le plus précoce de vos fichiers, sont d’environ 1 Go décompressé ou de 200 à 300 Mo compressé.
* [!DNL Amazon S3] impose sa propre limite de taille de fichier de 5 Go sur les fichiers téléchargés.
