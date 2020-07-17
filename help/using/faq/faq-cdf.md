---
description: Questions fréquentes sur les fichiers de flux de données client (CDF).
seo-description: Questions fréquentes sur les fichiers de flux de données client (CDF).
seo-title: FAQ sur le flux de données client
solution: Audience Manager
title: FAQ sur le flux de données client
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Customer Data Feeds
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 100%

---


# FAQ sur le flux de données client {#customer-data-feed-faq}

Questions fréquentes sur les fichiers de flux de données client (CDF).

## Stockage Amazon S3 {#amazon-s3-storage}

**Où est stocké mon fichier CDF sur [!DNL Amazon] ?**

Votre fichier CDF est stocké dans le répertoire racine `aam-cdf` d’un serveur [!DNL Amazon S3]. Ce compartiment par défaut est géré par [!DNL Audience Manager]. Voir aussi [Conventions de dénomination des fichiers de flux de données client](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**Mon compartiment de stockage est-il sécurisé ?**

Oui. Les clients n’ont accès qu’à leur propre espace de stockage. Vous disposerez d’un accès en lecture seule à votre compartiment de stockage. Vous ne disposerez pas d’un accès en écriture.

<br> 

**Puis-je personnaliser mon compartiment de stockage ou stocker des fichiers dans un autre répertoire ?**

Non. Les options de personnalisation et de stockage alternatif ne sont pas disponibles.

<br> 

**Un fichier est manquant dans mon répertoire pour une heure donnée. Où se trouve-t-il ?**

Un fichier manquant signifie que [!DNL Audience Manager] n’a pas pu traiter vos fichiers CDF pendant cette heure. Cela se produit généralement lorsque nos serveurs prennent du retard dans le traitement des fichiers CDF. Dans ce cas, votre fichier n’est pas perdu. Il apparaîtra dans un répertoire d’une heure ultérieure, lorsque notre système aura eu la possibilité de rattraper son retard. Voir aussi [Notifications de traitement des fichiers de flux de données client.](../features/cdf-files.md#cdf-file-processing-notifications)

<br> 

**Comment savoir quand mes fichiers CDF sont prêts ?**

Voir [Notifications de traitement des fichiers de flux de données client](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## Tailles de fichiers {#file-sizes}

**À quel type de tailles de fichiers dois-je m’attendre ? Quelle est la taille moyenne d’un fichier CDF ?**

Les tailles de fichiers sont difficiles à estimer. De plus, chaque fichier peut avoir une taille différente. Les tailles varient d’une heure à l’autre et de jour en jour. Il est utile d’être prêt à gérer un grand nombre de données lorsque vous recevez des fichiers CDF.

<br> 

**Combien de fichiers vais-je recevoir ?**

Encore une fois, cela est difficile à estimer. Toutefois, il est utile d’être prêt à gérer un grand nombre de données lorsque vous recevez des fichiers CDF.

<br> 

## Intégrité des données {#data-integrity}

**Comment puis-je vérifier l’intégrité des données chargées sur Amazon S3 ?**

[!DNL Amazon] divise les fichiers volumineux en plusieurs parties plus petites et les charge sur [!DNL Amazon S3] à l’aide du chargement en plusieurs parties. Ensuite, il génère une valeur `ETag` pour le chargement en plusieurs parties. Il calcule d’abord les sommes de contrôle MD5 individuelles de chaque partie chargée, puis les concatène en une seule chaîne. Ensuite, il calcule la somme de contrôle MD5 de la chaîne. La somme de contrôle résultante (la valeur `ETag`) est ensuite ajoutée avec un trait d’union et le nombre total de parties utilisées pour le chargement. Par exemple, la valeur `ETag` d’un fichier qui a été divisé en 5 parties au cours du chargement peut ressembler à ceci : `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Rétention des données {#data-retension}

**Quelle est la durée de conservation des fichiers CDF ?**

Les données sont supprimées après 8 (huit) jours.

<br> 

**Puis-je obtenir des fichiers CDF rétroactivement ou pour les jours précédents ?**

Vous ne pouvez générer des fichiers CDF que pour les 8 derniers jours. Il est impossible de générer à nouveau des fichiers CDF datant de plus de 8 jours.

>[!MORELIKETHIS]
>
>* [Flux de données client](../features/cdf-files.md)

