---
description: Questions fréquentes sur les fichiers de flux de données client (CDF).
seo-description: Questions fréquentes sur les fichiers de flux de données client (CDF).
seo-title: FAQ sur le flux de données client
solution: Audience Manager
title: FAQ sur le flux de données client
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# FAQ sur le flux de données client{#customer-data-feed-faq}

Questions fréquentes sur les fichiers de flux de données client (CDF).

## Stockage Amazon S3 {#amazon-s3-storage}

**Où est stocké mon fichier CDF[!DNL Amazon]?**

Votre fichier CDF est stocké dans le répertoire `aam-cdf` racine sur un [!DNL Amazon S3] serveur. Ce compartiment par défaut est géré par [!DNL Audience Manager]. Voir aussi Conventions [de dénomination des fichiers de flux de données](../features/cdf-files.md#cdf-naming-conventions)client.

<br> 

**Mon compartiment de stockage est-il sécurisé ?**

Oui. Les clients ont accès à leur propre espace de stockage uniquement. Vous aurez accès en lecture seule à votre compartiment de stockage. Vous n'aurez pas accès en écriture.

<br> 

**Puis-je personnaliser mon compartiment de stockage ou stocker des fichiers dans un autre répertoire ?**

Non. La personnalisation et les autres options de stockage ne sont pas disponibles.

<br> 

**Il manque un fichier dans mon répertoire pendant une heure particulière. Où est-ce ?**

Un fichier manquant signifie que [!DNL Audience Manager] vous n’avez pas pu traiter vos fichiers CDF pendant cette heure. Cela se produit généralement lorsque nos serveurs sont en retard dans le traitement des fichiers CDF. Dans ce cas, votre fichier n’est pas perdu. Il apparaîtra dans un répertoire horaire ultérieur une fois que notre système aura une chance de rattraper. Voir aussi Notifications [de traitement des fichiers de flux de données](../features/cdf-files.md#cdf-file-processing-notifications)client.

<br> 

**Comment savoir quand mes fichiers CDF sont prêts ?**

Voir Notifications [de traitement des fichiers de flux de données](../features/cdf-files.md#cdf-file-processing-notifications)client.

<br> 

## Taille du fichier {#file-sizes}

**Quelles tailles de fichier dois-je attendre ? Quelle est la taille d'un fichier CDF moyen ?**

Il est difficile d’estimer la taille des fichiers. Et chaque fichier peut être de taille différente. Les tailles varient d'heure en heure et jour en jour. Si vous recevez des fichiers CDF, il est utile d'être prêt à gérer beaucoup de données.

<br> 

**Combien de fichiers vais-je recevoir ?**

Encore une fois, il est difficile de l'estimer. Cependant, si vous allez recevoir des fichiers CDF, il est utile d'être prêt à gérer beaucoup de données.

<br> 

## Intégrité des données {#data-integrity}

**Comment puis-je vérifier l’intégrité des données transférées vers Amazon S3 ?**

Les fichiers d’une taille supérieure à 16 MiB sont divisés en blocs de 16 MiB et téléchargés vers [!DNL Amazon S3] l’aide d’un téléchargement en plusieurs parties.

[!DNL Amazon] génère une `ETag` valeur pour les téléchargements en plusieurs parties. Il commence par calculer les sommes de contrôle MD5 individuelles de chaque pièce téléchargée, puis les concatène en une seule chaîne. Ensuite, il calcule la somme de contrôle MD5 de la chaîne. La somme de contrôle résultante (la `ETag`) est ensuite ajoutée avec un trait d’union et le nombre total de pièces utilisées pour le téléchargement. Par exemple, le fichier `ETag` qui a été divisé en 5 parties pendant le téléchargement peut ressembler à quelque chose comme ceci : `2c51427d19021e88cf3395365895b6d4-5`

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

