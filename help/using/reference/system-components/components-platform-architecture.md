---
description: Cette carte contient les principaux systèmes Audience Manager. Il représente visuellement le flux de données vers, depuis et entre les composants Audience Manager.
seo-description: This map contains the major Audience Manager systems. It visually represents how data flows into, out of, and among Audience Manager components.
seo-title: Platform Architecture  Data Flow Map
solution: Audience Manager
title: Carte des flux de données de l’architecture de Platform
uuid: d845af1d-f448-4f4c-948e-b2c89f125086
feature: System Components
exl-id: 6543df7d-aac5-4181-87a8-bc47edd2e951
TQID: https://experienceleague.adobe.com/AuYZKnavjMq-XyilPWgEeWASzFB3K5HuAqx-wsE-H9k
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 0%

---

# Architecture de Platform : mappage des flux de données{#platform-architecture-data-flow-map}

Cette carte contient les principaux systèmes Audience Manager. Il représente visuellement le flux de données vers, depuis et entre les composants Audience Manager.

## Comment lire cette carte {#compmap}

<!-- 

c_compmap.xml

 -->

Sur la carte, la zone grise contient les systèmes [!DNL Audience Manager]. Certains composants sont entièrement internes et d&#39;autres se trouvent à la frontière entre le [!DNL Audience Manager] et le monde extérieur. En tant que client [!DNL Audience Manager], les composants internes sont souvent transparents ou inaccessibles. Cependant, vous pouvez parfois interagir avec ces systèmes par le biais de l’interface utilisateur ou des intégrations de données. Les systèmes en périphérie de la boîte collectent et envoient des données entre le [!DNL Audience Manager] et le monde extérieur.

Les couleurs définissent le type de données qui entre et sort des [!DNL Audience Manager]. Le vert correspond aux données client, le bleu aux données client (personnes qui visitent votre site) et l’orange aux données utilisées pour la création de rapports.

Pour obtenir une description du système et un résumé, reportez-vous aux sections data [action](../../reference/system-components/components-data-action.md), [collection](../../reference/system-components/components-data-collection.md), [traitement](../../reference/system-components/components-data-processing.md) et [gestion des balises](../../reference/system-components/components-tag-management.md).

![](assets/flowmap.png)
