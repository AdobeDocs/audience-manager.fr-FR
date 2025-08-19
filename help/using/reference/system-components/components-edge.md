---
description: Audience Manager utilise des topologies de calcul de périphérie distribuées pour répondre aux demandes de nos systèmes par des sources externes.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: Présentation du centre de données Edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Présentation du centre de données Edge{#understanding-the-edge-data-center}

Audience Manager utilise des topologies de calcul de périphérie distribuées pour répondre aux demandes de nos systèmes par des sources externes.

## Concepts de base du centre de données Edge {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

L&#39;informatique Edge offre de meilleures performances en réponse à une demande diffuse à l&#39;échelle d&#39;Internet, car la « périphérie » elle-même est une frontière mondiale. Cela signifie [!DNL Audience Manager] place dynamiquement le traitement au plus près des sources de demande et renvoie les données par le chemin le plus court possible. L’informatique Edge permet de maintenir les performances du site, ce qui préserve l’expérience utilisateur sur votre site web. Le centre de données Edge est une passerelle essentielle pour le déplacement de données dans et hors du [!DNL Audience Manager].

Le centre de données Edge de [!DNL Audience Manager] comprend les éléments suivants :

* **Serveurs principaux :** il s’agit des principaux systèmes [!DNL Audience Manager]. Ils mettent à jour et fournissent des données aux serveurs Edge.

* **Serveurs Edge :** il s’agit généralement de serveurs d’applications et/ou web. Ils sont à la frontière entre [!DNL Audience Manager] et Internet. Les serveurs Edge, tels que les systèmes [!DNL DCS] ou Akamai, gèrent généralement les données et les requêtes entrant et sortant du [!DNL Audience Manager].

* **Répartitions de charge :** permet de gérer les demandes de calcul/traitement inégales inhérentes aux applications Internet. Ces équilibreurs évitent que les clusters de serveurs soient surchargés tandis que d&#39;autres restent inactifs.

Le diagramme suivant illustre l’environnement du centre de données Edge d’Audience Manager.

![](assets/edge_data_center.png)

## Répartition géographique et équilibrage de charge {#geo-dist-balance}

Pour plus d&#39;informations, consultez la section [!DNL DCS] dans [Composants de collecte de données](../../reference/system-components/components-data-collection.md).
