---
description: Questions fréquentes sur les fichiers CDF (Customer Data Feed).
seo-description: Questions fréquentes sur les fichiers CDF (Customer Data Feed).
seo-title: FAQ sur le flux de données client
solution: Audience Manager
title: FAQ sur le flux de données client
uuid: 7183 b 3 e 2-e 999-4 e 1 e -892 f -2 bab 335 c 13 b 6
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Customer Data Feed FAQ{#customer-data-feed-faq}

Questions fréquentes sur les fichiers CDF (Customer Data Feed).

## Amazon S3 Storage {#amazon-s3-storage}

**Où est stockée mon fichier CDF[!DNL Amazon]?**

Your CDF file is stored in the `aam-cdf` root directory on an [!DNL Amazon S3] server. This default bucket is managed by [!DNL Audience Manager]. See also [Customer Data Feed File Naming Conventions](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**Mon compartiment de stockage est-il sécurisé ?**

Oui. Les clients ont accès à leur propre espace de stockage. Vous disposez d'un accès en lecture seule à votre compartiment de stockage. Vous n'aurez pas d'accès en écriture.

<br> 

**Puis-je personnaliser mon compartiment de stockage ou stocker des fichiers dans un autre répertoire ?**

Non. Les options de personnalisation et de stockage alternatif ne sont pas disponibles.

<br> 

**Il manque un fichier dans mon répertoire pendant une heure particulière. Where is it?**

A missing file means [!DNL Audience Manager] was not able to process your CDF files for that hour. Cela survient généralement lorsque nos serveurs se retrouvent derrière le traitement des fichiers CDF. Dans ce cas, votre fichier n'est pas perdu. Il apparaîtra dans un répertoire horaire ultérieur une fois que notre système aura la chance de rattraper le problème. See also, [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Comment savoir quand mes fichiers CDF sont prêts ?**

See [Customer Data Feed File Processing Notifications](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## File Sizes {#file-sizes}

**Quel type de fichier devrais-je prévoir ? How big is an average CDF file?**

Il est difficile d'estimer les tailles de fichier. Et chaque fichier peut avoir une taille différente. Les tailles varient d'une heure à l'autre. Si vous allez recevoir des fichiers CDF, il est utile d'être prêt à gérer beaucoup de données.

<br> 

**Combien de fichiers vais-je recevoir ?**

Là encore, il est difficile de l'estimer. Toutefois, si vous allez recevoir des fichiers CDF, il est utile d'être prêt à gérer beaucoup de données.

<br> 

## Data Integrity {#data-integrity}

**Comment puis-je vérifier l'intégrité des données téléchargées dans Amazon S 3 ?**

Files exceeding 16MiB in size are split into 16MiB chunks and uploaded to [!DNL Amazon S3] using multi-part upload.

[!DNL Amazon] génère `ETag` une valeur pour les transferts à parties multiples. Il calcule d'abord les sommes de contrôle MD 5 individuelles de chaque partie téléchargée, puis les concatène dans une seule chaîne. Puis calcule la somme de contrôle MD 5 de la chaîne. The resulting checksum (the `ETag`) is then appended with a hyphen and the total number of parts used for upload. For instance, the `ETag` for a file that was split into 5 parts during upload could look something like this: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**Combien de temps avez-vous stocké les fichiers CDF ?**

Les données sont supprimées après 8 (8) jours.

<br> 

**Puis-je obtenir des fichiers CDF rétroactivement ou pour des jours précédents ?**

Vous pouvez générer uniquement des fichiers CDF au cours des 8 derniers jours. Les fichiers CDF pour les intervalles antérieurs aux 8 derniers jours ne peuvent pas être recréés.

>[!MORE_ LIKE_ THIS]
>
>* [Flux de données client](../features/cdf-files.md)

