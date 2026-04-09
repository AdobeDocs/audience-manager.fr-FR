---
description: Méthodes qui vous permettent de travailler par programmation avec les fonctionnalités de destination.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: Méthodes d’API de destination
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
TQID: https://experienceleague.adobe.com/8fUlWE0aqgltxB-bS0X1cjE4Dg0-VvHpRjvWQmjKe5s
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: c814092e-2730-45e8-a12d-e084529f52cb
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 89
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
