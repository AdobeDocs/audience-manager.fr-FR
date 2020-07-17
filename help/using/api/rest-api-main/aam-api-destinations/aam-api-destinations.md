---
description: Méthodes qui vous permettent de travailler par programmation avec les fonctions de destination.
seo-description: Méthodes qui vous permettent de travailler par programmation avec les fonctions de destination.
seo-title: 'Méthodes d’API de destination '
solution: Audience Manager
title: 'Méthodes d’API de destination '
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 15%

---


# Méthodes d’API de destination {#destination-api-methods}

Méthodes qui vous permettent de travailler par programmation avec les fonctions de destination.

<!-- c_destinations_api.xml -->

En Audience Manager, une destination est tout autre système (serveur publicitaire, [!DNL DSP]réseau publicitaire, échange, cookie propriétaire, etc.) avec lequel vous souhaitez partager des données.

## Types de destination : URL et cookie {#destination-types}

Liste les variables utilisées par le `destinationType` paramètre. Spécifiez `push` ou `ADS` pour travailler avec un [!UICONTROL URL] ou [!UICONTROL cookie destination]un. Vous ne pouvez pas créer [!UICONTROL server-to-server destinations] avec les méthodes de destination disponibles [!DNL API] .

<!-- r_destination_types.xml -->

| Type de destination de l&#39;API | Type de destination de l’interface utilisateur |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Comment choisir un type de destination](../../../features/destinations/destinations.md)

