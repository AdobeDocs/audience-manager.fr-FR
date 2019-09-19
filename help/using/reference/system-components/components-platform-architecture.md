---
description: Cette carte contient les principaux systèmes Audience Manager. Il représente visuellement la manière dont les données s’enchaînent dans, en dehors et entre les composants d’Audience Manager.
seo-description: Cette carte contient les principaux systèmes Audience Manager. Il représente visuellement la manière dont les données s’enchaînent dans, en dehors et entre les composants d’Audience Manager.
seo-title: Carte du flux de données de l'architecture de plateforme
solution: Audience Manager
title: Carte du flux de données de l'architecture de plateforme
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Architecture de plateforme : Carte du flux de données{#platform-architecture-data-flow-map}

Cette carte contient les principaux systèmes Audience Manager. Il représente visuellement la manière dont les données s’enchaînent dans, en dehors et entre les composants d’Audience Manager.

## Comment lire cette carte {#compmap}

<!-- 

c_compmap.xml

 -->

Dans la carte, la zone grise contient [!DNL Audience Manager] des systèmes. Certains composants sont complètement internes et d'autres se trouvent à la frontière entre le monde [!DNL Audience Manager] et le monde extérieur. En tant que [!DNL Audience Manager] client, les composants internes sont souvent transparents ou inaccessibles. Cependant, vous pouvez parfois interagir avec ces systèmes par le biais de l’interface utilisateur ou des intégrations de données. Les systèmes au bord de la boîte collectent et envoient des données entre [!DNL Audience Manager] et le monde extérieur.

Les couleurs définissent le type de données entrant et sortant [!DNL Audience Manager]. Le vert désigne les données client, le bleu, les données client (visiteurs de votre site) et l’orange, les données utilisées pour la création de rapports.

Pour obtenir des descriptions et des résumés du système, reportez-vous aux sections [Action](../../reference/system-components/components-data-action.md)de données, [collecte](../../reference/system-components/components-data-collection.md), [traitement](../../reference/system-components/components-data-processing.md)et gestion des [balises.](../../reference/system-components/components-tag-management.md)

![](assets/flowmap.png)

