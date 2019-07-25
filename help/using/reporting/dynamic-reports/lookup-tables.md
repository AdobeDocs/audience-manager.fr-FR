---
description: Placez les données dans les fichiers journaux du rapport Performance de diffusion dans des tableaux contenant uniquement des ID. Placez des métadonnées non ID dans des tableaux de recherche distincts afin de réduire la taille du fichier et les temps de traitement.
seo-description: Placez les données dans les fichiers journaux du rapport Performance de diffusion dans des tableaux contenant uniquement des ID. Placez des métadonnées non ID dans des tableaux de recherche distincts afin de réduire la taille du fichier et les temps de traitement.
seo-title: Amélioration des délais de traitement des fichiers journaux avec les tables de recherche
solution: Audience Manager
title: Amélioration des délais de traitement des fichiers journaux avec les tables de recherche
uuid: ffc 77618-474 b -455 e -9 c 91-15 b 32 fc 151 a 5
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Improve Log File Processing Times with Lookup Tables{#improve-log-file-processing-times-with-lookup-tables}

Placez les données dans les fichiers journaux du rapport Performance de diffusion dans des tableaux contenant uniquement des ID. Placez des métadonnées non ID dans des tableaux de recherche distincts afin de réduire la taille du fichier et les temps de traitement.

<!-- 

c_lookup_tables.xml

 -->

## Les métadonnées du fichier journal augmentent la taille du fichier et le temps de traitement

A typical log file used by the [!UICONTROL Delivery Performance] report usually contains thousands of rows and dozens of columns. Il s'agit d'ID numériques et d'informations intelligibles, telles que des noms pour les créatifs, les annonceurs, les commandes d'insertion, etc.

This non-ID information is referred to as *`metadata`* (i.e., information about other information) and gets written in each row of the log file.

However, the [!UICONTROL Delivery Performance] report mainly works with the IDs in the log file. Les métadonnées sont utiles, mais répétitives. Elle augmente la taille du fichier et le temps d'ingestion des données.

## Réduire la taille du fichier et réduire le temps de traitement avec les tableaux d'index

Pour améliorer les performances, votre fichier de données principal doit contenir uniquement des ID. Placez les métadonnées dans un tableau de recherche (ou index) distinct et liez ces enregistrements au fichier principal avec une variable clé commune aux deux.

## Réduction de la taille du fichier dans les tableaux de recherche

Imaginons que vous disposez d'un fichier de données semblable à celui-ci.

| Identifiant utilisateur | Identifiant de publicité | Nom de la publicité | ID de commande | Nom de commande | Identifiant publicitaire | Nom du publicitaire |
|---|---|---|---|---|---|---|
| 1 | 111 | Chaussure A | 456 | Chaussures de sport | 27 | Société A |
| 2 | 111 | Chaussure A | 456 | Chaussures de sport | 27 | Société A |
| 3 | 111 | Chaussure A | 456 | Chaussures de sport | 27 | Société A |
| 4 | 222 | Chaussure B | 789 | Randonnée | 14 | Société B |
| 5 | 222 | Chaussure B | 789 | Randonnée | 14 | Société B |

<br> 

Voici le même fichier journal que les métadonnées supprimées. Le fichier est plus petit et plus facile à traiter lorsqu'il se compose d'ID uniquement.

| Identifiant utilisateur | Identifiant de publicité | ID de commande | Identifiant publicitaire |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Le fichier de recherche ci-dessous contient les métadonnées et peut être lié au fichier principal avec l'identifiant de publicité. Notez également la taille. Au lieu de répéter chaque annonceur plusieurs fois, vous n'avez besoin que d'une référence pour chacune d'elles.

| Identifiant de publicité | Nom de la publicité | Nom de commande | Nom du publicitaire |
|---|---|---|---|
| 111 | Chaussure A | Chaussures de sport | Société A |
| 222 | Chaussure B | Randonnée | Société B |

## API Peut éliminer le besoin de tables de recherche

Si votre système de service publicitaire comporte une API, il est possible que vous n'ayez pas à envoyer des métadonnées dans un fichier de recherche. Nous pouvons obtenir ces informations par le biais de l'API. Dans ce cas, vos fichiers journaux ne doivent contenir que des ID. Nous collaborerons avec vous pour déterminer si les métadonnées peuvent être obtenues via une API.

>[!MORE_ LIKE_ THIS]
>
>* [Rapport de remise et de performance](../../reporting/dynamic-reports/delivery-performance-report.md)

