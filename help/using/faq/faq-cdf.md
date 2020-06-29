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
ht-degree: 0%

---


# FAQ sur le flux de données client{#customer-data-feed-faq}

Questions fréquentes sur les fichiers de flux de données client (CDF).

## Enregistrement Amazon S3 {#amazon-s3-storage}

**Où est stocké mon fichier CDF[!DNL Amazon]?**

Votre fichier CDF est stocké dans le répertoire `aam-cdf` racine d’un [!DNL Amazon S3] serveur. Ce compartiment par défaut est géré par [!DNL Audience Manager]. Voir aussi Conventions [de dénomination des fichiers de flux de données](../features/cdf-files.md#cdf-naming-conventions)client.

<br> 

**Est-ce que mon seau d&#39;enregistrements est sécurisé ?**

Oui. Les clients n&#39;ont accès qu&#39;à leur propre espace d&#39;enregistrement. Vous aurez un accès en lecture seule à votre compartiment d&#39;enregistrement. Vous n&#39;aurez pas accès en écriture.

<br> 

**Puis-je personnaliser mon compartiment d’enregistrements ou stocker des fichiers dans un autre répertoire ?**

Non. Les options de personnalisation et d’enregistrement de remplacement ne sont pas disponibles.

<br> 

**Il manque un fichier dans mon répertoire pendant une heure donnée. Où est-ce ?**

Un fichier manquant signifie que [!DNL Audience Manager] les fichiers CDF n&#39;ont pas pu être traités pendant cette heure. Cela se produit généralement lorsque nos serveurs sont en retard dans le traitement des fichiers CDF. Dans ce cas, votre fichier n’est pas perdu. Il apparaîtra dans un répertoire horaire ultérieur une fois que notre système aura eu la chance de rattraper le retard. Voir aussi Notifications [de traitement des fichiers de flux de données](../features/cdf-files.md#cdf-file-processing-notifications)client.

<br> 

**Comment savoir quand mes fichiers CDF sont prêts ?**

Voir Notifications [de traitement des fichiers de flux de données](../features/cdf-files.md#cdf-file-processing-notifications)client.

<br> 

## Taille de fichier {#file-sizes}

**Quelle taille de fichier dois-je attendre ? Quelle est la taille d&#39;un fichier CDF moyen ?**

Il est difficile d&#39;estimer la taille des fichiers. Et chaque fichier peut être de taille différente. Les tailles varient d&#39;une heure à l&#39;autre et de jour en jour. Si vous allez recevoir des fichiers CDF, il est utile d&#39;être prêt à gérer beaucoup de données.

<br> 

**Combien de fichiers vais-je recevoir ?**

Encore une fois, il est difficile d&#39;estimer cela. Cependant, si vous allez recevoir des fichiers CDF, il est utile d&#39;être prêt à gérer beaucoup de données.

<br> 

## Intégrité des données {#data-integrity}

**Comment puis-je vérifier l’intégrité des données transférées vers Amazon S3 ?**

[!DNL Amazon] divise les fichiers volumineux en plusieurs parties plus petites et les télécharge vers [!DNL Amazon S3] l’aide du téléchargement en plusieurs parties. Ensuite, il génère une `ETag` valeur pour le téléchargement en plusieurs parties. Il calcule d&#39;abord les sommes de contrôle MD5 individuelles de chaque pièce téléchargée, puis les concatène en une seule chaîne. Ensuite, il calcule la somme de contrôle MD5 de la chaîne. La somme de contrôle résultante (la `ETag`) est ensuite ajoutée avec un trait d’union et le nombre total de pièces utilisées pour le téléchargement. Par exemple, le fichier `ETag` qui a été divisé en 5 parties au cours du téléchargement peut ressembler à ceci : `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**Combien de temps stockez-vous des fichiers CDF ?**

Les données sont supprimées après 8 (huit) jours.

<br> 

**Puis-je obtenir des fichiers CDF rétroactivement ou pour les jours précédents ?**

Vous ne pouvez générer des fichiers CDF que pour les 8 derniers jours. Il n’est pas possible de générer à nouveau des fichiers CDF pour des intervalles plus anciens que les 8 derniers jours.

>[!MORELIKETHIS]
>
>* [Flux de données client](../features/cdf-files.md)

