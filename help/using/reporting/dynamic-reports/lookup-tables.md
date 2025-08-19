---
description: Placer les données des fichiers de logs des rapports Performances de diffusion dans des tables contenant uniquement des identifiants. Placez les métadonnées non-ID dans des tables de recherche distinctes pour réduire la taille du fichier et les temps de traitement.
seo-description: Put data in Delivery Performance report log files into tables that contain IDs only. Put non-ID metadata in separate lookup tables to help reduce file size and processing times.
seo-title: Improve Log File Processing Times with Lookup Tables
solution: Audience Manager
title: Amélioration des temps de traitement des fichiers journaux avec les tables de recherche
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Reporting Reference
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 14%

---

# Amélioration des temps de traitement des fichiers journaux avec les tables de recherche{#improve-log-file-processing-times-with-lookup-tables}

Placer les données des fichiers de logs des rapports Performances de diffusion dans des tables contenant uniquement des identifiants. Placez les métadonnées non-ID dans des tables de recherche distinctes pour réduire la taille du fichier et les temps de traitement.

<!-- 

c_lookup_tables.xml

 -->

## Les métadonnées du fichier journal augmentent la taille du fichier et le temps de traitement

Un fichier journal type utilisé par le rapport [!UICONTROL Delivery Performance] contient généralement des milliers de lignes et des dizaines de colonnes. Il se compose d’identifiants numériques et d’informations lisibles par l’utilisateur, telles que les noms des créatifs, des annonceurs, des ordres d’insertion, etc.

Ces informations non identifiables sont appelées *`metadata`* (c’est-à-dire informations sur d’autres informations) et sont écrites dans chaque ligne du fichier journal.

Cependant, le rapport [!UICONTROL Delivery Performance] fonctionne principalement avec les identifiants figurant dans le fichier journal. Les métadonnées sont utiles, mais répétitives. Cela augmente la taille du fichier et les temps d’ingestion des données.

## Réduction de la taille des fichiers et du temps de traitement grâce aux tables d’index

Pour améliorer les performances, votre fichier de données principal ne doit contenir que des identifiants. Placez les métadonnées dans une table de recherche (ou d’index) distincte et liez ces enregistrements au fichier principal avec une variable clé commune aux deux.

## Réduction de la taille des fichiers grâce aux tables de recherche

Supposons que vous ayez un fichier de données qui ressemble à celui ci-dessous.

| Identifiant utilisateur | Identifiant de publicité | Nom de la publicité | ID de commande | Nom de la commande | Identifiant d’annonceur | Nom de d’annonceur |
|---|---|---|---|---|---|---|
| 1 | 111 | Chaussure A | 456 | Des baskets | 27 | Société A |
| 2 | 111 | Chaussure A | 456 | Des baskets | 27 | Société A |
| 3 | 111 | Chaussure A | 456 | Des baskets | 27 | Société A |
| 4 | 222 | Chaussure B | 789 | Randonnée | 14 | Société B |
| 5 | 222 | Chaussure B | 789 | Randonnée | 14 | Société B |

<br> 

Voici le même fichier journal avec les métadonnées supprimées. Le fichier est plus petit et plus facile à traiter lorsqu’il se compose uniquement d’identifiants.

| Identifiant utilisateur | Identifiant de publicité | ID de commande | Identifiant d’annonceur |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Le fichier de recherche ci-dessous contient les métadonnées et peut être lié au fichier principal avec l’ID d’annonce. Notez également la taille. Au lieu de répéter chaque annonceur plusieurs fois, vous n’avez besoin que d’une seule référence pour chaque annonceur.

| Identifiant de publicité | Nom de la publicité | Nom de la commande | Nom de d’annonceur |
|---|---|---|---|
| 111 | Chaussure A | Des baskets | Société A |
| 222 | Chaussure B | Randonnée | Société B |

## Les API peuvent rendre inutiles les tables de recherche

Si votre système de diffusion d’annonces dispose d’une API, vous n’aurez peut-être pas besoin d’envoyer de métadonnées dans un fichier de recherche. Nous pouvons peut-être obtenir ces renseignements par l&#39;intermédiaire de l&#39;API. Si c’est le cas, vos fichiers journaux ne doivent contenir que des identifiants . Nous collaborerons avec vous pour déterminer si les métadonnées peuvent être obtenues par le biais d’une API.
