---
description: Cette carte contient les principaux systèmes d'Audience Manager. Il représente visuellement la manière dont les données s’enchaînent dans, en dehors et entre les composants d’Audience Manager.
seo-description: Cette carte contient les principaux systèmes d'Audience Manager. Il représente visuellement la manière dont les données s’enchaînent dans, en dehors et entre les composants d’Audience Manager.
seo-title: Carte du flux de données de l'architecture de plate-forme
solution: Audience Manager
title: Carte du flux de données de l'architecture de plate-forme
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 2%

---


# Architecture de Platform : map des flux de données{#platform-architecture-data-flow-map}

Cette carte contient les principaux systèmes d&#39;Audience Manager. Il représente visuellement la manière dont les données s’enchaînent dans, en dehors et entre les composants d’Audience Manager.

## Comment lire cette carte {#compmap}

<!-- 

c_compmap.xml

 -->

Dans la carte, la zone grise contient des systèmes [!DNL Audience Manager]. Certains composants sont entièrement internes et d&#39;autres se trouvent à la frontière entre [!DNL Audience Manager] et le monde extérieur. En tant que client [!DNL Audience Manager], les composants internes sont souvent transparents ou inaccessibles. Cependant, il arrive que vous vous adressiez à ces systèmes par le biais de l’interface utilisateur ou des intégrations de données. Les systèmes à la lisière de la boîte collectent et envoient des données entre [!DNL Audience Manager] et le monde extérieur.

Les couleurs définissent le type de données entrant et sortant de [!DNL Audience Manager]. Le vert désigne les données client, le bleu désigne les données client (les visiteurs de votre site) et l’orange désigne les données utilisées pour le rapports.

Pour obtenir des descriptions et des résumés du système, voir les sections [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [traitement](../../reference/system-components/components-data-processing.md) et [gestion des balises](../../reference/system-components/components-tag-management.md).

![](assets/flowmap.png)

