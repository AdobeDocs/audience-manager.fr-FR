---
description: Audience Manager utilise des topologies de périphérie distribuées pour répondre aux exigences posées sur nos systèmes par des sources externes.
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

Audience Manager utilise des topologies de périphérie distribuées pour répondre aux exigences posées sur nos systèmes par des sources externes.

## Concepts de base du centre de données Edge {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

L’informatique Edge offre de meilleures performances en réponse à une demande différée à l’échelle d’Internet, car le &quot;bord&quot; lui-même est une frontière mondiale. Cela signifie que [!DNL Audience Manager] place dynamiquement le traitement le plus proche des sources de demande et renvoie les données selon le chemin le plus court possible. L’informatique Edge permet de maintenir les performances du site, ce qui, à son tour, préserve l’expérience de l’utilisateur sur votre site web. Le centre de données Edge est une passerelle clé pour déplacer des données vers et depuis [!DNL Audience Manager].

Le centre de données de périphérie [!DNL Audience Manager] comprend :

* **Serveurs principaux :** Il s’agit des systèmes [!DNL Audience Manager] principaux. Ils mettent à jour et fournissent des données aux serveurs Edge.

* **Serveurs Edge :** En règle générale, il s’agit de serveurs d’applications et/ou web. Ils se trouvent à la frontière entre [!DNL Audience Manager] et Internet. Les serveurs Edge, tels que les systèmes [!DNL DCS] ou Akamai, gèrent généralement les données et les requêtes entrant et sortant de [!DNL Audience Manager].

* **équilibreurs de charge :** gérez les exigences inégales de calcul/traitement inhérentes aux applications Internet. Ces équilibreurs empêchent la surcharge des clusters de serveurs, tandis que d&#39;autres restent inactifs.

Le diagramme suivant illustre l’environnement du centre de données Audience Manager Edge.

![](assets/edge_data_center.png)

## Distribution géographique et équilibrage de charge {#geo-dist-balance}

Voir la section [!DNL DCS] dans [Composants de collecte de données](../../reference/system-components/components-data-collection.md).
