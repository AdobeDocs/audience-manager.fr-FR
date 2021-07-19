---
description: Placez les données dans les fichiers journaux du rapport Performance de diffusion dans des tableaux contenant uniquement des identifiants. Placez des métadonnées non identifiables dans des tables de recherche distinctes afin de réduire la taille du fichier et les temps de traitement.
seo-description: Placez les données dans les fichiers journaux du rapport Performance de diffusion dans des tableaux contenant uniquement des identifiants. Placez des métadonnées non identifiables dans des tables de recherche distinctes afin de réduire la taille du fichier et les temps de traitement.
seo-title: Amélioration des délais de traitement des fichiers journaux avec les tables de correspondance
solution: Audience Manager
title: Amélioration des délais de traitement des fichiers journaux avec les tables de correspondance
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Référence de création de rapports
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 18%

---

# Amélioration des délais de traitement des fichiers journaux avec les tables de correspondance{#improve-log-file-processing-times-with-lookup-tables}

Placez les données dans les fichiers journaux du rapport Performance de diffusion dans des tableaux contenant uniquement des identifiants. Placez des métadonnées non identifiables dans des tables de recherche distinctes afin de réduire la taille du fichier et les temps de traitement.

<!-- 

c_lookup_tables.xml

 -->

## Les métadonnées de fichier journal augmentent la taille du fichier et le temps de traitement

Un fichier journal type utilisé par le rapport [!UICONTROL Delivery Performance] contient généralement des milliers de lignes et des dizaines de colonnes. Il se compose d’identifiants numériques et d’informations lisibles par l’utilisateur, telles que les noms des créatifs, des annonceurs, des commandes d’insertion, etc.

Ces informations non-ID sont appelées *`metadata`* (c’est-à-dire des informations sur d’autres informations) et sont écrites dans chaque ligne du fichier journal.

Cependant, le rapport [!UICONTROL Delivery Performance] fonctionne principalement avec les identifiants du fichier journal. Les métadonnées sont utiles, mais répétitives. Cela augmente la taille du fichier et les temps d’ingestion des données.

## Réduction de la taille du fichier et réduction du temps de traitement avec des tableaux d’index

Pour améliorer les performances, votre fichier de données principal ne doit contenir que des identifiants. Placez les métadonnées dans une table de recherche (ou index) distincte et liez ces enregistrements au fichier principal avec une variable clé commune aux deux.

## Comment les tables de recherche réduisent la taille du fichier

Supposons que vous ayez un fichier de données qui ressemble à celui ci-dessous.

| Identifiant utilisateur | Identifiant de publicité | Nom de la publicité | ID de commande | Nom de commande | Identifiant publicitaire | Nom de l’annonceur |
|---|---|---|---|---|---|---|
| 1 | 111 | Chaussure A | 456 | Des baskets | 27 | Société A |
| 2 | 111 | Chaussure A | 456 | Des baskets | 27 | Société A |
| 3 | 111 | Chaussure A | 456 | Des baskets | 27 | Société A |
| 4 | 222 | Chaussure B | 789 | La randonnée | 14 | Société B |
| 5 | 222 | Chaussure B | 789 | La randonnée | 14 | Société B |

<br> 

Voici le même fichier journal avec les métadonnées supprimées. Le fichier est plus petit et plus facile à traiter lorsqu’il se compose uniquement d’identifiants.

| Identifiant utilisateur | Identifiant de publicité | ID de commande | Identifiant publicitaire |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 1 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Le fichier de recherche ci-dessous contient les métadonnées et peut être lié à nouveau au fichier principal avec l’ID de publicité. Notez également la taille. Au lieu de répéter plusieurs fois chaque annonceur, vous n’avez besoin que d’une référence pour chacun d’eux.

| Identifiant de publicité | Nom de la publicité | Nom de commande | Nom de l’annonceur |
|---|---|---|---|
| 111 | Chaussure A | Des baskets | Société A |
| 222 | Chaussure B | La randonnée | Société B |

## Les API peuvent éliminer la nécessité de tables de recherche

Si votre système de service publicitaire dispose d’une API, vous n’aurez peut-être pas besoin d’envoyer des métadonnées dans un fichier de recherche. Nous pouvons peut-être obtenir ces informations via l’API. Dans ce cas, vos fichiers journaux ne doivent contenir que des identifiants. Nous collaborerons avec vous pour déterminer si des métadonnées peuvent être obtenues via une API.
