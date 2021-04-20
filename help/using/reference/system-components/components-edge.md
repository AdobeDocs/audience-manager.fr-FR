---
description: L'Audience Manager utilise des topologies de pointe distribuées pour répondre aux exigences de nos systèmes par des sources externes.
seo-description: L'Audience Manager utilise des topologies de pointe distribuées pour répondre aux exigences de nos systèmes par des sources externes.
seo-title: Présentation du centre de données Edge
solution: Audience Manager
title: Présentation du centre de données Edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# Présentation du centre de données Edge{#understanding-the-edge-data-center}

L&#39;Audience Manager utilise des topologies de pointe distribuées pour répondre aux exigences de nos systèmes par des sources externes.

## Bases du centre de données Edge {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

L&#39;informatique avancée offre de meilleures performances en réponse à une demande diffuse à l&#39;échelle d&#39;Internet, car le &quot;bord&quot; lui-même est une frontière mondiale. Cela signifie que [!DNL Audience Manager] place dynamiquement le traitement le plus proche des sources de demande et renvoie les données selon le chemin le plus court possible. L&#39;informatique avancée permet de maintenir les performances du site, ce qui, à son tour, préserve l&#39;expérience des utilisateurs sur votre site Web. Le centre de données Edge est une passerelle clé permettant de déplacer des données dans [!DNL Audience Manager].

Le centre de données Edge [!DNL Audience Manager] comprend :

* **Serveurs principaux :** il s’agit des  [!DNL Audience Manager] systèmes principaux. Ils mettent à jour et fournissent des données aux serveurs Edge.

* **Serveurs Edge : il s’agit** généralement de serveurs d’applications et/ou Web. Ils se trouvent à la frontière entre [!DNL Audience Manager] et Internet. Les serveurs Edge, tels que les systèmes [!DNL DCS] ou Akamai, gèrent généralement les données et les requêtes qui s&#39;enchaînent à [!DNL Audience Manager] ou en sortent.

* **Équilibrage de charge :** gérez les exigences inégales en matière de calcul et de traitement inhérentes aux applications Internet. Ces équilibreurs empêchent les clusters de serveurs d’être surchargés tandis que d’autres restent inactifs.

Le diagramme suivant illustre l&#39;environnement du centre de données du périmètre de l&#39;Audience Manager.

![](assets/edge_data_center.png)

## Répartition géographique et équilibrage de charge {#geo-dist-balance}

Voir la section [!DNL DCS] dans [Composants de collecte de données](../../reference/system-components/components-data-collection.md).
