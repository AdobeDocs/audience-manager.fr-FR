---
description: Audience Manager utilise des topologies distribuées par Edge et Edge pour répondre aux exigences de nos systèmes par des sources externes.
seo-description: Audience Manager utilise des topologies distribuées par Edge et Edge pour répondre aux exigences de nos systèmes par des sources externes.
seo-title: Présentation du Centre de données Edge
solution: Audience Manager
title: Présentation du Centre de données Edge
uuid: 4177 e 666-99 f 4-453 d -94 dd -058 c 6182 c 8 d 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Understanding the Edge Data Center{#understanding-the-edge-data-center}

Audience Manager utilise des topologies distribuées par Edge et Edge pour répondre aux exigences de nos systèmes par des sources externes.

## Edge Data Center Basics {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

L'informatique Edge offre des performances accrues en réponse à la demande à l'échelle Internet, car le « edge » est une limite globale. This means [!DNL Audience Manager] dynamically places processing closest to the sources of demand and returns data by the shortest possible path. L'informatique Edge permet de conserver les performances du site, ce qui préserve l'expérience de l'utilisateur sur votre site Web. The edge data center is a key gateway for moving data in and out of [!DNL Audience Manager].

The [!DNL Audience Manager] edge data center includes:

* **Serveurs principaux :** Il s'agit des [!DNL Audience Manager] systèmes principaux. Elles mettent à jour et fournissent des données aux serveurs Edge.

* **Serveurs Edge :** En règle générale, il s'agit de serveurs d'applications et/ou Web. They sit at the boundary between [!DNL Audience Manager] and the Internet. Edge servers, such as the [!UICONTROL DCS] or Akamai systems, typically handle data and requests flowing into and out of [!DNL Audience Manager].

* **Équilibreurs de charge :** Gérez les exigences de traitement/traitement inégales inhérentes aux applications Internet. Ces équilibreurs empêchent les clusters de serveurs d'être surchargés alors que d'autres restent inactifs.

Le diagramme suivant illustre l'environnement Centre de données Edge d'Audience Manager.

![](assets/edge_data_center.png)

## Geographic Distribution and Load Balancing {#geo-dist-balance}

See the [!UICONTROL DCS] section in [Data Collection Components](../../reference/system-components/components-data-collection.md).
