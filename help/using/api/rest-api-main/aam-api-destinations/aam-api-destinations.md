---
description: Méthodes qui vous permettent de travailler par programmation avec les fonctionnalités de destination.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: Méthodes d’API de destination
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 0%

---

# Méthodes d’API de destination {#destination-api-methods}

Méthodes qui vous permettent de travailler par programmation avec les fonctionnalités de destination.

<!-- c_destinations_api.xml -->

Dans Audience Manager, une destination est tout autre système (serveur de publicités, [!DNL DSP], réseau publicitaire, exchange, votre propre cookie propriétaire, etc.) avec lequel vous souhaitez partager des données.

## Types de destinations : URL et cookie {#destination-types}

Répertorie les variables utilisées par le paramètre `destinationType`. Spécifiez les `push` ou `ADS` à utiliser avec un [!UICONTROL URL] ou un [!UICONTROL cookie destination]. Vous ne pouvez pas créer de [!UICONTROL server-to-server destinations] avec les méthodes de [!DNL API] de destination disponibles.

<!-- r_destination_types.xml -->

| Type de destination de l’API | Type de destination de l’interface utilisateur |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Comment choisir un type de destination &#x200B;](../../../features/destinations/destinations.md)
