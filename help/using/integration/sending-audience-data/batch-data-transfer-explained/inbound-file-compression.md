---
description: Vous pouvez également compresser les fichiers de données lors de leur envoi en Audience Manager.
seo-description: Vous pouvez également compresser les fichiers de données lors de leur envoi en Audience Manager.
seo-title: Compression de fichiers pour les fichiers de transfert de données entrants.
solution: Audience Manager
title: Compression de fichiers pour les fichiers de transfert de données entrants.
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 10%

---


# Compression de fichiers pour les fichiers de transfert de données entrants{#file-compression-for-inbound-data-transfer-files}.

Vous pouvez compresser les fichiers de données lors de leur envoi à l’Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager prend en charge la compression gzip (`.gz`) pour les transferts de données asynchrones entrants.

L’Audience Manager prend également en charge les fichiers non compressés.

>[!IMPORTANT]
>
>Nous ne prenons pas en charge le chiffrement des fichiers entrants compressés à l&#39;aide de gzip (`.gz`).
>
>Pour chiffrer et compresser les fichiers entrants, utilisez [chiffrement PGP](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] le chiffrement inclut la compression de fichiers.

## Amazon S3 - Compression

Pour la diffusion à [!DNL Amazon S3], vous devez utiliser des fichiers `.gz` ou non compressés. Les fichiers compressés doivent être de 1 Go ou moins. Si les fichiers sont plus volumineux, discutez du processus de transfert et de traitement des fichiers avec le service d’assistance clientèle. Bien que [!DNL Audience Manager] puisse gérer des fichiers très volumineux, il peut être possible de réduire la taille du fichier ou de rendre le transfert des données plus efficace.

>[!IMPORTANT]
>
>Votre client [!DNL FTP] doit utiliser le mode binaire pour transférer des fichiers compressés ou chiffrés. Les fichiers compressés ou chiffrés envoyés en mode [!DNL ASCII] corrompent le fichier de transfert de données.

## Bonnes pratiques

* Les fichiers doivent être [!DNL .gzip] compressés (et avoir une extension de fichier [!DNL .gz]).
* La taille de fichier compressé maximale pour un fichier compressé `.gz` est de 1 Go.
* Les tailles de fractionnement optimales, pour le traitement le plus rapide/le plus précoce de vos fichiers, sont d&#39;environ 1 Go décompressés ou de 200 à 300 Mo compressés.
* [!DNL Amazon S3] impose sa propre limite de 5 Go de taille de fichier aux fichiers téléchargés.
