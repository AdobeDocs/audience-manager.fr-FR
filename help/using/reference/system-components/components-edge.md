---
description: L'Audience Manager utilise des topologies de pointe distribuées pour répondre aux exigences de nos systèmes par des sources externes.
seo-description: L'Audience Manager utilise des topologies de pointe distribuées pour répondre aux exigences de nos systèmes par des sources externes.
seo-title: Présentation du centre de données Edge
solution: Audience Manager
title: Présentation du centre de données Edge
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---


# Présentation du centre de données Edge{#understanding-the-edge-data-center}

L&#39;Audience Manager utilise des topologies de pointe distribuées pour répondre aux exigences de nos systèmes par des sources externes.

## Bases du centre de données Edge {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

L&#39;informatique avancée offre de meilleures performances en réponse à une demande diffuse à l&#39;échelle d&#39;Internet, car le &quot;bord&quot; lui-même est une frontière mondiale. Cela signifie qu’il place [!DNL Audience Manager] dynamiquement le traitement le plus proche des sources de demande et qu’il renvoie les données le plus rapidement possible. L&#39;informatique avancée permet de maintenir les performances du site, ce qui, à son tour, préserve l&#39;expérience des utilisateurs sur votre site Web. Le centre de données Edge est une passerelle essentielle pour déplacer les données vers [!DNL Audience Manager]et vers l&#39;extérieur.

Le centre de données [!DNL Audience Manager] Edge comprend :

* **Serveurs principaux :** Ce sont les principaux [!DNL Audience Manager] systèmes. Ils mettent à jour et fournissent des données aux serveurs Edge.

* **Serveurs Edge :** Il s’agit généralement de serveurs d’applications et/ou Web. Ils s&#39;assoient à la frontière entre [!DNL Audience Manager] et Internet. Les serveurs Edge, tels que les systèmes [!DNL DCS] ou Akamai, gèrent généralement les données et les requêtes entrant et sortant [!DNL Audience Manager].

* **Équilibrages de charge :** Gérez les exigences inégales en matière de traitement et d&#39;informatique inhérentes aux applications Internet. Ces équilibreurs empêchent les clusters de serveurs d’être surchargés tandis que d’autres restent inactifs.

Le diagramme suivant illustre l&#39;environnement du centre de données du périmètre de l&#39;Audience Manager.

![](assets/edge_data_center.png)

## Répartition géographique et équilibrage de charge {#geo-dist-balance}

Reportez-vous à la [!DNL DCS] section Composants [de](../../reference/system-components/components-data-collection.md)collecte de données.
