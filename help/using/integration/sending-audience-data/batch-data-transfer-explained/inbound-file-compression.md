---
description: En tant qu'option, vous pouvez compresser les fichiers de données lors de leur envoi à Audience Manager.
seo-description: En tant qu'option, vous pouvez compresser les fichiers de données lors de leur envoi à Audience Manager.
seo-title: Compression de fichier pour les fichiers de transfert de données entrants
solution: Audience Manager
title: Compression de fichier pour les fichiers de transfert de données entrants
uuid: 2 a 68 f 69 c -60 b 0-4002-863 b -302 d 2320 e 356
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

En tant qu&#39;option, vous pouvez compresser les fichiers de données lors de leur envoi à Audience Manager.

<!-- inbound-file-compression.xml -->

Audience Manager supports gzip ( `.gz`) compression for inbound, asynchronous data transfers.

Audience Manager prend également en charge les fichiers non compressés.

>[!IMPORTANT]
>
>Actuellement, nous ne prenons pas en charge le chiffrement et la compression dans le même fichier de données entrantes. You can select to either [encrypt](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) or compress your inbound files.

## Compression Amazon S 3

For delivery to [!DNL Amazon S3], you must use `.gz` or uncompressed files. Les fichiers compressés doivent être de 1 Go ou plus. Si les fichiers sont plus volumineux, veuillez discuter du fichier et du processus de transfert avec le service d&#39;assistance clientèle. Although [!DNL Audience Manager] can handle very large files, there may be ways to reduce the file size or make transfer of data more efficient.

>[!IMPORTANT]
>
>Your [!DNL FTP] client must use binary mode to transfer compressed or encrypted files. Compressed or encrypted files sent in [!DNL ASCII] mode will corrupt the data transfer file.

## Bonnes pratiques

* Files should be [!DNL .gzip] compressed (and have a [!DNL .gz] file extension.)
* The maximum compressed file size for a `.gz` compressed file is 1 GB.
* Les tailles de répartition optimales, pour le traitement rapide/le plus rapide de vos fichiers, sont d&#39;environ 1 Go décompressées ou de 200-300 Mo compressées.
* [!DNL Amazon S3] impose sa propre taille de fichier de 5 Go aux fichiers téléchargés.