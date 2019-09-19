---
description: Audience Manager utilise des topologies de pointe distribuées pour répondre aux exigences posées sur nos systèmes par des sources externes.
seo-description: Audience Manager utilise des topologies de pointe distribuées pour répondre aux exigences posées sur nos systèmes par des sources externes.
seo-title: Présentation du centre de données Edge
solution: Audience Manager
title: Présentation du centre de données Edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Présentation du centre de données Edge{#understanding-the-edge-data-center}

Audience Manager utilise des topologies de pointe distribuées pour répondre aux exigences posées sur nos systèmes par des sources externes.

## Bases du centre de données Edge {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

L'informatique de pointe offre de meilleures performances en réponse à une demande diffusée à l'échelle d'Internet, car le "bord" lui-même est une frontière mondiale. Cela signifie qu’il place [!DNL Audience Manager] dynamiquement le traitement le plus proche des sources de demande et renvoie les données selon le chemin le plus court possible. L’informatique Edge permet de maintenir les performances du site, ce qui, à son tour, préserve l’expérience des utilisateurs sur votre site Web. Le centre de données Edge est une passerelle clé pour le déplacement des données en entrée et en sortie [!DNL Audience Manager].

Le centre de données [!DNL Audience Manager] Edge comprend :

* **** Serveurs principaux : Ce sont les principaux [!DNL Audience Manager] systèmes. Ils mettent à jour et fournissent des données aux serveurs Edge.

* **** Serveurs Edge : Il s’agit généralement de serveurs d’applications et/ou Web. Ils sont assis à la limite entre [!DNL Audience Manager] et Internet. Les serveurs Edge, tels que les systèmes [!UICONTROL DCS] ou Akamai, gèrent généralement les données et les requêtes qui entrent et sortent [!DNL Audience Manager].

* **** Équilibrage de charge : Gérez les demandes inégales de traitement et de calcul inhérentes aux applications Internet. Ces équilibreurs empêchent les clusters de serveurs d’être surchargés tandis que d’autres restent inactifs.

Le diagramme suivant illustre l’environnement du centre de données Edge d’Audience Manager.

![](assets/edge_data_center.png)

## Répartition géographique et équilibrage de charge {#geo-dist-balance}

Reportez-vous à la [!UICONTROL DCS] section Composants [de collecte de](../../reference/system-components/components-data-collection.md)données.
