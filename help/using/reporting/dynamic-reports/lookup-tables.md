---
description: Placez les données dans les fichiers journaux du rapport Performances de remise dans des tableaux contenant uniquement des ID. Placez les métadonnées non identifiables dans des tableaux de recherche distincts pour réduire la taille du fichier et les temps de traitement.
seo-description: Placez les données dans les fichiers journaux du rapport Performances de remise dans des tableaux contenant uniquement des ID. Placez les métadonnées non identifiables dans des tableaux de recherche distincts pour réduire la taille du fichier et les temps de traitement.
seo-title: Amélioration des délais de traitement des fichiers journaux avec les tables de recherche
solution: Audience Manager
title: Amélioration des délais de traitement des fichiers journaux avec les tables de recherche
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Amélioration des délais de traitement des fichiers journaux avec les tables de recherche{#improve-log-file-processing-times-with-lookup-tables}

Placez les données dans les fichiers journaux du rapport Performances de remise dans des tableaux contenant uniquement des ID. Placez les métadonnées non identifiables dans des tableaux de recherche distincts pour réduire la taille du fichier et les temps de traitement.

<!-- 

c_lookup_tables.xml

 -->

## Les métadonnées du fichier journal augmentent la taille du fichier et le temps de traitement

Un fichier journal type utilisé par le [!UICONTROL Delivery Performance] rapport contient généralement des milliers de lignes et des dizaines de colonnes. Il se compose d’identifiants numériques et d’informations lisibles par l’utilisateur, telles que les noms des créatifs, des annonceurs, des ordres d’insertion, etc.

Ces informations non-ID sont appelées *`metadata`* (c’est-à-dire des informations sur d’autres informations) et sont écrites dans chaque ligne du fichier journal.

Cependant, le [!UICONTROL Delivery Performance] rapport fonctionne principalement avec les ID du fichier journal. Les métadonnées sont utiles, mais répétitives. Il augmente la taille du fichier et le temps d’assimilation des données.

## Réduction de la taille du fichier et réduction du temps de traitement avec les tableaux d’index

Pour améliorer les performances, votre fichier de données principal ne doit contenir que des ID. Placez les métadonnées dans une table de recherche (ou index) distincte et liez ces enregistrements au fichier principal avec une variable clé commune aux deux.

## Comment les tables de recherche réduisent la taille du fichier

Supposons que vous ayez un fichier de données qui ressemble à celui ci-dessous.

| Identifiant utilisateur | Identifiant de publicité | Nom de la publicité | ID de commande | Nom de commande | Identifiant publicitaire | Nom du publicitaire |
|---|---|---|---|---|---|---|
| 1 | 111 | Chaussure A | 456 | Dessinateurs | 27 | Société A |
| 2 | 111 | Chaussure A | 456 | Dessinateurs | 27 | Société A |
| 3 | 111 | Chaussure A | 456 | Dessinateurs | 27 | Société A |
| 4 | 222 | Chaussure B | 789 | Randonnée | 14 | Société B |
| 5 | 222 | Chaussure B | 789 | Randonnée | 14 | Société B |

<br> 

Voici le même fichier journal avec les métadonnées supprimées. Le fichier est plus petit et plus facile à traiter lorsqu’il se compose uniquement d’ID.

| Identifiant utilisateur | Identifiant de publicité | ID de commande | Identifiant publicitaire |
|---|---|---|---|
| 1 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Le fichier de recherche ci-dessous contient les métadonnées et peut être lié de nouveau au fichier principal avec l’identifiant de publicité. Notez également la taille. Au lieu de répéter plusieurs fois chaque annonceur, vous n’avez besoin que d’une référence pour chacun d’eux.

| Identifiant de publicité | Nom de la publicité | Nom de commande | Nom du publicitaire |
|---|---|---|---|
| 111 | Chaussure A | Dessinateurs | Société A |
| 222 | Chaussure B | Randonnée | Société B |

## Les API peuvent éliminer le besoin de tables de recherche

Si votre système de service publicitaire comporte une API, vous n’aurez peut-être pas besoin d’envoyer des métadonnées dans un fichier de recherche. Nous pouvons peut-être obtenir ces informations via l'API. Dans ce cas, vos fichiers journaux ne doivent contenir que des ID. Nous travaillerons avec vous pour déterminer si les métadonnées peuvent être obtenues par le biais d'une API.

>[!MORELIKETHIS]
>
>* [Rapport sur la livraison et les performances](../../reporting/dynamic-reports/delivery-performance-report.md)

