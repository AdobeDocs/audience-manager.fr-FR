---
description: Questions fréquentes sur les fichiers de flux de données client (CDF).
seo-description: Questions fréquentes sur les fichiers de flux de données client (CDF).
seo-title: FAQ sur le flux de données client
solution: Audience Manager
title: FAQ sur le flux de données client
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
translation-type: tm+mt
source-git-commit: 7018705c130bf7c65f3a69da5e4bd9e0666423bc

---


# FAQ sur le flux de données client{#customer-data-feed-faq}

Questions fréquentes sur les fichiers de flux de données client (CDF).

## Amazon S3  {#amazon-s3-storage}

**Où est stocké mon fichier CDF[!DNL Amazon]?**

Votre fichier CDF est stocké dans le répertoire `aam-cdf` racine sur un [!DNL Amazon S3] serveur. Ce compartiment par défaut est géré par [!DNL Audience Manager]. Voir aussi Conventions [de dénomination des fichiers de flux de données](../features/cdf-files.md#cdf-naming-conventions)client.

<br> 

**Est-ce que mon   est sûr ?**

Oui. Les clients ont accès à leur propre espace de  de  uniquement. Vous aurez accès en lecture seule à votre  de . Vous n&#39;aurez pas accès en écriture.

<br> 

**Puis-je personnaliser mon   de compartiment ou stocker des fichiers dans un autre répertoire ?**

Non. Les options de personnalisation et d’autres options de  de  ne sont pas disponibles.

<br> 

**Il manque un fichier dans mon répertoire pendant une heure particulière. Où est-ce ?**

Un fichier manquant signifie qu’il n’ [!DNL Audience Manager] a pas été possible de traiter vos fichiers CDF pendant cette heure. Cela se produit généralement lorsque nos serveurs sont en retard dans le traitement des fichiers CDF. Dans ce cas, votre fichier n’est pas perdu. Il apparaîtra dans un répertoire horaire ultérieur une fois que notre système aura une chance de rattraper. Voir aussi Notifications [de traitement des fichiers de flux de données](../features/cdf-files.md#cdf-file-processing-notifications)client.

<br> 

**Comment savoir quand mes fichiers CDF sont prêts ?**

Voir Notifications [de traitement des fichiers de flux de données](../features/cdf-files.md#cdf-file-processing-notifications)client.

<br> 

## Taille du fichier {#file-sizes}

**Quelles tailles de fichier dois-je attendre ? Quelle est la taille d&#39;un fichier CDF moyen ?**

Il est difficile d’estimer la taille des fichiers. Et chaque fichier peut être de taille différente. Les tailles varient d&#39;heure en heure et jour en jour. Si vous recevez des fichiers CDF, il est utile d&#39;être prêt à gérer beaucoup de données.

<br> 

**Combien de fichiers vais-je recevoir ?**

Encore une fois, il est difficile de l&#39;estimer. Cependant, si vous allez recevoir des fichiers CDF, il est utile d&#39;être prêt à gérer beaucoup de données.

<br> 

## Intégrité des données {#data-integrity}

**Comment puis-je vérifier l’intégrité des données transférées vers Amazon S3 ?**

[!DNL Amazon] sépare les fichiers volumineux en parties plus petites et les télécharge vers [!DNL Amazon S3] l’aide du téléchargement en plusieurs parties. Il génère ensuite une `ETag` valeur pour le téléchargement en plusieurs parties. Il calcule d’abord les sommes de contrôle MD5 individuelles de chaque pièce téléchargée, puis les concatène en une seule chaîne. Ensuite, il calcule la somme de contrôle MD5 de la chaîne. La somme de contrôle résultante (la `ETag`) est ensuite ajoutée avec un trait d’union et le nombre total de pièces utilisées pour le téléchargement. Par exemple, le fichier `ETag` qui a été divisé en 5 parties pendant le téléchargement peut ressembler à quelque chose comme ceci : `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Data Retention {#data-retension}

**Combien de temps stockez-vous les fichiers CDF ?**

Les données sont supprimées au bout de 8 (8) jours.

<br> 

**Puis-je obtenir des fichiers CDF rétroactivement ou pour les jours précédents ?**

Vous ne pouvez générer des fichiers CDF que pour les 8 derniers jours. Les fichiers CDF pour les intervalles antérieurs aux 8 derniers jours ne peuvent pas être recréés.

>[!MORELIKETHIS]
>
>* [Flux de données client](../features/cdf-files.md)

